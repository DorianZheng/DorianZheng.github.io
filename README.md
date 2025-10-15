# DorianZheng.github.io

## Local Preview

To run the site locally for preview:

1. Ensure you have a recent Ruby installed (e.g., via Homebrew: `brew install ruby`) and that the Homebrew Ruby is on your `PATH`.
2. Install dependencies from the project root:
   ```bash
   bundle install
   ```
3. Start the Jekyll development server with live reload:
   ```bash
   bundle exec jekyll serve --livereload
   ```
4. Visit `http://127.0.0.1:4000/` (or the host/port shown in the terminal) to preview the blog. The server will rebuild automatically when files change.
5. Press `Ctrl+C` in the terminal to stop the server when you are done.

## Create a New Post

1. From the project root, run the Rake helper (replace the slug inside the quotes):
   ```bash
   bundle exec rake post["my-new-post"]
   ```
   This creates `_posts/YYYY-MM-DD-my-new-post.md`, copies the path to your clipboard, and stages the file.
2. Open the new file, update the front matter (title, tags, etc.), and add your content below the `---` delimiter.
3. Preview the change locally with the steps in the previous section, then commit and push when you are satisfied.

## Add Images

1. Save your image under `media/uploads/` (feel free to create subfolders such as `media/uploads/2025/` to stay organized) and add it to version control.
2. Reference the asset in Markdown using Jekyll’s `relative_url` filter so links work locally and after deployment:
   ```markdown
   ![Alt text]({{ "/media/uploads/example.jpg" | relative_url }})
   ```
3. Commit the image together with the post that uses it to avoid broken references.
