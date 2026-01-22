# Project Overview

This is a simple, static website that serves as a personal blog or a collection of notes. The main page (`index.html`) dynamically loads a list of articles from a `data.json` file. The articles themselves are written in Markdown and stored in the `notes/` directory. When a user clicks on an article link, the content is fetched and rendered into the `note.html` page using the `marked` JavaScript library.

The website has a retro, "hacker terminal" aesthetic, with a black background and green text.

# Key Files

*   **`index.html`**: The main entry point of the website. It contains the logic for fetching and displaying the list of articles from `data.json`.
*   **`note.html`**: The template for displaying individual articles. It uses the `marked` library to render Markdown content passed in the URL.
*   **`style.css`**: The stylesheet for the website, which gives it its "hacker terminal" look.
*   **`data.json`**: A JSON file that contains the metadata for all the articles, including the title, file path, date, and hashtags.
*   **`notes/`**: A directory containing the individual articles as Markdown files.
*   **`hashtag.html`**: A page that displays all the articles associated with a specific hashtag.

# Building and Running

This is a static website and does not require a build process. To run the website, you can open the `index.html` file in your web browser. However, due to the use of `fetch` to load local files, you will need to serve the files using a local web server to avoid CORS errors.

You can use the following Python command to start a simple web server in the project directory:

```bash
python -m http.server
```

Once the server is running, you can access the website at `http://localhost:8000`.

# Development Conventions

*   **Adding a new article**: To add a new article, create a new Markdown file in the `notes/` directory and add a corresponding entry to the `data.json` file.
*   **Styling**: All styling is done in the `style.css` file. The website uses a simple, single-stylesheet approach.
*   **JavaScript**: The website uses vanilla JavaScript for all its dynamic functionality.

# How to Publish a Note

To publish a new note and make it appear on the website with categories, follow these steps:

1.  **Create a new Markdown file**:
    *   In the `notes/` directory, create a new Markdown file (e.g., `my-third-note.md`).
    *   Add your note's content in Markdown format to this file.

2.  **Update `data.json`**:
    *   Open the `data.json` file in the root directory.
    *   Add a new entry to the `articles` array with the following structure:

    ```json
    {
      "title": "My Third Note",
      "file": "notes/my-third-note.md",
      "date": "2024-01-03",
      "hashtags": ["new", "tutorial", "gemini"]
    }
    ```
    *   **`title`**: The title of your note, which will be displayed on the main page.
    *   **`file`**: The path to your Markdown file (e.g., `"notes/my-third-note.md"`).
    *   **`date`**: The publication date of your note in "YYYY-MM-DD" format.
    *   **`hashtags`**: An array of strings representing categories or tags for your note. These will appear as clickable links on the main page.

3.  **Verify your changes**:
    *   Ensure your local web server is running (`python -m http.server`).
    *   Open `http://localhost:8000` in your browser. Your new note should now appear on the main page.
    *   Click on the new note to ensure it displays correctly.
    *   Click on the hashtags to see the (upcoming) hashtag functionality.

4.  **Publish to GitHub Pages (if applicable)**:
    *   If your website is hosted on GitHub Pages, commit your changes (`git add .`, `git commit -m "Add new note and update data.json"`) and push them to your GitHub repository (`git push origin main`). Your new note will then be live on your GitHub Pages site.