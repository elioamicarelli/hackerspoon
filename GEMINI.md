# HackerSpoon Website Documentation

This document outlines the structure of the HackerSpoon website and provides instructions for adding new content.

## Website Structure

The website is a **Single-Page Application (SPA)**. The main entry point is `index.html`, which contains all the necessary HTML, CSS, and JavaScript to dynamically load and display content.

- **`index.html`**: The core of the website. It contains a client-side router that reads the URL hash (`#`) to determine which content to display.
- **`css/style.css`**: The main stylesheet for the website.
- **`images/`**: Contains all image assets.
- **`posts.json`**: A JSON file that defines the content cards displayed on the homepage.
- **`md_posts/`**: Contains the markdown files for internal articles linked from the homepage.
- **`notebook/`**: A directory for personal notes and articles.
  - **`notes/`**: Contains the markdown files for individual notes.
  - **`data.json`**: A JSON file that lists all the notes in the `notes/` directory, including their titles, file paths, dates, and hashtags. This file populates the "Notes" page (`index.html#notes`).

## How to Add Content

### Adding a Post to the Main Page

The main page displays a list of projects or articles defined in `posts.json`.

1.  **Update `posts.json`**:
    Open the `posts.json` file and add a new JSON object to the array. The object should have the following structure:
    ```json
    {
        "title": "Your Post Title",
        "preview_image": "images/your-preview-image.png",
        "description": "A short description of your post.",
        "link_type": "external",
        "link_target": "https://example.com"
    }
    ```
    - `title`: The title of the post.
    - `preview_image`: The path to the preview image in the `images/` directory.
    - `description`: A brief summary of the post.
    - `link_type`: Can be `"external"` or `"markdown"`.
      - Use `"external"` for links to other websites.
      - Use `"markdown"` to link to a local markdown file.
    - `link_target`: The URL for an external link, or the filename of the markdown file for an internal post (e.g., `"my-post.md"`).

2.  **(If applicable) Create the Markdown File**:
    If you set `link_type` to `"markdown"`, create a new markdown file in the `md_posts/` directory. The filename should match the `link_target` you specified.

### Adding a Note to the Notebook

The "Notes" page (`index.html#notes`) displays a list of notes from the `notebook/` directory.

1.  **Create the Markdown File**:
    Create a new markdown file inside the `notebook/notes/` directory (e.g., `my-new-note.md`). Write your content in this file.

2.  **Update `notebook/data.json`**:
    Open the `notebook/data.json` file and add a new JSON object to the `articles` array. This object tells the website about your new note.
    ```json
    {
      "title": "My New Note Title",
      "file": "notes/my-new-note.md",
      "date": "YYYY-MM-DD",
      "hashtags": ["tag1", "tag2"]
    }
    ```
    - `title`: The title of your note, which will be displayed in the list.
    - `file`: The path to your new markdown file, relative to the `notebook/` directory.
    - `date`: The publication date.
    - `hashtags`: An array of relevant tags for your note.
