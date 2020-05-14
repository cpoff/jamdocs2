---
title: Design Components
date: 2018-09-15T07:42:34.000+00:00
slug: design-components
---

## Style guide

![Approved - 5/14/20](/RTA_Style_Guide_v2_051420.jpg)

## Layouts

![Homepage](/RTA_Wireframe_Homepage.jpg)
![Category page](/RTA_Wireframe_Category.jpg)
![Article/Post page](/RTA_Wireframe_ArticlePost.jpg)

Kristin will also produce these CSS assets in Generate Press:

[RTA Main](http://rtamain.pagrtahost.kinsta.cloud/wp-content/themes/generatepress/style.css)<br>
[RTA Next](http://rtanext.pagrtahost.kinsta.cloud/wp-content/themes/generatepress/style.css)

Several base styles are also controlled via GP's Customize controls.

## Components

Curt will produce the HTML assets that the CSS will style. The CSS code for each of those components will be housed in this section. The Alert Module entry coming up next - and the rest of the placeholder text here - is a reflection of how this will be displayed on this site.

### Alert module

```html
<div id="alertModule">
  <style type="text/css">
    .alertRed {
      padding: 8px 15px 8px 14px;
      margin-bottom: 18px;
      color: #000000;
      background-color: #fff;
      border: 0px;
      -webkit-border-radius: 4px;
      -moz-border-radius: 4px;
      border-radius: 4px;
    }

    .alertRed .alert-link {
      color: blue;
    }

    .alertRed-heading {
      color: inherit;
    }
  </style>

  <div class="alertRed">
    <p style="text-align: center;">
      <a href="URL" target="_blank"
        ><img alt="" src="URL" style="width: 200px;"
      /></a>
    </p>

    <p style="color:#000;text-align: center;">
      CAPTION<br />
      <strong
        ><a class="alert-link" href="URL" target="_blank"
          >Read more &raquo;</a
        ></strong
      >
    </p>
  </div>
</div>
```

## Adding icons

If you need to use icons somewhere in the theme, you can use any icon from [Feather Icons](https://feathericons.com/) as a component. All that is needed is that you import the icon in the component you want to use it like i do it in the theme switcher component:

```javascript
import { MoonIcon, SunIcon } from 'vue-feather-icons'

export default {
  components: {
    MoonIcon,
    SunIcon
  },
...
```

And then the icon can be used like this:

```html
<sun-icon class="sun" />
```

## Changing colors

To change the theme colors you need to edit the file `src/assets/scss/config/_colors.scss`. When you open the file for the first time it will look like this:

```scss
// Dark theme
$backgroundDark: #18191a;
$sidebarDark: #2a2c2f;
$textDark: #fff;

// Bright theme
$backgroundBright: #fff;
$sidebarBright: #f3f4f5;
$textBright: #2a2c2f;

// Brand
$brandPrimary: #10c186;
```

## Changing font

Jamdocs uses Source Sans Pro by default. I chose to embed the font in the project to increase page speed. To change the font, you just install another Google Font as a dependency, lets say you want Open Sans:

```bash
yarn add typeface-open-sans
```

Then, on line 7 in `src/main.js` you change the line to:

```javascript
require("typeface-open-sans");
```

Now you can go to line 12 in `src/assets/scss/globals.scss` and change that line to:

```scss
font-family: "Open Sans", sans-serif;
```

You're done!

## Edit the sidebar

To edit the sidebar, open the file `data/settings.json`. In this file you will find global theme settings as objects and arrays. The sidebar is edit by adding an sections. A section object looks like this:

```json
{
  "section": "Introduction",
  "topics": [
    {
      "title": "Getting started",
      "slug": "getting-started"
    }
  ]
}
```

The section contains a name, in this case "Introduction", and following the name is an array called topics. Each topic resembles a markdown file in `docs` and contains the title you want that file to have in the sidebar, as well as the slug for routing.

For each topic the markdown is scanned for h2 headings, which is added as anchor links right below the topic in the sidebar.
