
# Personal Blog (Built with Hugo in Go, Deployed via GitHub Actions to AWS Amplify)

Welcome to the repository for my personal blog, a static site built using Hugo, a fast and flexible static site generator written in Go. This blog is hosted on AWS Amplify and automatically deployed using GitHub Actions for continuous deployment.

## Table of Contents

- About the Project
- Tech Stack
- Getting Started
  - Prerequisites
  - Installation
- Continuous Deployment with GitHub Actions
- Hosting on AWS Amplify
- Contributing
- License

## About the Project

This repository contains the source code for my personal blog, a lightweight and performant website generated with Hugo. The site leverages Hugo's capabilities to create a fast, SEO-friendly, and easy-to-maintain blog. The project is written in Go (via Hugo) and uses Markdown for content creation.

## Tech Stack

- **Hugo**: Static site generator written in Go.
- **AWS Amplify**: Hosting platform for the deployed website.
- **GitHub Actions**: CI/CD pipeline for continuous deployment.
- **Markdown**: For writing blog posts and content.
- **HTML/CSS/JavaScript**: For theming and front-end customization.

## Getting Started

### Prerequisites

To run this project locally, ensure you have the following installed:

- Hugo (Extended version recommended for SCSS support)
- Git
- Node.js (optional, for some Hugo themes or additional tooling)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/LeandroMileski/personal-blog.git
   cd personal-blog
   ```

2. Install Hugo dependencies (if any):

   ```bash
   hugo mod get -u
   ```

3. Run the Hugo development server:

   ```bash
   hugo server
   ```

4. Open your browser and navigate to `http://localhost:1313` to preview the site.

To build the static site for production:

```bash
hugo
```

The generated files will be in the `public/` directory.

## Continuous Deployment with GitHub Actions

This project uses **GitHub Actions** to automate the build and deployment process. The workflow is configured to:

1. Trigger on pushes to the `main` branch.
2. Build the Hugo site using the Hugo CLI.
3. Deploy the generated static files to **AWS Amplify**.

The GitHub Actions workflow configuration can be found in `.github/workflows/deploy.yml`. Key steps include:

- Checking out the repository.
- Installing Hugo.
- Building the site with `hugo --minify`.
- Deploying to AWS Amplify using the Amplify CLI or direct integration.

To set up your own continuous deployment:

1. Configure AWS Amplify in your AWS account (see below).
2. Add the necessary secrets (e.g., `AWS_ACCESS_KEY_ID`, `AWS_SECRET_ACCESS_KEY`) to your GitHub repository's Secrets settings.
3. Ensure the `.github/workflows/deploy.yml` file is correctly configured for your Amplify app.

## Hosting on AWS Amplify

The blog is hosted on **AWS Amplify**, which provides a scalable and secure platform for static site hosting. Amplify integrates seamlessly with GitHub Actions for continuous deployment and supports features like:

- Automatic HTTPS.
- Custom domain configuration.
- Global CDN for fast content delivery.

To host your own Hugo site on AWS Amplify:

1. Create an Amplify app in the AWS Management Console.
2. Connect your GitHub repository to Amplify.
3. Configure the build settings (Amplify auto-detects Hugo builds, but you may need to specify the `public/` output directory).
4. Deploy the app and set up a custom domain (optional).

For detailed instructions, refer to the Hugo deployment guide for AWS Amplify.

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/your-feature`).
3. Make your changes and commit (`git commit -m "Add your feature"`).
4. Push to the branch (`git push origin feature/your-feature`).
5. Open a Pull Request.

Please ensure your changes are compatible with Hugo and follow the project's coding style.

## License

This project is licensed under the MIT License. See the LICENSE file for details.
