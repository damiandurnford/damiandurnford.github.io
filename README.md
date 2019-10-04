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
