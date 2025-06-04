# Hannah Li – AP Computer Science Principles (2025)

Welcome to my personal GitHub repository for the 2025 AP Computer Science Principles (CSP) course. This site contains my notebooks, blogs, and projects developed throughout the year using tools like Python, JavaScript, HTML/CSS, and Jupyter.

The repository is organized using Jekyll and GitHub Pages to create a public-facing, interactive portfolio of my learning journey in computer science.

---
### Next Steps

1. Make design cleaner
2. Fix errors in features
3. Organize all notebooks in blogs
4. Update everything

---

## 🕰️ History

This project is based on the third generation of Nighthawk Pages and uses:

- Jupyter Notebooks  
- GitHub Actions for auto-deployment  
- Makefiles for automation  
- Tailwind CSS for styling  
- Markdown + Liquid for blog content  

---

## 📄 License

This project is distributed under the MIT License. You're free to reuse and adapt this content for educational purposes.

---

## ⚙️ Key Features

- Notebooks and markdown-based blog posts  
- GitHub Actions for continuous deployment  
- Organized layout for homeworks and blogs
- Fun features in navbar

---

## 🤝 Contributions

Although this is an individual portfolio, many features support collaborative work:

- UI improvements and design templates  
- Backend logic integrations  
- Blog writing and development documentation  
- Support for teammates and shared projects  

---

## 🌐 GitHub Pages Setup

To deploy the site:

1. Navigate to `Settings > Pages`  
2. Choose `GitHub Actions` as your deployment method  
3. In `_config.yml`, update the following:

```yaml
github_repo: "hannahli2025"
baseurl: "/hannahli2025"
```

---

## 🔧 Tool Requirements

- **Jekyll** – Static site generator that converts notebooks to blogs  
- **VSCode** – Editor for markdown, Python, and HTML  
- **nbconvert** – Converts `.ipynb` to markdown  
- **Mac/Linux Terminal** – To run the Makefile and scripts  
- **Git/GitHub CLI** – For version control and pushing changes  

---

## 💻 Development Environment Setup

### 📥 Clone Repository

```bash
git clone https://github.com/hannahli2025/hannahli2025.git
cd hannahli2025/scripts
```


## 🍎 macOS Activation

```bash
./activate_macos.sh
```

## 🛠️ Run Server on Localhost

### 🔁 One-Time Bundle Install

To install project dependencies:

```bash
bundle install
```

## ▶️ Start Jekyll Server

### To start the Jekyll server:

```bash
make
```
## Development Support

### File Names in "_posts", "_notebooks"

There are two primary directories for creating blogs.  The "_posts" directory is for authoring in markdown only.  The "_notebooks" allows for markdown, pythons, javascript and more.

To name a file, use the following structure (If dates are in the future, review your config.yml setting if you want them to be viewed).  Review these naming conventions.

- For markdown files in _posts:
  - year-month-day-fileName.md
    - GOOD EXAMPLE: 2021-08-02-First-Day.md
    - BAD EXAMPLE: 2021-8-2-first-day.md
    - BAD EXAMPLE: first-day.md
    - BAD EXAMPLE: 2069-12-31-First-Day.md

- For Jupyter notebooks in _notebooks:
  - year-month-day-fileName.ipynb
    - GOOD EXAMPLE: 2021-08-02-First-Day.ipynb
    - BAD EXAMPLE: 2021-8-2-first-day.ipynb
    - BAD EXAMPLE: first-day.ipynb
    - BAD EXAMPLE: 2069-12-31-First-Day.ipynb
      
### Tags

Tags are used to organize pages by their tag the way to add tags is to add the following to your front matter such as the example seen here `categories: [Tools]` Each item in the same category will be lumped together to be seen easily on the search page.

### Search

All pages can be searched for using the built-in search bar. This search bar will search for any word in the title of a page or in the page itself. This allows for easily finding pages and information that you are looking for. However, sometimes this may not be desirable so to hide a page from the search you need to add `search_exclude: true` to the front matter of the page. This will hide the page from appearing when the viewer uses search.

### Navigation Bar

To add pages to the top navigation bar use _config.yml to order and determine which menus you want and how to order them.  Review the_config.yml in this project for an example.

### Blog Page

There is a blog page that has options for images and a description of the page. This page can help the viewer understand what the page is about and what they can expect to find on the page. The way to add images to a page is to have the following front matter `image: /images/file.jpg` and then the name of the image that you want to use. The image must be in the `images` folder. Furthermore, if you would like the file to not show up on the blog page `hide: true` can be added to the front matter.

### SASS support

NIGHTHAWK Pages support a variety of different themes that are each overlaid on top of minima. To use each theme, go to the "_sass/minima/custom-styles.scss" file and simply comment or uncomment the theme you want to use.

To learn about the minima themes search for "GitHub Pages minima" and review the README.

To find a new theme search for "GitHub Pages Themes".

### Includes

- Nighthawk Pages uses liquid syntax to import many common page elements that are present throughout the repository. These common elements are imported from the _includes directory. If you want to add one of these common elements, use liquid syntax to import the desired element to your file. Here’s an example of the liquid syntax used to import: `{%- include post_list.html -%}` Note that the liquid syntax is surrounded by curly braces and percent signs. This can be used anywhere in the repository.

### Layouts

- To use or create a custom page layout, make an HTML page inside the _layouts directory, and when you want to use that layout in a file, use the following front matter `layout: [your layout here]`.  All layouts will be written in liquid to define the structure of the page.

## 🧼 Other Commands

Useful Makefile commands for local development:

| Action            | Command       |
|-------------------|---------------|
| Stop Server       | `make stop`   |
| Clean Build       | `make clean`  |
| Convert Notebooks | `make convert`|

## 🗂️ Development Support & Structure

### 🗃️ File Naming Format

File naming for consistency:

- **Blog Posts:** `_posts/2025-05-10-my-title.md`  
- **Notebooks:** `_notebooks/2025-05-10-my-notebook.ipynb`

✅ Use real dates  
🚫 Don't use future dates or special characters in filenames

## 🏷️ Tags and Categories

To add categories in your Markdown post’s front matter:

```yaml
categories: [Tools]
```

To hide a post from site search results:

search_exclude: true

## 🧭 Navigation Bar Configuration

### To customize the navbar, edit nav/home.html:

navbar:

```html
<td><a href="{{site.baseurl}}/newpage" style="color: purple;">New Page</a></td>
```

## 🖼️ Blog Images and Metadata

### To include metadata and images in the front matter of your blog post:

```yaml
image: /images/dna-quiz.png
title: "DNA Game Project"
description: "Base pair logic, quiz modal, and visual design"
```

## 🎨 Themes and Layouts
### Set the layout of a post:

```yaml
layout: post
```

Customize styles using:

```bash
_sass/minima/custom-styles.scss
```

Create or edit page layouts in:

```bash
_layouts/
```

## 🔁 Includes and Liquid Syntax
### To dynamically include a list of posts:

```liquid
{% include post_list.html %}
```

This pulls in reusable or dynamic content like blog previews or navigation items.

## 🧾 Metadata in Posts
### Example front matter block for a CSP blog post:

```yaml
---
title: "Final Blog"
layout: post
toc: true
comments: true
courses: { csp: {week: 5} }
type: ccc
---
```
## 📋 Front Matter Field Reference

| Field     | Purpose                                      |
|-----------|----------------------------------------------|
| `title`   | Display name of the post                     |
| `layout`  | Layout style (e.g., `post`, `notebook`)      |
| `toc`     | Enables Table of Contents                    |
| `comments`| Enables comment section                      |
| `courses` | Organizes post by course/week               |
| `type`    | Optional custom tag (e.g., `ccc`)            |



