# npm

---

## Package Management

### [NPM](https://www.npmjs.com/) - Node.js Package Manager

- Install [node.js](https://nodejs.org/en/) to get the package manager **npm**
- npm packages needed in a project (dependencies) are listed in the `package.json` file and can be install with `npm install` command
- locally installed (=project specific) packages are downloaded to `node_modules/` folder (should be excluded from version control)

---

### OS X no sudo for Mac users

MacOS no sudo for Mac users!!
* Older MacOS (bash terminal)
```
mkdir ~/.npm-packages
npm config set prefix ~/.npm-packages
echo NPM_PACKAGES="${HOME}/.npm-packages" >> ${HOME}/.bashrc
echo prefix=${HOME}/.npm-packages >> ${HOME}/.npmrc
echo NODE_PATH=\"\$NPM_PACKAGES/lib/node_modules:\$NODE_PATH\" >> ${HOME}/.bashrc
echo PATH=\"\$NPM_PACKAGES/bin:\$PATH\" >> ${HOME}/.bashrc
echo source "~/.bashrc" >> ${HOME}/.bash_profile
source ~/.bashrc
```
* Newer MacOS (zsh terminal)
```
mkdir ~/.npm-packages
npm config set prefix ~/.npm-packages
echo NPM_PACKAGES="${HOME}/.npm-packages" >> ${HOME}/.zshrc
echo prefix=${HOME}/.npm-packages >> ${HOME}/.npmrc
echo NODE_PATH=\"\$NPM_PACKAGES/lib/node_modules:\$NODE_PATH\" >> ${HOME}/.zshrc
echo PATH=\"\$NPM_PACKAGES/bin:\$PATH\" >> ${HOME}/.zshrc
echo source "~/.zshrc" >> ${HOME}/.zsh_profile
source ~/.zshrc
```

---

## npm Alternatives

### [Yarn](https://yarnpkg.com/)

- newcomer gaining a lot of traction
- first [open source release on October, 2016](https://code.facebook.com/posts/1840075619545360)
- uses same package.json file and npm registry as npm
- claimed to be faster, more secure and reliable but npm has been catching up

### [PNPM](https://pnpm.io/)

- stores dependencies in a single store, saving disk space and enhancing performance.
- encompasses all the capabilities of npm and yarn, including workspaces, peer dependencies, lockfiles, and scripts.
- offers additional distinctive features, like multiple package registry support, selective dependency resolutions, and customizable installation behavior through hooks.
- integrates with npm packages and tools, allowing for easy installation via npm or curl.

