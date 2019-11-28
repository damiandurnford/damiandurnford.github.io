## Welcome to GitHub Pages


<script src="https://apis.google.com/js/platform.js" async defer></script>

<script>
    function onSignIn(googleUser) {
      var profile = googleUser.getBasicProfile();
      //console.log('ID: ' + profile.getId()); // Do not send to your backend! Use an ID token instead.
      //console.log('Image URL: ' + profile.getImageUrl());
      //console.log('Name: ' + profile.getName());
      //console.log('Email: ' + profile.getEmail());
      var user_uname = profile.getName();
      var user_email = profile.getEmail();
      alert(user_uname);
    }

</script>
You can use the [editor on GitHub](https://github.com/damiandurnford/damiandurnford.github.io/edit/master/README.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/damiandurnford/damiandurnford.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.

<style>
    * {
        margin: 0;
        padding: 0;
        font-family: Arial, Helvetica, sans-serif;
        box-sizing: border-box;
    }

    button {
        font-size: 14px;
        font-weight: bold;
        margin: 2px;
        border-radius: 8px;
        background: #1e6c93;
        background-color: #1e6c93;
        display: inline-block;
        color: white;
        cursor: pointer;
        width: 42px;
        height: 42px;
        left: 50%;
        right: 50%;
        text-align: center;
        border: 0;
    }

    button:hover {
        background: #1e6c9369;
        color: black;
    }

    table {


        border: 0;
    }

    td {
        border: 0px;
        padding: .2em;
        vertical-align: top;
        text-align: left;
        background-color: #fff;

    }

    #song {

        font-weight: bold;
        background: #1e6c93;
        background-color: #1e6c93;
        color: white;
        padding: 10px;
        margin-top: 10px;
    }

    .column {
        float: left;
        width: 50%;
        padding: 10px;

    }


    .row:after {
        content: "";
        display: table;
        clear: both;
    }

    @media screen and (max-width: 600px) {
        .column {
            width: 100%;
        }

    }
</style>


<button onclick="songsButton()" style="width:70px" id="songsButton">Songs</button>


<p id="song" style="display:none"></p>
<p id="songTitle" style="display:none"></p>
<p id="lyrics" style="display:none"></p>
    <div class="row">
        <div class="column">

            <p id="menu"></p>
        </div>
        <div class="column">
            
            <p id="table" style="display:none">Loading...</p>
        </div>
    </div>

    <script>
        function selectSong(x) {
            document.getElementById("table").innerHTML = "";
            document.getElementById("songsButton").style.display = "block";
            document.getElementById("song").style.display = "block";
 document.getElementById("songTitle").style.display = "block";
            document.getElementById("table").style.display = "none";

            document.getElementById("song").innerHTML = "Song " + x;

            document.getElementById("menu").innerHTML = "";

            var xhttp = new XMLHttpRequest();
            xhttp.onreadystatechange = function() {
                if (this.readyState == 4 && this.status == 200) {
                    document.getElementById("songTitle").innerHTML = this.responseText;
                }
            };
            xhttp.open("GET", "https://docs.google.com/spreadsheets/d/1_u9G_RmtVx4fXMoweL37ZDnaalxdPI5YPY5zSr_QK74/gviz/tq?tqx=out:html&tq=select+B+where+A=" + x, true);
            xhttp.send();
            document.getElementById('songTitle').style.fontSize = "xx-large";


            var xhttp = new XMLHttpRequest();
            xhttp.onreadystatechange = function() {
                if (this.readyState == 4 && this.status == 200) {
                    document.getElementById("lyrics").innerHTML = this.responseText;
                }
            };
            xhttp.open("GET", "https://docs.google.com/spreadsheets/d/1_u9G_RmtVx4fXMoweL37ZDnaalxdPI5YPY5zSr_QK74/gviz/tq?gid=1181931951&tqx=out:html&tq=select+C+where+A=2", true);
            xhttp.send();
            document.getElementById("lyrics").style.display = "block";




        }

        function songsButton() {
            document.getElementById("table").innerHTML = "";
            document.getElementById("songTitle").innerHTML = "";
            document.getElementById("lyrics").innerHTML = "";
            document.getElementById("songsButton").style.display = "none";
            document.getElementById("song").style.display = "none";

            let i = 1;
            for (i; i <= 57; i++) {

                let myBtn = document.createElement("button");
                myBtn.innerHTML = i;
                myBtn.onclick = function() {
                    selectSong(myBtn.innerHTML);
                };
                menu.appendChild(myBtn);
            }

            var xhttp = new XMLHttpRequest();
            xhttp.onreadystatechange = function() {
                if (this.readyState == 4 && this.status == 200) {
                    document.getElementById("table").innerHTML = this.responseText;
                }
            };
            xhttp.open("GET", "https://docs.google.com/spreadsheets/d/1_u9G_RmtVx4fXMoweL37ZDnaalxdPI5YPY5zSr_QK74/gviz/tq?tqx=out:html", true);
            xhttp.send();
            document.getElementById("table").style.display = "block";





        }
    </script>

