# Hacker Spoon

This is a simple website created to be hosted on GitHub Pages.

## How to add a new post

1.  Create a new HTML file in the `posts` directory. For example, `posts/post-title.html`.
2.  The new file should have the following structure:
    ```html
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Post Title</title>
        <link rel="stylesheet" href="../css/style.css">
    </head>
    <body>
        <header>
            <h1>hacker spoon</h1>
        </header>
        <main>
            <article>
                <h2>Post Title</h2>
                <img src="https://via.placeholder.com/300x200.png?text=Post+Image" alt="Post Image">
                <p>Full post content goes here.</p>
            </article>
        </main>
    </body>
    </html>
    ```
3.  Add a new post preview to the `index.html` file, inside the `posts-container` div. The preview should have the following structure:
    ```html
    <div class="post-preview">
        <img src="https://via.placeholder.com/300x200.png?text=Post+Image" alt="Post Image">
        <h2>Post Title</h2>
        <p>A 5-line description of the post.</p>
        <a href="posts/post-title.html">Read More</a>
    </div>
    ```

## How to run locally

Open the `index.html` file in your web browser.
