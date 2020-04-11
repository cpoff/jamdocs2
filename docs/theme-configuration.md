---
title: Design Toolkit
date: 2018-09-15T07:42:34.000+00:00
slug: toolkit

---
## Components
Since there is a bright and a dark theme in Jamdocs, you will need two logotypes. Just replace the two svg files in `src/assets/img` where the dark on is named `logo-dark.svg` and the bright one is named `logo-bright.svg`. If you can´t provide SVG logos, you can just change the file format to for example PNG in line 5 and 10 `src/components/Logo.vue`.

### Alert box
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
<p style="text-align: center;"><a href="/Default.aspx?tabid=84" target="_blank"><img alt="" src="/portals/0/images/MAGtool233.jpg" style="width: 200px;" /></a></p>

<p style="color:#000;text-align: center;"><b>Arizona Healthcare Assets Map</b>: A web-based, map viewer tool developed by Maricopa Association of Governments, PAG's peer organization in Phoenix, includes helpful COVID-19 data for our region.<br />
<strong><a class="alert-link" href="/Default.aspx?tabid=84" target="_blank">Read more &raquo;</a></strong></p>
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
require('typeface-open-sans')
```

Now you can go to line 12 in `src/assets/scss/globals.scss` and change that line to:

```scss
font-family: 'Open Sans', sans-serif;
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