# Vite-Default

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/vitejs-vite-bythgn)

# To make a Static site on Github Pages.

https://vitejs.dev/guide/static-deploy.html

1. Set the correct base in vite.config.js.

If you are deploying to https://<USERNAME>.github.io/, you can omit base as it defaults to '/'.

If you are deploying to https://<USERNAME>.github.io/<REPO>/, for example your repository is at https://github.com/<USERNAME>/<REPO>, then set base to '/<REPO>/'.

2. Go to your GitHub Pages configuration in the repository settings page and choose the source of deployment as "GitHub Actions", this will lead you to create a workflow that builds and deploys your project, a sample workflow that installs dependencies and builds using npm is provided:

# Simple workflow for deploying static content to GitHub Pages

name: Deploy static content to Pages

on:

# Runs on pushes targeting the default branch

push:
branches: ['main']

# Allows you to run this workflow manually from the Actions tab

workflow_dispatch:

# Sets the GITHUB_TOKEN permissions to allow deployment to GitHub Pages

permissions:
contents: read
pages: write
id-token: write

# Allow one concurrent deployment

concurrency:
group: 'pages'
cancel-in-progress: true

jobs:

# Single deploy job since we're just deploying

deploy:
environment:
name: github-pages
url: ${{ steps.deployment.outputs.page_url }}
runs-on: ubuntu-latest
steps: - name: Checkout
uses: actions/checkout@v3 - name: Set up Node
uses: actions/setup-node@v3
with:
node-version: 18
cache: 'npm' - name: Install dependencies
run: npm install - name: Build
run: npm run build - name: Setup Pages
uses: actions/configure-pages@v3 - name: Upload artifact
uses: actions/upload-pages-artifact@v1
with: # Upload dist repository
path: './dist' - name: Deploy to GitHub Pages
id: deployment
uses: actions/deploy-pages@v1
