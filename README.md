IMPORTANT NOTES:

if you want to use development branch (unstable, but latest development) clone using --branch develop
it's necessary to enable Git symlinks because they used for shared modules (every project has symlinks to shared modules in the /shared folder)
because of symlinks, you may need to clone from an elevated command prompt. On Windows run console with "Run as Administrator" option.
If you use Git >= v2.14, it probably makes sense to setup following globally:

git config --global core.symlinks true
git config --global submodule.recurse true
Notes:

to setup Symlinks & Submodules recurse locally only (for Ever repo), remove --global in the commands above
for older Git versions see this
at the moment we are not using Git sub-modules, but it may change in the future (we were using them, but decided to drop for now in favor of symlinks)
we are moving from symlinks to npm modules managed by Lerna. See branch https://github.com/ever-co/ever/tree/feature/use-packages
Yarn
Currently, we are using Yarn (instead of npm), so make sure you have latest Yarn version installed before running Ever Platform:

npm install -g yarn@latest
Quick installation
After git repo cloned, just run following command to install/bootstrap all dependencies:

yarn bootstrap
Above command install required packages in all Platform projects using Lerna.

Note: if above command fails for any reason, you can try to install required packages manually by running yarn inside every sub-folder with 'package.json' file

Lerna (manual installation)
We are using Lerna for mono-repo management. You need to run the following command from the working folder where you cloned Ever git repo, which install Lerna together with other packages:

yarn
You may instead install Lerna globally:

npm install lerna@latest -g
Now, after Lerna installed (locally or globally), you need to Bootstrap all dependencies manually:

yarn lerna bootstrap
The command above install all required packages for every sub-project of the Ever Platform.

Note: if above command fails for any reason, you can try to install required packages manually by running yarn inside every sub-folder with 'package.json' file

MongoDB
Ever platform configured to use MongoDB by default and assume you have MongoDB service running and accepting connections on the default localhost:27017. Please see relevant section in our documentation.

Platform Configuration
See relevant section in our documentation.

Run Platform Projects
Finally, each project from Ever Platform could start by single command from this list:

Run API server yarn run:server
Run Admin Website yarn run:admin and open http://localhost:4200
Run Shopping Mobile App yarn run:shopmobile and open http://localhost:4201
Run Merchant Ionic Tablet App yarn run:merchant and open http://localhost:4202
Run Carrier Mobile app yarn run:carrier and open http://localhost:4203
Run Shopping Website yarn run:shopweb and open http://localhost:3000
Note 1: during development you can run server with yarn run:server:dev to enable watch on TS files changes

Note 2: on the first run, API Server (Backend) creates MongoDB local database ever_development with the following (default) Admin user
