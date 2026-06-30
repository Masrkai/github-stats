go read [this file](./parameters.md) first, but here are a few typical ways you would run this program depending on what you want to achieve:

### 1. The Standard Run (Fetch and Generate)

This is the most common use case. You pass your GitHub token, and it automatically fetches your data, generates the default `overview.svg` and `languages.svg` files, and prints informational logs.

```bash
./github-stats --access_token "your_github_pat_here"
```

### 2. The Cached Run (Faster & Saves API Quota)

If you want to tweak your SVG templates or filtering options without hitting GitHub's API rate limits every single time, you can fetch and save the data to a JSON file first:

**Step 1: Fetch and save data**

```bash
./github-stats --access_token "your_github_pat_here" --json_output_file stats.json
```

**Step 2: Generate SVGs locally from the saved JSON**

```bash
./github-stats --json_input_file stats.json
```

---

### 3. Advanced Filtering & Custom Outputs

If you want to hide private repositories, filter out specific projects, and change where the final images are saved, a typical command looks like this:

```bash
./github-stats \
  --json_input_file stats.json \
  --exclude_private true \
  --exclude_repos "dotfiles,test-repo,demo-*" \
  --overview_output_file "images/my-overview.svg" \
  --languages_output_file "images/my-languages.svg"
```

---

### 4. Customizing Templates

If you don't like the look of the default SVGs, you can dump the built-in templates, modify them, and feed them back into the program:

```bash
# 1. Export the default templates
./github-stats --dump_overview_template custom_template.svg

# 2. Run the program using your modified template
./github-stats --json_input_file stats.json --overview_template custom_template.svg
```