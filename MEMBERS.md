# Hugo Theme - Skye

For each member of the site create a file (usually called <firstname><lastname>.toml) under the data\members folder. See below for the configuration of this file.

## Members Configuration

### name

A string containing the name to display for the member. Note that this must match the `author` frontmatter for the post.

```toml
name = "Paul Broadwith"
```

### img

An image of the member to display. Note that this image should be 90px x 90px.

```toml
img = "/images/members/paulbroadwith-90x90.jpg"
```

### position

The authors current title or position. Not currently displayed.

```toml
position = "IT Guru"
```

### Social Icons

See [social icons](https://github.com/pauby/hugo-theme-skye/blob/master/CONFIGURATION.md#social-icons---paramssocial) for details of what you can use here.

### website

URL of a website for the author. This will be displayed with the 'Home' icon.

```toml
website = "https://pauby.com"
```

### bio

A description or bio of the author.

```toml
bio = """Paul is a Senior Technology Engineer with 25 years experience in finance, government, manufacturing and services industries. He is a father, Microsoft professional, coder and loves to automate everything."""
```