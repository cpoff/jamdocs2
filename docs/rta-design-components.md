---
title: RTA Design Components
date: 2018-09-15T07:42:34.000+00:00
slug: rta-design-components
---

## Style guide

<img src="/RTAWebStyleGuide_v2_051420-1.jpg"><br>
<img src="/RTAWebStyleGuide_v2_051420-2.jpg">

## Layouts

![Homepage](/RTA_Wireframe_Homepage.jpg)
![Category page](/RTA_Wireframe_Category.jpg)
![Article/Post page](/RTA_Wireframe_ArticlePost.jpg)

Kristin will also produce and maintain all CSS assets in Generate Press:

[RTA master CSS](https://rtamobility.com/wp-content/themes/generatepress/style.css)<br>

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
