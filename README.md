# ryandowse.github.io
Personal broker website for Ryan Dowse — California licensed real estate and business broker specializing in cannabis M&A and commercial acquisitions.

## Add a new blog post

1. **Copy the template** to a new file in `blog/posts/`. Use a lowercase-hyphenated slug:
   ```bash
   cp _templates/post.html blog/posts/your-post-slug.html
   ```

2. **Fill in the placeholders** in the new file (find-and-replace each `{{...}}`):
   - `{{TITLE}}`, `{{SUBTITLE}}`, `{{DESCRIPTION}}`, `{{KEYWORDS}}`
   - `{{TAG}}` (e.g. `Cannabis M&amp;A · Regulatory`)
   - `{{SLUG}}` (filename without `.html`)
   - `{{DATE_ISO}}` (`YYYY-MM-DD`) and `{{DATE_DISPLAY}}` (`Month D, YYYY`)
   - `{{READ_TIME}}` (e.g. `5 min read`)
   - `{{FOOTER_LABEL}}`, `{{CTA_LINE_1}}`, `{{CTA_LINE_2_LEAD}}`, `{{CTA_LINE_2_ACCENT}}`

3. **Write the body** inside `<div class="post-body">`. Delete any structural blocks (pull-quote, callout, data table, list) you don't need.

4. **Add the card** to `blog/index.html`. Paste this at the top of `<div class="posts-grid" id="postsGrid">` (newest first), and remove the bottom-most `<!-- PLACEHOLDER -->` block so the grid stays balanced:
   ```html
   <!-- POST N — published -->
   <div class="post-card">
     <a href="/blog/posts/your-post-slug.html">
       <div class="post-tag">Your Tag · Subtag</div>
       <div class="post-title">Your Full Title Here</div>
       <p class="post-excerpt">One- or two-sentence hook. Match the energy of the existing cards.</p>
       <div class="post-meta">
         <div class="post-date">Mon D, YYYY</div>
         <div class="post-read">5 min read &#8594;</div>
       </div>
     </a>
   </div>
   ```

5. **Preview locally** (optional). From the repo root:
   ```bash
   python3 -m http.server 8000
   ```
   Then open http://localhost:8000/blog/ in a browser.

6. **Push live:**
   ```bash
   git add blog/posts/your-post-slug.html blog/index.html
   git commit -m "Add post: your post title"
   git push
   ```
   GitHub Pages auto-deploys within ~1 minute.

### Notes
- `_templates/` is ignored by GitHub Pages' Jekyll build (leading underscore), so the template file won't be published.
- HTML-escape ampersands in any user-visible text: write `&amp;` not `&`.
- Keep three posts visible on the grid at any time (mix of real cards + "Coming Soon" placeholders) so the 3-column layout stays full on desktop.
