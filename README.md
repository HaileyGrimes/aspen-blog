# Setup

[![Deploy To Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/HaileyGrimes/aspen-blog)

Run these in a terminal. You can open a terminal in VS Code with <kbd>CTRL+`</kbd>

```bash
npm install
npm start
```

## What does this stuff mean?

### package.json

List of npm commands. List of JavaScript packages needed. When we run `npm install`, npm looks at package.json for the list of stuff it needs to install.

### Folders

`src`

Folder where code be.

`src/assets/scss`

Folder where css styling be.

`src/util/site.json`

Site-wide settings

## How does Gatsby (React) work

In Gatsby, use `<Link to="">` instead of `<a href="">` for internal links.

Components are custom HTML tags.

```jsx
// Header component in components/header.js
const Header = ({ children }) => (
  <header
    className="site-header"
    sx={{
      bg: "siteColor",
    }}
  >
    {children}
  </header>
)

// All the tags inside of <Header> are its children
<Header>
  <Logo title={siteTitle} />
  <div sx={layoutStyle.nav}>
    <div sx={{ display: ["flex", "flex", "flex", "none"] }}>
      <Search searchIndex={siteSearchIndex.index} />
    </div>
    <Navigation />
  </div>
  <div sx={layoutStyle.appearance}>
    <Search searchIndex={siteSearchIndex.index} />
    <Theme />
  </div>
</Header>
```

Props are custom attributes

```jsx
// Defining what a Logo component is in components/logo.js
const Logo = props => (
  <div className="site-logo">
    <Link to="/">{props.title}</Link>
  </div>
)

// Creating a Logo component in components/layout.js with a title prop
<Logo title={siteTitle} />
```
