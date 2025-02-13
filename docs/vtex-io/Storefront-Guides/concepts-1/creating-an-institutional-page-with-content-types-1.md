---
title: "Creating an institutional page with Content types"
slug: "creating-an-institutional-page-with-content-types-1"
hidden: false
createdAt: "2022-09-20T13:26:38.616Z"
updatedAt: "2022-09-23T19:41:16.408Z"
---

Content types are templates that structure your documents. They can be pages, publications, articles, events, products, and any other type of content that you want to insert into your project. You can also use them in the CMS to create an institutional page.

To create an institutional page, follow these tutorial.

1. Define the components of your page. In the example below, we use the `ww.vtex.com` page and its title, partners, highlights, and carousel components.

  ![](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/creating-an-institutional-page-with-content-types-1-0.png)

2. In the cms folder, go to the `content-types.json` file.

  ![](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/creating-an-institutional-page-with-content-types-1-1.png)

3. In the `content-type.json` file, create a new content type. To do this, define the following information:

- `id`: content type ID. It is recommended to have a lowercase pattern with no spaces, like with URLs.
- `name`: name that will be displayed on the page.
- `configurationSchemaSets`: extra blocks that will configure the page, such as menu settings and slug blocks, for example.

```json
{
  "id": "landing",
  "name": "Landing Page",
  "configurationSchemaSets": []
}
```

4. Determine the page sections in the `section.json` file. To define the sections, duplicate an existing one and edit it using the new names and descriptions that you want in your page.

```json
{
  “name” “Hero”,
  “schema”:  {
    “title” “Hero”,
    “description”: “Add a quick promotion with an image/action pair”,
    “type”: “object”,
    “properties”: {
      “title”: {
        “type”: “string”
      },
      “subtitle”: {
        “type”: “string”
      },
      “linkText”: {
        “type”: “string”,
        “title”: “Link text”
      },
      “link”: {
        “type”: “string”,
        “title”: “Link path”
      },
      “ImageSrc”: {
        “type”: “string”,
        “title”: “Image”,
        “widget”: {
          “ui:widget”: image-uploader
        },
        “Imagealt”: {
          “Type”: “string”,
          “title”: “Alt text”
        }
      }
    }
  }
}
```

> ℹ️️ These fields are the structure of your page. Complete them based on what was defined in step one of this tutorial.

5. After defining the sections, save them. If you want to view the draft, go to the repository for testing. 6. Go to the store to view the final version of your page.

## Learn More

- [Setting up the VTEX Headless CMS in your FastStore project](https://www.faststore.dev/tutorials/cms/2#step-2---syncing-your-changes)
- [Adding Content Types and Sections to the VTEX Headless CMS](https://www.faststore.dev/tutorials/cms/3)
- [Querying the CMS data](https://www.faststore.dev/tutorials/cms/4)
