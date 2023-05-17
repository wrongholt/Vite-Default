# Vite-Default

[Edit on StackBlitz ⚡️](https://stackblitz.com/edit/vitejs-vite-bythgn)

# To make a Static site on Github Pages.

https://vitejs.dev/guide/static-deploy.html

1. Set the correct base in vite.config.js.

If you are deploying to https://<USERNAME>.github.io/, you can omit base as it defaults to '/'.

If you are deploying to https://<USERNAME>.github.io/<REPO>/, for example your repository is at https://github.com/<USERNAME>/<REPO>, then set base to '/<REPO>/'.

2. Go to your GitHub Pages configuration in the repository settings page and choose the source of deployment as "GitHub Actions", this will lead you to create a workflow that builds and deploys your project, a sample workflow that installs dependencies and builds using npm is provided:

3. Copy code from:
   https://vitejs.dev/guide/static-deploy.html
