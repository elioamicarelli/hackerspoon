# Hacker Spoon

A simple, minimalist blog created with vanilla JavaScript and hosted on GitHub Pages. This project uses a single-page application (SPA) architecture, dynamically loading and rendering post content from Markdown files.

## Tech Stack

*   **Frontend:** Vanilla JavaScript, HTML5, CSS3
*   **Content:** Markdown files with YAML front matter
*   **Libraries:**
    *   [marked.js](https://marked.js.org/) for parsing Markdown
    *   [js-yaml](https://github.com/nodeca/js-yaml) for parsing YAML front matter

## How to add a new post

1.  **Create a new Markdown file:**
    Add a new file to the `md_posts/` directory (e.g., `post5.md`).

2.  **Add content to your Markdown file:**
    The file must start with a YAML front matter section. The front matter needs to include a `title` and an `image` path for the post's content page.

    ```markdown
    ---
    title: "Your New Post Title"
    image: "images/your_post_image.png"
    ---

    This is the full content of your new post. You can use Markdown here.
    ```

3.  **Update the posts list:**
    Add a new JSON object to the `posts.json` file to make your post appear on the homepage. The object should include:
    *   `title`: The title of your post.
    *   `preview_image`: The path to the image that will be shown in the post preview on the homepage.
    *   `description`: A short description for the post preview.
    *   `markdown_file`: The name of the Markdown file you created in step 1.

    Example entry in `posts.json`:
    ```json
    {
        "title": "Your New Post Title",
        "preview_image": "images/your_preview_image.png",
        "description": "A short and catchy description for the homepage.",
        "markdown_file": "post5.md"
    }
    ```

## How to run locally

Because this project uses `fetch` to load local files, you need to run it through a local web server. Simply opening `index.html` in your browser will not work due to CORS security restrictions.

A simple way to start a local server is to use Python's built-in HTTP server.

1.  Open your terminal in the project's root directory.
2.  Run the following command:

    ```bash
    python3 -m http.server
    ```
    (If you are using Python 2, the command is `python -m SimpleHTTPServer`).

3.  Open your web browser and navigate to `http://localhost:8000`.

## Deployment

This website is configured to be deployed on GitHub Pages.

A crucial step for the deployment to work correctly is the presence of an empty file named `.nojekyll` in the root of the repository. This file tells GitHub Pages to not process the site with Jekyll, which is the default behavior. Without `.nojekyll`, GitHub Pages might not serve the Markdown files in the `md_posts` directory correctly, leading to 404 errors.