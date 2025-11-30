# Mkdocs Feature Demo

The purpose of this document is to showcase additional Mkdocs functionality. You can see lots of functionality supported by Mkdocs which is particularly useful for developer docs. While many WYSIWYG content editors and CMS tools provide much of this functionality out of the box, developer-built environments in repositories with static site generators will still write their content like this. Each tool or content type comes with an additional section for integrating it into your own Mkdocs site.

!!! note

    This works on my device. I am using the latest version of Mkdocs Material, and will mention any necessary dependencies in this doc where possible. Of course, if you are still finding problems, don't hesitate to contact me and let me know. This page will also continue to see new additions as I discover them and integrate them into this webpage. Rome wasn't built in a day!

## Better Code Blocks

There are several additions to our code blocks we can make that improve their display and interactability.

### Color Coding

In order for code blocks to display with color-coded syntax, we need to tell Mkdocs what type of content we are writing in that table by adding it to our code block. In this example, we're adding color coding to an example of Python code like:

```py
print("Hello, World!")
```

This is written as:

````
```py
print("Hello, World!")
```
````

However, this also supports `html`, `css`, `yaml`, `json`, and other formats we may need to display. We will continue to use this method throughout the article with different formats to better demonstrate.

### Copy to Clipboard

You'll notice in the code blocks above, we can select an icon in the top right to copy the code to our clipboard. To enable this, add this to your `mkdocs.yml`:

```yaml
theme:
  features:
    - content.code.copy
```

### Adding Titles to Code Blocks

We've made some great additions to our code blocks, but now suppose we want to add more context to our code blocks so users know what they are supposed to be looking at. This can be useful for labeling API payloads by their response code, for example:

```py title="404: Not Found"
{
  "status": 404,
  "error": "Not Found",
  "message": "The requested resource was not found on this server.",
  "path": "/brett/fake-api"
}
```

A title can be added at the top of your code block by adding the correct syntax as specified in [Color Coding](#color-coding), followed by `title="Name of Code Block"`.

## Collapsible Tabs

<details>
    <summary>Here is a collapsible tab!</summary>
    Here is an example of content that is hidden within an interactable tab.
</details>

Collapsible tabs are an HTML element supported by Mkdocs Material by default. Collapsible tabs can be formatted in your article like:

```html title="Collapsible Tab Template"

<details>
    <summary>Using collapsible tabs</summary>
     Here is an example of content that is hidden within an interactable tab.
</details>

```

## Better Tables

Through a very basic plugin and some CSS, tables can be a little more pleasing to the eye. Add the following into your `mkdocs.yml` file under `markdown_extensions`:

    ```yaml
    markdown_extensions:
        tables
    ```

This will create a clean layout for your tables, and highlight table rows when you hover over them with your cursor.

### Example: Ingredients for Korean ground beef and rice recipe

| Ingredient | Amount |
|---|---|
| Ground beef | 1 lb |
| Garlic | 3 cloves |
| Brown sugar | 1/4 cup |
| Soy sauce | 1/4 cup |
| Sesame oil | 2 tsp |
| Ground ginger | 1/4 tsp |
| Red pepper flakes | 1/4 tsp |
| Pepper | 1/4 tsp |
| White rice | 2 cups |