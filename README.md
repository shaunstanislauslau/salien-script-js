# salien-script-js

👽 Scripting the Steam Salien Sale minigame, the proper way.

> A Node.js implementation of https://github.com/SteamDatabase/SalienCheat by [xPaw](https://github.com/xPaw) with additional features!

[![npm](https://img.shields.io/npm/v/salien-script-js.svg)](https://www.npmjs.com/package/salien-script-js)
[![CI Status](https://img.shields.io/travis/South-Paw/salien-script-js.svg)](https://travis-ci.org/South-Paw/salien-script-js)
[![Dependencies](https://david-dm.org/South-Paw/salien-script-js.svg)](https://david-dm.org/South-Paw/salien-script-js)
[![Dev Dependencies](https://david-dm.org/South-Paw/salien-script-js/dev-status.svg)](https://david-dm.org/South-Paw/salien-script-js?type=dev)

---

## 🌈 Features

* 🎉 Easy to install, run and update
* ✉️ Update checker and log notifications
* 👽 Same logic as the [PHP version](https://github.com/SteamDatabase/SalienCheat) (we almost have parity)
* 👌 Pick your own steam group
* 👥 Works well with multiple tokens/scripts
* 👀 Name your running scripts
* 🐳 Docker support
* ☁️ Heroku support

> Note: We'll try our best to keep this version up to date with the PHP and other versions! Suggestions welcome.

---

## 🕹️ How to use this

1. Install [Node.js](https://nodejs.org/en/). (Version 10 and above)
2. Log into [Steam](http://store.steampowered.com/) in your browser.
3. Open the following URL: <https://steamcommunity.com/saliengame/gettoken>. You should be able to find the bit that looks like `"token":"xxxxxxxx"`. Copy whatever is inside the second quotes, (e.g. `xxxxxxxx`).
4. Open PowerShell on Windows. (Tip: Start > Run > type `powershell.exe` > Enter)
5. Run `npm install -g salien-script-js` to install this project.
6. Run the script by typing `salien-script-js --token xxxxxxxx` where `xxxxxxxx` is your token from step 3.

> ### If you appreciate the script, please leave a star ⭐ on the project!

## 😍 How to update the script

1. Close/cancel any running script windows
2. Open PowerShell on Windows.
3. Run `npm update -g salien-script-js`
4. Re-run your scripts using the same command

Easy right?

---

### 👌 Represent your Steam Group (Optional)

If you'd like to represent a specific steam group, simply pass the `--group` option with the ID of the group.

```sh-session
salien-script-js --token xxxxxxxx --group 123456789
```

You can get your group id by going to https://steamcommunity.com/groups/YOUR_GROUP_NAME_HERE/memberslistxml/?xml=1 and replacing `YOUR_GROUP_NAME_HERE` with the group name shown at the end of your groups url.

**You must be a member of a group to represent that group!**

If you'd like to team up with an established larger group please consider using either:

* [/r/saliens](https://steamcommunity.com/groups/summersaliens) id: `103582791462557324`
* [100Pals](https://steamcommunity.com/groups/100pals) id: `103582791454524084`
* [SteamDB](https://steamcommunity.com/groups/steamdb) id: `103582791434298690`

### 👥 Multiple tokens/scripts

Simply open another PowerShell window and run `salien-script-js --token yyyyyyyy --name "name of this script"` where `yyyyyyyy` is your other accounts token and `name of this script` if what you'd like to see in the log outputs.

---

## Advanced: 📦 Usage as an npm package

```js
const SalienScript = require('salien-script-js');

const config = {
  token: '', // Your token from https://steamcommunity.com/saliengame/gettoken
  clan: '', // (optional) Clan id from https://steamcommunity.com/groups/YOUR_GROUP_NAME_HERE/memberslistxml/?xml=1
  name: '', // (optional) Name of this instance for logging
};

const salien = new SalienScript(config);

salien.init();
```

## Advanced: ☁️ Deploying to heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy)

1. Click the button above.
2. Set SALIEN_CONFIG ("token1:group1:name1;token2:group2:name2...").
3. All done. For now, there is no way to update script easily without re-creating heroku app or manually pulling upstream changes into heroku repo.

## Advanced: 🐳 Running as a Docker container

The provided Dockerfile allows you to build this repository as a Docker container. To do that, clone the following repo and run the following commands.

```bash
# builds an image of the repo
$ docker build -t salien-script-js .

# sets up a container based on said image in "detached" mode
$ docker run -d --name salien-script-js salien-script-js [options]
```

You can also set up continuous deployment through Docker Hub. [Read the following comment](https://github.com/South-Paw/salien-script-js/pull/11#issuecomment-399747215) for a guide.

---

## 👨‍💻 Contributing and Development

Want to help out? Awesome! 👍

Pull the repo and you can run the script with `node cli.js -t TOKEN`.

PRs, suggestions, fixes and improvements all welcome.

---

## License

This project is licensed under [MIT](https://github.com/South-Paw/salien-script-js/blob/master/LICENSE)

```
MIT License

Copyright (c) 2018 Alex Gabites

https://github.com/South-Paw/salien-script-js

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
