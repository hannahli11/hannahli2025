# Hannah Li – AP Computer Science Principles (2025)

Welcome to my personal GitHub repository for the 2025 AP Computer Science Principles (CSP) course. This site contains my notebooks, blogs, and projects developed throughout the year using tools like Python, JavaScript, HTML/CSS, and Jupyter.

The repository is organized using Jekyll and GitHub Pages to create a public-facing, interactive portfolio of my learning journey in computer science.

---
### 💡 Ways to Share and Collaborate

1. Share `.ipynb` files using raw links  
2. Use this template as your personal base  
3. Fork/clone to work on group projects  
4. Blog regularly to document development  

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

- ✍️ Notebooks and markdown-based blog posts  
- 🕹️ Interactive biotech-themed games  
- 🎨 Tailwind-based frontend UI design  
- 🔌 Gemini AI API for trivia generation  
- 🚀 GitHub Actions for continuous deployment  
- 📂 Organized layout for lessons and topics  

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
---

**## 🔧 Tool Requirements**

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

## 🍎 macOS Activation

```bash
./activate_macos.sh

## 🛠️ Run Server on Localhost

### 🔁 One-Time Bundle Install

To install project dependencies:

```bash
bundle install

## ▶️ Start Jekyll Server

### To start the Jekyll server:

```bash
make

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

To hide a post from site search results:

search_exclude: true

## 🧭 Navigation Bar Configuration

### To customize the navbar, edit nav/home.html:

navbar:

```html
<td><a href="{{site.baseurl}}/newpage" style="color: purple;">New Page</a></td>

## 🖼️ Blog Images and Metadata

### To include metadata and images in the front matter of your blog post:

```yaml
image: /images/dna-quiz.png
title: "DNA Game Project"
description: "Base pair logic, quiz modal, and visual design"

## 🎨 Themes and Layouts
### Set the layout of a post:

```yaml
layout: post

Customize styles using:

```bash
_sass/minima/custom-styles.scss

Create or edit page layouts in:

```bash
_layouts/

## 🔁 Includes and Liquid Syntax
### To dynamically include a list of posts:

```liquid
{% include post_list.html %}

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
## 📋 Front Matter Field Reference

| Field     | Purpose                                      |
|-----------|----------------------------------------------|
| `title`   | Display name of the post                     |
| `layout`  | Layout style (e.g., `post`, `notebook`)      |
| `toc`     | Enables Table of Contents                    |
| `comments`| Enables comment section                      |
| `courses` | Organizes post by course/week               |
| `type`    | Optional custom tag (e.g., `ccc`)            |



