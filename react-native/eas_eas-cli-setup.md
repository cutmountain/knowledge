# Troubleshoot eas-cli installation

```bash
Last login: Thu Apr  3 19:34:25 on ttys005
(base) montse@Mac ~ % npm install -g eas-cli
npm ERR! code EACCES
npm ERR! syscall mkdir
npm ERR! path /usr/local/lib/node_modules/eas-cli
npm ERR! errno -13
npm ERR! Error: EACCES: permission denied, mkdir '/usr/local/lib/node_modules/eas-cli'
npm ERR!     at async mkdir (node:internal/fs/promises:855:10)
npm ERR!     at async /usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:551:20
npm ERR!     at async Promise.allSettled (index 0)
npm ERR!     at async [reifyPackages] (/usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:251:11)
npm ERR!     at async Arborist.reify (/usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:170:5)
npm ERR!     at async Install.exec (/usr/local/lib/node_modules/npm/lib/commands/install.js:152:5)
npm ERR!     at async module.exports (/usr/local/lib/node_modules/npm/lib/cli-entry.js:61:5)
npm ERR!  Error: EACCES: permission denied, mkdir '/usr/local/lib/node_modules/eas-cli'
npm ERR!     at async mkdir (node:internal/fs/promises:855:10)
npm ERR!     at async /usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:551:20
npm ERR!     at async Promise.allSettled (index 0)
npm ERR!     at async [reifyPackages] (/usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:251:11)
npm ERR!     at async Arborist.reify (/usr/local/lib/node_modules/npm/node_modules/@npmcli/arborist/lib/arborist/reify.js:170:5)
npm ERR!     at async Install.exec (/usr/local/lib/node_modules/npm/lib/commands/install.js:152:5)
npm ERR!     at async module.exports (/usr/local/lib/node_modules/npm/lib/cli-entry.js:61:5) {
npm ERR!   errno: -13,
npm ERR!   code: 'EACCES',
npm ERR!   syscall: 'mkdir',
npm ERR!   path: '/usr/local/lib/node_modules/eas-cli'
npm ERR! }
npm ERR! 
npm ERR! The operation was rejected by your operating system.
npm ERR! It is likely you do not have the permissions to access this file as the current user
npm ERR! 
npm ERR! If you believe this might be a permissions issue, please double-check the
npm ERR! permissions of the file and its containing directories, or try running
npm ERR! the command again as root/Administrator.

npm ERR! A complete log of this run can be found in: /Users/montse/.npm/_logs/2025-04-03T17_44_09_131Z-debug-0.log
(base) montse@Mac ~ % ls
Desktop				OneDrive
Documents			Pictures
Downloads			practicas-en-clase.ipynb
Library				Public
Movies				scikit_learn_data
Music
(base) montse@Mac ~ % mkdir ~/.npm-global
(base) montse@Mac ~ % npm config set prefix '~/.npm-global'
(base) montse@Mac ~ % touch .profile
(base) montse@Mac ~ % vim .profile
(base) montse@Mac ~ % cat .profile
export PATH=~/.npm-global/bin:$PATH
(base) montse@Mac ~ % source ~/.profile
(base) montse@Mac ~ % npm install -g eas-cli
npm WARN deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm WARN deprecated sudo-prompt@9.1.1: Package no longer supported. Contact Support at https://www.npmjs.com/support for more info.
npm WARN deprecated @xmldom/xmldom@0.7.13: this version is no longer supported, please update to at least 0.8.*
npm WARN deprecated rimraf@2.4.5: Rimraf versions prior to v4 are no longer supported
npm WARN deprecated glob@6.0.4: Glob versions prior to v9 are no longer supported
npm WARN deprecated lodash.get@4.4.2: This package is deprecated. Use the optional chaining (?.) operator instead.
npm WARN deprecated @oclif/screen@3.0.8: Package no longer supported. Contact Support at https://www.npmjs.com/support for more info.

added 444 packages in 17s

53 packages are looking for funding
  run `npm fund` for details
(base) montse@Mac ~ % eas login
(node:62412) [DEP0040] DeprecationWarning: The `punycode` module is deprecated. Please use a userland alternative instead.
(Use `node --trace-deprecation ...` to show where the warning was created)
Log in to EAS with email or username (exit and run eas login --help to see other login options)
✖ Email or username … 
(base) montse@Mac ~ % ls -a
.				.odbcinst.ini
..				.profile
.afirma				.python_history
.anaconda			.surprise_data
.bash_profile			.swiftpm
.bashrc				.tcshrc
.cache				.Trash
.CFUserTextEncoding		.viminfo
.conda				.virtual_documents
.condarc			.vscode
.config				.xonshrc
.continuum			.zsh_history
.DS_Store			.zsh_sessions
.expo				.zshrc
.gitconfig			Desktop
.ipynb_checkpoints		Documents
.ipython			Downloads
.jupyter			Library
.lesshst			Movies
.matplotlib			Music
.mcf				OneDrive
.npm				Pictures
.npm-global			practicas-en-clase.ipynb
.npmrc				Public
.nvm				scikit_learn_data
.odbc.ini
(base) montse@Mac ~ % cat .profile
export PATH=~/.npm-global/bin:$PATH
```