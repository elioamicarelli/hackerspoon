# [Hacker Spoon](https://third-mystic.github.io/hackerspoon/)

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
