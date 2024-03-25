# Building and Deploying a Jekyll Site to GitHub Pages

This guide outlines the workflow for building and deploying a Jekyll site to GitHub Pages, designed for the Pero's Academy's faculty and technical team.

![Setting up a GitHub Pages site with Jekyll](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/70570770-1152-4fba-8821-0cbe1fafd651)


## Workflow Overview

The workflow is designed to trigger on two occasions:

1. Automatically upon `push` events to the `main` branch.
2. Manually via `workflow_dispatch` for greater control.

The workflow manages permissions to read the repository content, write to GitHub Pages, and handle secure deployment.

![actions-workflow runs](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/6bcc8141-6e8b-4026-aea9-2b54a71f7bf7)


### Build Job

```yaml
runs-on: ubuntu-latest
steps:
  - name: Checkout
    uses: actions/checkout@v4
  - name: Setup Pages
    uses: actions/configure-pages@v4
  - name: Build with Jekyll
    uses: actions/jekyll-build-pages@v1
    with:
      source: ./
      destination: ./_site
  - name: Upload artifact
    uses: actions/upload-pages-artifact@v3
```

### Deployment Job

```yaml
runs-on: ubuntu-latest
needs: build
steps:
  - name: Deploy to GitHub Pages
    uses: actions/deploy-pages@v4
```

**Please Note**: The YAML configuration should be placed in a file named `.github/workflows/jekyll-gh-pages.yml` within your Jekyll project repository.

## Resources and Learning Materials

For members new to Jekyll or GitHub Pages, or those looking to sharpen their skills, the following resources can be highly beneficial.

### Official Documentation

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)

### Tutorials

- [Jekyll Step-by-Step Tutorial](https://jekyllrb.com/tutorials/home/)
- [GitHub Learning Lab](https://lab.github.com/courses)

### Video Tutorials

- [Jekyll YouTube Playlist](https://www.youtube.com/playlist?list=PLm_Qt4aKpfKgQZuLJ7fMOeJfZ8h9oRVbG)
- [GitHub Pages Workshop](https://www.youtube.com/watch?v=2MsN8gpT6jY)

### Community and Support

- [Jekyll Talk](https://talk.jekyllrb.com/) - The Jekyll community forum.
- [GitHub Community](https://github.community/) - A place to learn and engage about GitHub practices.
- [Stack Overflow](https://stackoverflow.com/questions/tagged/jekyll) - Tagged questions related to Jekyll.
- [GitHub Support](https://support.github.com/) - For issues specifically related to GitHub Pages hosting and services.

### Advanced Topics

- [Customizing GitHub Pages](https://docs.github.com/en/pages/customizing-your-github-pages-site)
- [Securing your GitHub Pages site with HTTPS](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/securing-your-github-pages-site-with-https)
- [Jekyll Themes](https://jekyllrb.com/docs/themes/)

By exploring these resources, members of Pero's Academy can expand their knowledge on website building, version control, and site deployment, leading to enriched course content and collaborative opportunities.

---

To create a section that contains steps for setting up a GitHub Pages site with Jekyll, along with enhancing the existing document to provide additional information, tutorials, and learning materials, you can follow the structure below. This structure is formatted in Markdown and suitable for a `README.md` file or a documentation page on GitHub.

---

# Comprehensive Guide for Curriculum Proposal Submissions at Pero's Academy

## Introduction
This guide is designed to help faculty members and collaborators at Pero's Academy navigate the curriculum proposal submission process using GitHub. We utilize GitHub to foster a collaborative environment where innovation in educational content can thrive.

## Curriculum Proposal Submission Workflow
The workflow for submitting curriculum proposals is streamlined through our GitHub repository to encourage active participation and structured submissions.

### Prerequisites
Before submitting a curriculum proposal, ensure you have the following:
- A GitHub account with admin permissions for the repository.
- Jekyll and Git installed on your local machine. [See Jekyll Installation Guide](https://jekyllrb.com/docs/installation/)
- Bundler installed to manage Ruby gem dependencies. [See Bundler Documentation](https://bundler.io/)

### Steps for Creating a GitHub Pages Site with Jekyll

#### Creating a Repository for Your Site
1. Create or choose an existing repository for your site on GitHub.
2. If using a new repository, initialize it with a `README`, `.gitignore`, and license as appropriate.

#### Creating Your Site
1. Clone your repository to your local machine and navigate to it.
2. Run `jekyll new --skip-bundle .` in your repo directory to create a new Jekyll site.
3. Modify the `Gemfile` to use the `github-pages` gem for Jekyll, ensuring you use the latest version compatible with GitHub Pages.
4. Run `bundle install` to install dependencies.

#### Testing Your Site Locally
1. Run `bundle exec jekyll serve` to build and test your site locally.
2. Visit `http://localhost:4000` to view your site.

#### Deploying Your Site
1. Commit and push your changes to your GitHub repository.
2. Set up GitHub Pages in your repository settings and choose the correct publishing source.
3. Visit your site at `http(s)://<username>.github.io/<repository>`.

![Setting up a GitHub Pages site with Jekyll](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/343e6ab9-6603-4f3c-9132-553e6d119a74)

#### Additional Steps
- Add content, customize themes, and set up custom domains as desired.
- Refer to GitHub's official documentation on [Creating a GitHub Pages site with Jekyll](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll) for detailed instructions.

### Visual Aids
Include screenshots from the submission process to guide users through each step visually.

---

## Enhancing Curriculum Proposals

### Resources for Learning Jekyll and GitHub Pages
- [Jekyll's Official Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/pages)
- [YouTube: Jekyll Tutorials Playlist](https://www.youtube.com/playlist?list=PLm_Qt4aKpfKgQZuLJ7fMOeJfZ8h9oRVbG)
- [Testing Jekyll Sites Locally](https://jekyllrb.com/docs/)

### Tutorials and Community Support
- [Jekyll Quickstart Guide](https://jekyllrb.com/docs/)
- [GitHub Community Forum](https://github.community/)
- [Stack Overflow: Jekyll Questions](https://stackoverflow.com/questions/tagged/jekyll)

### Continuous Learning
- Subscribe to [Jekyll's Newsletter](https://jekyllrb.com/news/)
- Engage with [GitHub Training and Guides](https://lab.github.com/)
- Attend workshops and webinars focused on Jekyll and GitHub Pages.

---

## Conclusion
At Pero's Academy, we are committed to providing an exceptional learning experience. By leveraging GitHub, we create a platform for innovation that allows us to continuously evolve our curriculum in line with the latest educational standards and technological advancements.

For any questions or additional support, reach out to the contacts provided or use the community forums for assistance.

---

# Raydo's Contribution

Creating a comprehensive documentation that integrates the provided screenshots and thoroughly explains the concept and process of curriculum proposal submissions at Pero's Academy involves several steps. Since I can't directly use or display the screenshots, I'll guide you on where to place them in your documentation.

## Title: Curriculum Proposal Submission Guide for Pero's Academy

---

## Introduction
This guide is crafted for the faculty members at Pero's Academy, detailing the process for submitting innovative curriculum proposals through our GitHub repository. The process fosters collaboration, transparency, and organization, ensuring that every proposal is thoroughly reviewed and considered.

## GitHub Repository and Project Boards
Our GitHub repository serves as the central hub for all curriculum-related activities. Here, faculty members can submit proposals, track progress, and collaborate on course development.

### Using the GitHub Project Boards
The GitHub Project Boards allow us to visualize and manage the workflow of curriculum development.

![projects](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/b793e174-8833-417c-8808-daff7db29277)

### Viewing Open Curriculum Proposals
Faculty can view open proposals within the GitHub Project Boards, offering an overview of ongoing work.

![protects example](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/bae8749f-3879-4a8b-826d-7383fb6ea09a)

## Curriculum Proposal Process

### Step 1: Accessing the Submission Template
To maintain a standard for submissions, we use a predefined template.

![issue template](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/4ff7d73e-6fa3-4a1c-ba72-6e926281e08d)


### Step 2: Submitting a New Course Proposal
Faculty members can start a new course proposal by creating a new issue in the GitHub repository.

1. Navigate to the **Issues** tab in the repository.
2. Click on **New Issue**.
3. Fill out the provided **Curriculum Proposal Template** with the necessary details of your course.

![issues](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/a6b88db8-cdad-4983-82e1-150b7e6a6b78)


## Completing the Proposal Template
The template ensures all proposals include essential information, facilitating an efficient review process.

**Fields to complete**:
- Course Title
- Course Description
- Learning Objectives
- Target Audience
- Syllabus Outline
- Assessment Methods
- Tools & Resources
  
![issue template](https://github.com/Pero-s-Academy/Curriculum-Proposals/assets/126121348/33f9456a-3eb2-474f-88a7-ddcdc35b8fe0)

### Tagging Your Submission
Utilize the appropriate tags to help categorize your proposal. This aids in the sorting and prioritization process.

**Tags include**:
- `New-Course-Proposal`
- `Course-Update`
- `Urgent`
- `Technology-Focused`
- `Skill-Development`

## Review and Collaboration
Once submitted, proposals enter the review stage. Here, faculty members and the curriculum development team can collaborate, offering feedback and suggestions.

**Key points**:
- Constructive feedback and discussions are encouraged on each issue.
- Proposals can be refined and updated based on the collaborative input.

## Conclusion
Submitting a curriculum proposal is a significant step toward contributing to the educational journey of our students at Pero's Academy. Our structured approach on GitHub streamlines the process and ensures that each proposal receives the attention it deserves.

---

This guide outlines the workflow for curriculum proposal submissions at Pero's Academy, integrating a visual component with screenshots for clarity. Faculty members are encouraged to reference this guide throughout the submission process to ensure their proposals are complete and align with the Academy's standards for educational excellence.
