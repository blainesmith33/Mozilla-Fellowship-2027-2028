# Explain blAIne (27)

- Conversation ID: `6b092cef-acc4-83e8-bd71-47264d4f6ffc`
- Exported: 2026-11-27T07:57:25.000Z
- Scope: human-visible user/assistant messages on the active conversation branch
- Raw source: matching .raw.json archive containing the complete ChatGPT conversation endpoint response

---

## Assistant

This is a useful find. The `cics_v2` directory is not itself a Git repository, but it contains a substantial, physically preserved copy of the AzerothCore Wiki.

The important detail is that it has the actual documentation structure (`docs/`, `_includes/`, `_layouts/`, `_posts/`, assets, and configuration), not just references to AzerothCore. It may be the surviving copy we need.

Let's check its own documentation for provenance before modifying or copying anything. Run:

```bash
WIKI="/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki"

for FILE in \
  .github/README.md \
  .github/README_es.md \
  docs/getting-started.md \
  docs/wiki-standards.md \
  _config.yml
do
  echo
  echo "========== $FILE =========="
  sed -n '1,180p' "$WIKI/$FILE"
done
```

I'm looking for an upstream repository URL, revision or synchronization date, and any indication of whether this was a complete clone or a curated documentation export. We should preserve this copy untouched until we know what it represents.

## User

\========== .github/README.md ========== \
\# AzerothCore Wiki \
&#x20;\
Welcome to the AzerothCore Wiki! This repository provides comprehensive documentation for setting up, configuring, and customizing the AzerothCore WoW emula\
tor. \
&#x20;\
If you want to contribute to the wiki please open a PR in the /docs/ directory. \
&#x20;\
Any problems? [Open a issue]\([https://github.com/azerothcore/wiki/issues/new](https://github.com/azerothcore/wiki/issues/new)). \
&#x20;\
\========== .github/README_es.md ========== \
\# AzerothCore WIKI \
&#x20;\
Leer en: [Ingles :gb:]\(README.md) | [Español :es:]\(README_es.md) \
&#x20;\
Wiki para el proyecto AzerothCore disponible aquí: [http://azerothcore.github.io/wiki/es](http://azerothcore.github.io/wiki/es) \
&#x20;\
\## Cómo instalar localmente (desarrollo) \
&#x20;\
\### Con [docker-compose]\([https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)) \
&#x20;\
1\. Instalar [docker-compose]\([https://docs.docker.com/compose/install/](https://docs.docker.com/compose/install/)) \
2\. Ejecutar \`docker-compose up github-wiki-theme\` \
3\. El sitio web estará listo el \`[http://127.0.0.1:4000/](http://127.0.0.1:4000/)\` \
&#x20;\
\### Sin docker compose \
&#x20;\
En primer lugar, instale el [entorno de desarrollo ruby]\([https://jekyllrb.com/docs/installation/](https://jekyllrb.com/docs/installation/)) utilizando [esta guía]\([https://jekyllrb.com/docs/installat](https://jekyllrb.com/docs/installat)\
ion/). \
&#x20;\
Después de eso, instale \`bundler\` usando la gema y ejecute \`bundler install\`: \
&#x20;\
\`\`\` \
$ gem install bundler \
$ bundle install \
\`\`\` \
&#x20;\
Pues bien, ahora puedes ejecutar localmente la aplicación utilizando: \
&#x20;\
\`\`\` \
bundle exec jekyll serve \
\`\`\` \
&#x20;\
Si todo ha ido bien, puedes visitar tu aplicación web en \`[http://127.0.0.1:4000/](http://127.0.0.1:4000/)\`. \
&#x20;\
¿Algún problema? [Abrir una incidencia]\([https://github.com/azerothcore/wiki/issues/new](https://github.com/azerothcore/wiki/issues/new)). \
&#x20;\
\========== docs/getting-started.md ========== \
\# Getting started with AzerothCore \
&#x20;\
\## Introduction \
&#x20;\
Would you like to learn about AzerothCore (AC), setup your WoW server for the first time, understand how to modify it and become able to contribute? You cam\
e to the right place! \
&#x20;\
Getting started with WoW emulation might be tricky at first, but don't worry, we will be there to help you in case you encounter any issue or have any quest\
ions to ask. Just read [this page]\(How-to-ask-for-help) before asking for help. \
&#x20;\
If while reading any of the tutorials linked on this page you find something that is not clear: let us know. We'll do our best to rephrase it and make it ea\
sier to be understood for beginners. Improving the docs is also a way to contribute! \
&#x20;\
![AzerothCore learning code]\([https://user-images.githubusercontent.com/75517/109369720-b6fa7d00-789d-11eb-86b4-5fe15d6ab834.png](https://user-images.githubusercontent.com/75517/109369720-b6fa7d00-789d-11eb-86b4-5fe15d6ab834.png)) \
&#x20;\
&#x20;\
\## Knowledge requirements \
&#x20;\
There are \*\*NO\*\* technical requirements. You just need to be patient and willing to learn. \
&#x20;\
If you already have some programming knowledge it would surely be an advantage for you. However, trust me, you don't need any pre-existing knowledge to lear\
n about WoW servers. \
&#x20;\
\*Personal note from the author of this tutorial: when I first installed my first WoW server I was 15, I had no programming knowledge at all, I was using Win\
dows XP and barely understood English. I'm sure if you are reading this, you have already more skills than I used to have when I was trying to install MaNGO\
S+UDB+ScriptDev2 and get a decent WoW server to run on my local machine. \
Initially, I spent hours trying to read and understand tutorials from different people written on different websites, but eventually, I succeeded. AzerothCo\
re is an all-in-one project so it's going to be easier than that, bear with me and you'll get there!\* \
&#x20;\
Tempted to use a repack instead? [Don't do it]\([https://www.mangosrumors.org/why-you-should-not-use-repacks-to-run-your-wow-server/](https://www.mangosrumors.org/why-you-should-not-use-repacks-to-run-your-wow-server/)). \
&#x20;\
\## Installing AzerothCore on your computer \
&#x20;\
The first step is always installing a local WoW server in your own machine. And there are several ways to do it, which can vary according to the operating s\
ystem. \
&#x20;\
\### Your operating system \
&#x20;\
Let me be clear about one thing: \*\*ALL operating systems are supported by AzerothCore\*\*. \
So you can successfully install AzerothCore GNU/Linux, macOS or Windows without any issue. \
&#x20;\
However, I can tell you if you use a Linux distribution such as \*\*Ubuntu 20.04\*\*, the process is going to be easier. If you would like to install Ubuntu, yo\
u can download it from [here]\([https://ubuntu.com/download/desktop](https://ubuntu.com/download/desktop)) and you can find plenty of tutorials online about how to do it. There is a nice tutorial \
about running WoW on Linux [here]\([https://www.mangosrumors.org/how-to-run-wow-on-linux/](https://www.mangosrumors.org/how-to-run-wow-on-linux/)). \
&#x20;\
Would you like to stick with \*\*Windows\*\* or \*\*macOS\*\*? That's absolutely fine. \
&#x20;\
![AzerothCore supports GNU/Linux, macOS and Windows]\([https://user-images.githubusercontent.com/75517/109369213-e5775880-789b-11eb-8356-99a4ab842bfb.png](https://user-images.githubusercontent.com/75517/109369213-e5775880-789b-11eb-8356-99a4ab842bfb.png)) \
&#x20;\
\### Different ways to install AzerothCore \
&#x20;\
Basically, there are 3 main ways to install AC: \
&#x20;\
\- The "\*\*classic setup\*\*": this is the traditional setup you would normally use to install a common WoW emulator. \*\*All operating systems are supported.\*\* D\
oing this setup also probably gives you a better overview of the components of the server. \
\- The "\*\*docker setup\*\*": this is a simplified setup that uses Docker to automate a lot of things for you. This setup is typically easier. \*\*You can use thi\
s setup in all operating systems where you can install [Docker]\([https://www.docker.com/products/docker-desktop).\*\*](https://www.docker.com/products/docker-desktop\).**) \
\- The "\*\*dashboard setup\*\*": this is an \*\*EXTREMELY EASY\*\* way of installing AzerothCore in your machine, based on a collection of bash scripts created by [\
Yehonal]\([https://github.com/Yehonal](https://github.com/Yehonal)). However, \*\*you can only use this setup in Ubuntu\*\* or similar platforms. Windows is not supported, and probably we are\
&#x20;not there yet with macOS as well. \
&#x20;\
You can choose one setup, or even try more than one. You can find all the instructions here: \
&#x20;\
\- [azerothcore.org/wiki/Installation]\(installation) \
&#x20;\
Should you encounter any issue or doubt while trying to install your AC server, [ask us for help]\([https://github.com/azerothcore/wiki/blob/master/docs/how-t](https://github.com/azerothcore/wiki/blob/master/docs/how-t)\
o-ask-for-help). \
&#x20;\
Got your WoW server installed? Congratulations! Now let's see what you can do next. \
&#x20;\
![AzerothCore server running on macOS]\([https://user-images.githubusercontent.com/75517/109369101-80236780-789b-11eb-900c-bcc17a3cf13c.png](https://user-images.githubusercontent.com/75517/109369101-80236780-789b-11eb-900c-bcc17a3cf13c.png)) \
&#x20;\
\## Access the game, learn the GM commands \
&#x20;\
First of all, make sure your Client has their realmlist.wtf set to the following: \`set realmlist localhost\`. After this (assuming you've already setup Azero\
thCore) make sure you've a \`GM\` (Security of 2 or Higher) account created. If you haven't created an account or you're not sure follow this [Creating Accoun\
ts]\(creating-accounts). \
After this your \`GM\` account will be able to use the following commands from link with a list of all commands below: \
&#x20;\
\- [azerothcore.org/wiki/GM-Commands]\(GM-Commands) \
&#x20;\
Get confident with the commands, you will need them for any administration, testing or development activities. \
&#x20;\
![AzerothCore GM]\([https://user-images.githubusercontent.com/75517/109369940-ba423880-789e-11eb-88d6-e6d8f7b8a723.png](https://user-images.githubusercontent.com/75517/109369940-ba423880-789e-11eb-88d6-e6d8f7b8a723.png)) \
&#x20;\
\## Consider learning git \
&#x20;\
You can just blindly copy-paste the \`git\` commands that you'll see in the tutorials linked here, most likely you will not have issues with them. \
However, properly learning \`git\` will make you really aware of what you're doing, and this knowledge can help you with whatever other software development p\
roject you may work with. \
Yes, because \`git\` is one of the most important tools used in many software engineering projects. Learning its basics will not only help you a lot with Azer\
othCore, but it's also something very good to put in your CV. \
&#x20;\
You can find plenty of resources online about learning \`git\`, for example [try.github.io]\([https://try.github.io/](https://try.github.io/)) \
&#x20;\
![AzerothCore learning git]\([https://user-images.githubusercontent.com/75517/109370018-fb3a4d00-789e-11eb-8532-1ab1bf8fba60.png](https://user-images.githubusercontent.com/75517/109370018-fb3a4d00-789e-11eb-8532-1ab1bf8fba60.png)) \
&#x20;\
\## Learn how to update your WoW server \
&#x20;\
We release improvements to AzerothCore on a daily basis. You should learn how to update your server and keep updating it often. We recommend avoiding workin\
g on older versions of AzerothCore because they can have bugs that we already resolved and you don't want to stay behind. \
&#x20;\
So it is \*\*very important\*\* that you update your AzerothCore server regularly. We recommend you to do it at least once a week. Read this guide: \
&#x20;\
\- [azerothcore.org/wiki/Update]\(update) \
&#x20;\
After you follow the update procedure, it is important to \*\*verify\*\* that: \
&#x20;\
\- Your server application (core) has been properly updated, use the \`server info\` command to make sure of it. \
\- Your DB has been properly updated and aligned to your core version, [read this answer on stackoverflow]\([https://stackoverflow.com/a/55282168/3497671](https://stackoverflow.com/a/55282168/3497671)). \
&#x20;\
![AzerothCore server info]\([https://user-images.githubusercontent.com/75517/109370296-00e46280-78a0-11eb-9ed0-b9df14f2008b.png](https://user-images.githubusercontent.com/75517/109370296-00e46280-78a0-11eb-9ed0-b9df14f2008b.png)) \
&#x20;\
\## Learn to check out PRs \
&#x20;\
A great way to start contributing is by testing PRs made by other contributors. This is not only quite easy to do, but it is extremely helpful for the proje\
ct and can help you to get into our development process. \
&#x20;\
This topic is so important that there is a dedicated tutorial for it: \
&#x20;\
\- [azerothcore.org/wiki/How-to-test-a-PR]\(How-to-test-a-PR) \
&#x20;\
![image]\([https://user-images.githubusercontent.com/75517/109370244-d397b480-789f-11eb-9ac7-64d98ca0d33c.png](https://user-images.githubusercontent.com/75517/109370244-d397b480-789f-11eb-9ac7-64d98ca0d33c.png)) \
&#x20;\
\## Learning how to work with the Database \
&#x20;\
The Database is the best place to start developing a WoW server. Because it's easier than the other components, and there are tools that are able to automat\
ically generate the code for you. For example, Keira3. \
&#x20;\
\### Download Keira3 \
&#x20;\
Keira3 is a DB editor for AzerothCore which allows you to edit or add contents to the world very easily, we recommend to install and play with it: \
&#x20;\
\- [azerothcore.org/Keira3]\([https://www.azerothcore.org/Keira3](https://www.azerothcore.org/Keira3)) \
&#x20;\
Keira3 automatically generates the SQL code needed to create or change stuff in the database. \
Sounds complicated? Give it a try and you'll see how it works. \
&#x20;\
![AzerothCore Keira3]\([https://user-images.githubusercontent.com/75517/109370160-769bfe80-789f-11eb-9958-dc17ff48f39a.png](https://user-images.githubusercontent.com/75517/109370160-769bfe80-789f-11eb-9958-dc17ff48f39a.png)) \
&#x20;\
\### Download a MySQL client \
&#x20;\
You'll need a generic database management tool too in order to manage tables and their contents. \
&#x20;\
\- [Database Management Tool]\(database-management-tool) \
&#x20;\
![AzerothCore world database viewed with sequel-ace]\([https://user-images.githubusercontent.com/75517/109370368-42750d80-78a0-11eb-946c-c0831a02b52b.png](https://user-images.githubusercontent.com/75517/109370368-42750d80-78a0-11eb-946c-c0831a02b52b.png)) \
&#x20;\
\### The DB documentation is your friend \
&#x20;\
Always read the documentation about every table that you deal with: \
&#x20;\
\- [azerothcore.org/wiki/database-world]\(database-world) \
&#x20;\
\### SmartAI \
&#x20;\
With SmartAI you can do a lot of things. You can add special behaviour to an element of the game such as a creature, without ever touching a single line of \
C++. \
&#x20;\
In a nutshell, with SmartAI you can make an entity (for example a Creature) perform a certain \*\*action\*\* when a certain \*\*event\*\* occurs, optionally specify\
ing a \*\*target\*\*. In other words, you can make entities react to events with behaviour defined by you. \
&#x20;\
For example, you can make a creature cast a spell (action), when its health goes below 50% of its total health (event), against a random member of the party\
&#x20;group (target). \
&#x20;\
Technically the \`smart_script\` is just a table inside the world database (and its documentation can be found [here]\(smart_scripts)). Tools like Keira3 help \
you working with SmartAI using a practical graphic interface. \
&#x20;\
Try to open Keira3, look for any creature that has "SmartAI" as "AIName", open it and click on "SmartAI" on the right menu. \
You'll be prompted with a visual editor that will assist you when working with SmartAI. \
&#x20;\
![AzerothCore SmartAI with Keira3]\([https://user-images.githubusercontent.com/75517/109367698-1bfea480-7897-11eb-9cf0-f047b3dcdb85.png](https://user-images.githubusercontent.com/75517/109367698-1bfea480-7897-11eb-9cf0-f047b3dcdb85.png)) \
&#x20;\
Experiment with the SmartAI and get confident with it. It's a simple but very powerful tool. \
After getting some knowledge of it, you will be able to do many things. Many bugs can be fixed just using the SmartAI. \
&#x20;\
The AI of most of the creatures you'll find in the world is done with SmartAI. While more complex creatures (typically raid bosses) are scripted in C++. \
&#x20;\
![SmartAI vs C++]\([https://user-images.githubusercontent.com/75517/109369529-e78de700-789c-11eb-97d5-02ecc6c85a0a.png](https://user-images.githubusercontent.com/75517/109369529-e78de700-789c-11eb-97d5-02ecc6c85a0a.png)) \
&#x20;\
\### Learn the SQL language \
&#x20;\
Usually, you'll need only the basics of the SQL language, and in most cases, you'll probably figure it out by yourself, however, it's not a bad idea to read\
&#x20;about the SQL language. You can find a lot of resources online, for example: \
&#x20;\
\- [[https://www.w3schools.com/sql/sql_intro.asp\](https://www.w3schools.com/sql/sql_intro.asp)](https://www.w3schools.com/sql/sql_intro.asp]\(https://www.w3schools.com/sql/sql_intro.asp\)) \
&#x20;\
if you understand how basic statements such as \`SELECT\`, \`UPDATE\`, \`INSERT\` and \`DELETE\` work, that's usually enough. You don't need to go too deep into SQL\
&#x20;in order to be able to contribute. \
&#x20;\
\## Share your code! \
&#x20;\
You can submit your improvement via PR. Read this guide: \
&#x20;\
\- [How to create a Pull Request (PR)]\(how-to-create-a-pr) \
&#x20;\
\## Start contributing! \
&#x20;\
If you mastered some of the above parts, there is already \*\*A LOT\*\* you can do to help our project and becoming a contributor. \
For example: \
&#x20;\
\- Help the developers by testing PRs and giving your feedback \
\- Do some bug triaging by confirming issues and helping us to identify and close the invalid reports \
\- You can also help by [triaging the bugs coming from the players of ChromieCraft]\([https://github.com/chromiecraft/chromiecraft](https://github.com/chromiecraft/chromiecraft)) (our child-project) \
\- Report any bug that you may find yourself \
\- Try to fix bugs, a lot of them can just be fixed with some SQL and you can use Keira3 for that (e.g. using SmartAI or other embedded editors). Being this \
an open-source project, you can find plenty of examples on our main GitHub repository \
&#x20;\
Would you like to talk to us? Join [the AzerothCore Discord server]\([https://discordapp.com/invite/gkt4y2x](https://discordapp.com/invite/gkt4y2x)). \
&#x20;\
\========== docs/wiki-standards.md ========== \
\# WIKI STANDARDS \
&#x20;\
\## FILE NAMING: \
&#x20;\
DATABASE TABLES files are to be named exactly as it is in the database, \
&#x20;\
ALL OTHER FILES are to be named in \`lowercase\` and to use \`-\` (dashes) for spaces. \
&#x20;\
FILES SHOULD NOT contain special characters other than \`-\` (dashes). If we want a file named C++ we name it cpp. \
&#x20;\
ALL WIKI FILES should end with with \`.md\`. \
&#x20;\
\## FILE ENCODING \
&#x20;\
ALL FILES must be UTF-8 encoded to work on the wiki. \
&#x20;\
\## FILE LANGUAGE \
&#x20;\
TO ENSURE EASY MAINTENANCE, all files must be written in \`markdown\` format. HTML is not allowed! \
&#x20;\
\## FILE HEADERS \
&#x20;\
THE FILE  SHOULD ALWAYS START WITH \`# File Name\`. (This is to display correct info in the browser tab.) \
&#x20;\
\## DATABASE TABLE FILES: \
&#x20;\
ALL DATABASE TABLE FILES should be present in the correct DATABASE FILE. \
&#x20;\
When adding/removing a table it should also be updated in \`database-auth\` \`database-characters\` \`database-world\` \
&#x20;\
\## LINKING WITHIN THE WIKI \
&#x20;\
When linking to a page in the wiki we use relative links. (\`[home]\(home#overview)\`). \
&#x20;\
When linking to a header on the same page in the wiki relative links. (\`[withCapitalLetters]\(#withcapitalletters).\` \
&#x20;\
It is important to note that only lowercase letters and no special characters are allowed in relative links. Otherwise, the links will be broken. \
&#x20;\
When linking to a page outside of the wiki we use absolute links. (\`[Google]\([https://google.com](https://google.com))\`). \
&#x20;\
\## TRANSLATION \
&#x20;\
ALL TRANSLATIONS should be in a sub-directory of /docs/ with the shortened locale of the language. i.e./docs/es/. If there have been no translations prior, \
you need to allow the directory path in the config. See [this commit on how to do it]\([https://github.com/azerothcore/wiki/commit/8b897c3384298674e82108357ee](https://github.com/azerothcore/wiki/commit/8b897c3384298674e82108357ee)\
5e655f788229f). \
&#x20;\
ALL FILES should be named the \*\*exact same as the English versions\*\*! Do not ever translate the file names, only the contents within. \
&#x20;\
\## ARCHIVED PAGES: (Not yet implemented) \
&#x20;\
ALL ARCHIVED PAGES that could potentially have some some value should be added to the \`archive\` list and links to these pages should be removed from other p\
laces in the wiki. \
&#x20;\
They should also be moved into the /docs/archive/ folder. \
&#x20;\
\========== \_config.yml ========== \
\# this version is only used internally to update  \
\# the remote_theme when needed \
ac_wiki_version: 2.0.5 \
\# based on latest (master) git-wiki-theme \
remote_theme: Drassil/git-wiki-theme@master \
\# (string) Title of your wiki \
title: AzerothCore \
\# (string) Description of your wiki \
description: Wiki and Documentation of the AzerothCore project \
\# (boolean) Enable/disable wiki page list in sidebar \
show_wiki_pages: true \
\# (integer) Maximum number of wiki page to shown in sidebar \
show_wiki_pages_limit: 0 \
\# (boolean) Enable/disable blog feature \
blog_feature: false \
\# (boolean) Enable/disable wiki posts list in sidebar (needs blog_feature enabled) \
show_wiki_posts: false \
\# (integer) Maximum number of wiki posts to shown in sidebar \
show_wiki_posts_limit: 10 \
\# from jekyll (read jekyll doc) \
paginate: 5 \
paginate_path: "/blog/page:num" \
permalink: /blog/posts/:year/:month/:day/:title:output_ext \
\# (boolean) Enable/disable download buttons in sidebar \
show_downloads: false \
\# (string) Specify branch rendered by gitpages allowing wiki tool buttons to work \
git_branch: "master" \
\# (string) Url of logo image, it can be full, absolute or relative. \
logo_url: [http://www.azerothcore.org/images/logo.png](http://www.azerothcore.org/images/logo.png) \
\# (string) The UA-XXXXX-Y code from google analytic to enable GA on your wiki \
google_analytics: \
\# (string) folder where wiki pages are stored, it's needed for tool buttons \
wiki_folder: docs \
\# (boolean) if you're using github wiki as submodule then this config \
\# must be enabled to allow tool buttons to work properly \
use_github_wiki: false \
\# (boolean) Enable "Edit with Prose.io" button in tools, it's a 3rd party \
\# service to edit github markdown pages easily \
use_prose_io: false \
\# Select search_engine component from: \
\# - js: it uses a built in javascript component that uses generated js object \
\# - js_rss: it uses a built in javascript component that uses generated  sitemap_full.xml to search inside your wiki with lunr library (slow and experimenta\
l) \
\# - github : it uses internal github repository search \
\# - google : it uses cse search bar, you need to configure google_cse_token \
\# \
search_engine : "js" \
\# Setting google custom search engine for google \
\# cse search bar ([https://cse.google.it/cse/](https://cse.google.it/cse/)) \
google_cse_token: \
&#x20;\
\# \
\# Jekyll configurations \
\# \
&#x20;\
\# You can customize it changing default layout for all pages \
\# More info: [https://jekyllrb.com/docs/configuration/](https://jekyllrb.com/docs/configuration/) \
\# \
\# git-wiki includes some internal themes that you can choose \
\# check \_layouts folder \
\# \
markdown: GFM \
highlighter: rouge \
encoding: UTF-8 \
&#x20;\
defaults: \
&#x20;\- \
&#x20;   scope: \
&#x20;     locale: "en" \
&#x20;     path: "docs" \
&#x20;   values: \
&#x20;     permalink: /:basename \
&#x20;\- \
&#x20;   scope: \
&#x20;     locale: "es" \
&#x20;     path: "docs/es" \
&#x20;   values: \
&#x20;     permalink: /es/:basename \
&#x20;\- \
&#x20;   scope: \
&#x20;     path: "" # an empty string here means all files in the project \
&#x20;   values: \
&#x20;     layout: "azerothcore" \
&#x20;\- \
&#x20;   scope: \
&#x20;     path: "" \
&#x20;     type: "pages" \
&#x20;   values: \
&#x20;     layout: "azerothcore" \
&#x20;\- \
&#x20;   scope: \
&#x20;     path: "" \
&#x20;     type: "posts" \
&#x20;   values: \
&#x20;     layout: "git-wiki-post" \
&#x20;\- \
&#x20;   scope: \
&#x20;     path: blog \
&#x20;   values: \
&#x20;     layout: "git-wiki-blog" \
sass: \
&#x20;   style: compressed \
plugins: \
&#x20;\- jekyll-feed \
&#x20;\- jekyll-redirect-from \
&#x20;\- jekyll-seo-tag \
&#x20;\- jekyll-sitemap \
&#x20;\- jekyll-avatar \
&#x20;\- jemoji \
&#x20;\- jekyll-mentions \
&#x20;\
exclude: ['wiki'] \
&#x20;\
&#x20;\
\# \
\# INCLUDING HOOKS \
\# They are optional, change them only if you need \
\# Check wiki documentation to learn how they work \
\# \
&#x20;\
inc_before_toc : \
inc_after_toc : \
inc_before_content : \
inc_after_content : \
inc_before_footer : \
inc_after_footer : \
inc_before_head : \
inc_after_head : "azerothcore/afterhead.html" \
inc_before_meta : \
inc_after_meta : \
inc_before_scripts : \
inc_after_scripts : \
inc_before_styles : \
inc_after_styles : \
inc_before_header : \
inc_after_header : \
inc_before_tail : \
inc_after_tail : \
inc_before_tools : \
inc_after_tools : \
&#x20;\
inc_before_page_list : "azerothcore/sidebar.html" \
inc_after_page_list : \
inc_before_post_list : \
inc_after_post_list : \
(**deck@ExosSteamDeck engineering-rag-corpus**)$ \
&#x20;\
&#x20;

## Assistant

Yes. I was investigating the missing **AzerothCore Wiki source snapshot referenced by the Engineering RAG project**. I should have made that explicit before sending you through more searches.

Your latest output is useful: it confirms that `cics_v2` contains a substantial AzerothCore Wiki source tree, not merely a few references to it. The fact that `cics_v2` itself is not a Git repository does not diminish the value of that copy.

But I don't want to conflate two things:

- **The AzerothCore Wiki inside CICS v2:** a potentially usable source copy.
- **The Engineering RAG acquisition:** a separately recorded full Git clone pinned to commit `7d540fc7e683c3bf34a2f465789f1b3df268b609`, with a 1,054-file inventory and SHA-256 record.

We haven't established whether the CICS v2 copy is the same snapshot, an earlier version, or a separately acquired copy.

And to be clear: I'm not asking you to rebuild AzerothCore or investigate the game server. This is strictly about identifying the source data behind the Engineering RAG work.

**Next, I'd like to compare the CICS v2 Wiki tree against the acquisition record**—file count, documentation contents, and Git metadata if any exists. That will tell us whether this is the missing source or a different copy.

## User

do it

## Assistant

We'll compare the CICS v2 Wiki tree directly against the exact Engineering RAG pin:

`7d540fc7e683c3bf34a2f465789f1b3df268b609`

This is a content-level comparison, not just matching file counts. It will identify:

- Files present in both copies with identical contents.
- Files present in both but with different contents.
- Files missing from the CICS copy.
- Additional files in the CICS copy.
- Whether the 912-document English/Spanish source scope is represented.

The procedure fetches only the pinned Wiki Git objects into a temporary directory. It does not modify either project or the old-drive copy.

Run this in Konsole:

```bash
set -euo pipefail

WIKI="/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki"
PIN="7d540fc7e683c3bf34a2f465789f1b3df268b609"
TMP="$(mktemp -d /tmp/azerothcore-wiki-compare.XXXXXX)"
trap 'rm -rf "$TMP"' EXIT

echo "Fetching the exact Engineering RAG Wiki revision..."
git init --bare -q "$TMP/repo.git"
git --git-dir="$TMP/repo.git" fetch -q --depth=1 \
  https://github.com/azerothcore/wiki.git "$PIN"

echo "Comparing pinned Git tree against CICS v2 copy..."

WIKI="$WIKI" GIT_DIR="$TMP/repo.git" PIN="$PIN" python - <<'PY'
import os, subprocess
from pathlib import Path

root = Path(os.environ["WIKI"])
git_dir = os.environ["GIT_DIR"]
pin = os.environ["PIN"]

raw = subprocess.check_output([
    "git", f"--git-dir={git_dir}", "ls-tree",
    "-r", "-z", pin
])

source = {}
for entry in raw.split(b"\0"):
    if not entry:
        continue
    meta, path = entry.split(b"\t", 1)
    mode, kind, oid = meta.decode().split()
    source[path] = (mode, oid)

identical, different, missing, extra = [], [], [], []

for path, (mode, oid) in source.items():
    local = root / os.fsdecode(path)
    if not local.is_file() and not local.is_symlink():
        missing.append(os.fsdecode(path))
        continue

    if mode == "120000":
        content = os.fsencode(os.readlink(local)) if local.is_symlink() else local.read_bytes()
    else:
        if local.is_symlink():
            different.append(os.fsdecode(path))
            continue
        content = local.read_bytes()

    import hashlib
    header = f"blob {len(content)}\0".encode()
    local_oid = hashlib.sha1(header + content).hexdigest()

    if local_oid == oid:
        identical.append(os.fsdecode(path))
    else:
        different.append(os.fsdecode(path))

source_paths = {os.fsdecode(p) for p in source}
for p in root.rglob("*"):
    if p.is_file() or p.is_symlink():
        rel = p.relative_to(root).as_posix()
        if rel not in source_paths:
            extra.append(rel)

print("\n========== EXACT PIN COMPARISON ==========")
print("Pinned commit:", pin)
print("Pinned Git paths:", len(source))
print("Identical files:", len(identical))
print("Different files:", len(different))
print("Missing files:", len(missing))
print("Additional CICS files:", len(extra))

print("\n========== DOCUMENTATION COUNTS ==========")
for label, collection in [
    ("Pinned docs/", [p for p in source if p.startswith(b"docs/")]),
    ("CICS docs/", list((root / "docs").rglob("*")) if (root / "docs").exists() else [])
]:
    count = sum(1 for p in collection if not isinstance(p, Path) or p.is_file())
    print(f"{label}: {count}")

for label, items in [
    ("DIFFERENT", different),
    ("MISSING", missing),
    ("ADDITIONAL", extra)
]:
    print(f"\n========== {label} FILES (first 25) ==========")
    for item in sorted(items)[:25]:
        print(item)
PY
```

**Interpretation:** if all pinned paths are identical and there are no missing files, the CICS v2 copy is an exact content recovery of the Engineering RAG snapshot, regardless of whether it has Git history. If there are differences, we'll quantify them and determine whether the copy can still serve as a recovery source.

## User

Fetching the exact Engineering RAG Wiki revision... \
Comparing pinned Git tree against CICS v2 copy... \
&#x20;\
\========== EXACT PIN COMPARISON ========== \
Pinned commit: 7d540fc7e683c3bf34a2f465789f1b3df268b609 \
Pinned Git paths: 1054 \
Identical files: 688 \
Different files: 103 \
Missing files: 263 \
Additional CICS files: 0 \
&#x20;\
\========== DOCUMENTATION COUNTS ========== \
Pinned docs/: 912 \
CICS docs/: 651 \
&#x20;\
\========== DIFFERENT FILES (first 25) ========== \
.gitignore \
docs/account.md \
docs/bugreport.md \
docs/channels_bans.md \
docs/character_achievement_progress.md \
docs/character_arena_stats.md \
docs/character_equipmentsets.md \
docs/character_gifts.md \
docs/character_instance.md \
docs/character_queststatus.md \
docs/character_queststatus_rewarded.md \
docs/character_spell_cooldown.md \
docs/common-errors.md \
docs/conditions.md \
docs/creature_formations.md \
docs/creature_respawn.md \
docs/creature_template.md \
docs/creature_text.md \
docs/database-auth.md \
docs/database-characters.md \
docs/database-world.md \
docs/documentation-index.md \
docs/es/ac-dashboard-core-installation.md \
docs/es/account.md \
docs/es/account_data.md \
&#x20;\
\========== MISSING FILES (first 25) ========== \
.github/workflows/assign-copilot-wiki-update.yml \
.github/workflows/copilot-pr-ready.yml \
docs/agentic-engineering.md \
docs/chat_filter.md \
docs/config-merger.md \
docs/creature_immunities.md \
docs/creature_text_option_sets.md \
docs/creature_text_options.md \
docs/es/ac-new-example.md \
docs/es/achievement_reward_locale.md \
docs/es/acore_string.md \
docs/es/active_arena_season.md \
docs/es/agentic-engineering.md \
docs/es/antidos_opcode_policies.md \
docs/es/areatrigger.md \
docs/es/areatrigger_involvedrelation.md \
docs/es/areatrigger_scripts.md \
docs/es/areatrigger_tavern.md \
docs/es/areatrigger_teleport.md \
docs/es/arena_season_reward.md \
docs/es/arena_season_reward_group.md \
docs/es/autobroadcast_locale.md \
docs/es/battleground_template.md \
docs/es/battlemaster_entry.md \
docs/es/broadcast_text.md \
&#x20;\
\========== ADDITIONAL FILES (first 25) ========== \
(**deck@ExosSteamDeck engineering-rag-corpus**)$ \
&#x20;\
&#x20;

## Assistant

This is a significant recovery lead. The CICS v2 copy is **not an exact copy** of the Engineering RAG acquisition: it contains 688 files identical to the pinned revision, 103 differing files, and is missing 263 files. Its 651 documentation files also fall short of the pinned revision’s 912.

That means it preserves a substantial portion of the same AzerothCore Wiki source, but we must not substitute it wholesale for the original 1,054-file snapshot or treat it as the exact July 21 acquisition.

I was looking for the AzerothCore source because the Engineering RAG repository's acquisition records point to that Wiki as its original external input, and we were investigating whether the missing snapshot survived on the old drive. I should have made that connection explicit before sending you through the searches.

### What this comparison establishes

| Measure | Result |
|---|---:|
| Files in exact pinned revision | 1,054 |
| Files in CICS v2 copy | 791 |
| Byte-identical files | 688 |
| Existing but different files | 103 |
| Files absent from CICS v2 copy | 263 |
| Extra files in CICS v2 copy | 0 |
| Documentation files in pinned revision | 912 |
| Documentation files in CICS v2 copy | 651 |

The CICS v2 copy is a **partial, modified copy of the same upstream Wiki**. It is not an unrelated corpus. However, the comparison does not establish whether its differences came from a different upstream revision, local edits, or selective processing.

### Implications for Engineering RAG

1. **We found a substantial surviving source copy.** The 688 identical files are usable as verified copies of their counterparts in the pinned revision.
2. **We have not recovered the original acquisition snapshot.** The 103 modified and 263 missing files prevent treating this directory as an exact replacement.
3. **We should preserve the CICS copy in place.** Do not overwrite, normalize, or merge into it.
4. **The exact pinned revision remains recoverable from its upstream Git commit**, assuming the repository still serves that commit. We can reacquire it as a separately documented recovery, verify its inventory against the historical SHA-256, and keep the CICS copy as an independent source artifact.

The next useful forensic step is to inspect the 103 differing files and establish whether they represent later revisions, older content, or local modifications. That will tell us more about the CICS copy's provenance—and whether it contains any useful material beyond the exact pinned snapshot.

## User

lets keep going till we resolve the incosistencies

## Assistant

We'll continue until the discrepancies are accounted for, not just until we find a plausible replacement.

The next step is to classify the **103 differing files**. For each, we need to determine whether the CICS v2 version is:

- an older version of the pinned document;
- a newer upstream version;
- locally modified;
- structurally transformed or truncated;
- or different for another identifiable reason.

We should also establish the CICS copy's own provenance: when it was acquired, from which revision, and whether any processing was applied.

**One detail I need before giving you the next command:** did the comparison script retain the exact pinned Git checkout on disk? If so, what is its directory path? If it did not, we'll recreate it at the exact pinned commit and make the comparison reproducible.

## User

I'm not sure. lets recreate

## Assistant

We'll recreate a clean, detached checkout of the exact recorded upstream commit. This will be separate from both the CICS v2 copy and your Engineering RAG repository. It will not modify either one.

Run this in Konsole:

```bash
set -euo pipefail

REPO_URL="https://github.com/azerothcore/wiki.git"
PINNED_COMMIT="7d540fc7e683c3bf34a2f465789f1b3df268b609"
DEST="$HOME/Downloads/azerothcore-wiki-pinned-$PINNED_COMMIT"

echo "========== CHECK DESTINATION =========="
if [ -e "$DEST" ]; then
    echo "STOP: Destination already exists: $DEST"
    exit 1
fi

mkdir -p "$(dirname "$DEST")"

echo
echo "========== FETCH EXACT UPSTREAM REVISION =========="
git init "$DEST"
git -C "$DEST" remote add origin "$REPO_URL"
git -C "$DEST" fetch --depth=1 origin "$PINNED_COMMIT"
git -C "$DEST" checkout --detach FETCH_HEAD

echo
echo "========== VERIFY CHECKOUT =========="
ACTUAL="$(git -C "$DEST" rev-parse HEAD)"
printf 'Expected: %s\nActual:   %s\n' "$PINNED_COMMIT" "$ACTUAL"

if [ "$ACTUAL" != "$PINNED_COMMIT" ]; then
    echo "ERROR: Commit verification failed."
    exit 1
fi

printf 'Tracked files: '
git -C "$DEST" ls-files | wc -l

printf 'Documentation files: '
git -C "$DEST" ls-files docs/ | wc -l

printf 'Working tree: '
if [ -z "$(git -C "$DEST" status --porcelain)" ]; then
    echo "CLEAN"
else
    echo "NOT CLEAN"
    git -C "$DEST" status --short
    exit 1
fi

echo
echo "Pinned checkout: $DEST"
echo "========== COMPLETE =========="
```

This uses a shallow fetch of the exact commit rather than downloading the repository's entire history. The checkout should verify as commit `7d540fc7...` and contain the historical 1,054 tracked files.

Send me the output. Then we'll use this checkout to reproduce the comparison, classify all 103 differences, and investigate the 263 missing files.

## User

\========== CHECK DESTINATION ========== \
&#x20;\
\========== FETCH EXACT UPSTREAM REVISION ========== \
hint: Using 'master' as the name for the initial branch. This default branch name \
hint: will change to "main" in Git 3.0. To configure the initial branch name \
hint: to use in all of your new repositories, which will suppress this warning, \
hint: call: \
hint: \
hint:   git config --global init.defaultBranch \<name> \
hint: \
hint: Names commonly chosen instead of 'master' are 'main', 'trunk' and \
hint: 'development'. The just-created branch can be renamed via this command: \
hint: \
hint:   git branch -m \<name> \
hint: \
hint: Disable this message with "git config set advice.defaultBranchName false" \
Initialized empty Git repository in /home/deck/Downloads/azerothcore-wiki-pinned-7d540fc7e683c3bf34a2f465789f1b3df268b609/.git/ \
remote: Enumerating objects: 1081, done. \
remote: Counting objects: 100% (1081/1081), done. \
remote: Compressing objects: 100% (877/877), done. \
remote: Total 1081 (delta 379), reused 583 (delta 197), pack-reused 0 (from 0) \
Receiving objects: 100% (1081/1081), 12.16 MiB | 3.60 MiB/s, done. \
Resolving deltas: 100% (379/379), done. \
From [https://github.com/azerothcore/wiki](https://github.com/azerothcore/wiki) \
&#x20;\* branch            7d540fc7e683c3bf34a2f465789f1b3df268b609 -> FETCH_HEAD \
HEAD is now at 7d540fc docs(account): document implemented ACCOUNT_FLAG_COLLECTOR behavior in EN/ES (#1250) \
&#x20;\
\========== VERIFY CHECKOUT ========== \
Expected: 7d540fc7e683c3bf34a2f465789f1b3df268b609 \
Actual:   7d540fc7e683c3bf34a2f465789f1b3df268b609 \
Tracked files: 1054 \
Documentation files: 912 \
Working tree: CLEAN \
&#x20;\
Pinned checkout: /home/deck/Downloads/azerothcore-wiki-pinned-7d540fc7e683c3bf34a2f465789f1b3df268b609 \
\========== COMPLETE ========== \
(**deck@ExosSteamDeck engineering-rag-corpus**)$ \
&#x20;\
&#x20;

## Assistant

The recovery succeeded. We now have an independently verified reference checkout:

<badge color="success">Verified</badge> **Exact pinned revision restored**

| Check | Result |
|---|---:|
| Commit | `7d540fc7e683c3bf34a2f465789f1b3df268b609` |
| Tracked files | 1,054 |
| `docs/` files | 912 |
| Working tree | Clean |
| Checkout | `/home/deck/Downloads/azerothcore-wiki-pinned-7d540fc7e683c3bf34a2f465789f1b3df268b609` |

One important distinction: this verifies the recreated checkout against the recorded commit. It does **not** establish that this is the original July 21 acquisition directory or prove when the CICS copy was made.

## Next: reproduce and deepen the comparison

Let's generate a file-level report, not just totals. It will show every path as identical, different, or missing, with file sizes and SHA-256 hashes. It will not modify either source tree.

Run:

```bash
python3 - <<'PY'
from pathlib import Path
import hashlib
import csv

pinned = Path.home() / "Downloads/azerothcore-wiki-pinned-7d540fc7e683c3bf34a2f465789f1b3df268b609"
cics = Path("/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki")
report = Path.home() / "Downloads/azerothcore-cics-exact-comparison.csv"

def inventory(root):
    result = {}
    for path in root.rglob("*"):
        if path.is_file() and ".git" not in path.parts:
            rel = path.relative_to(root).as_posix()
            data = path.read_bytes()
            result[rel] = (len(data), hashlib.sha256(data).hexdigest())
    return result

print("Building inventories...")
a = inventory(pinned)
b = inventory(cics)

rows = []
counts = {"IDENTICAL": 0, "DIFFERENT": 0, "MISSING": 0, "ADDITIONAL": 0}

for rel in sorted(set(a) | set(b)):
    if rel not in b:
        status = "MISSING"
    elif rel not in a:
        status = "ADDITIONAL"
    elif a[rel][1] == b[rel][1]:
        status = "IDENTICAL"
    else:
        status = "DIFFERENT"

    counts[status] += 1
    rows.append([
        status, rel,
        a.get(rel, ("", ""))[0], b.get(rel, ("", ""))[0],
        a.get(rel, ("", ""))[1], b.get(rel, ("", ""))[1]
    ])

with report.open("w", newline="", encoding="utf-8") as f:
    writer = csv.writer(f)
    writer.writerow(["status", "path", "pinned_bytes", "cics_bytes", "pinned_sha256", "cics_sha256"])
    writer.writerows(rows)

print("\n========== COMPARISON ==========")
print(f"Pinned files: {len(a)}")
print(f"CICS files:   {len(b)}")
for status, count in counts.items():
    print(f"{status:10}: {count}")

print("\n========== DIFFERENCE SIZE PATTERNS ==========")
diffs = [r for r in rows if r[0] == "DIFFERENT"]
same_size = sum(1 for r in diffs if r[2] == r[3])
cics_smaller = sum(1 for r in diffs if r[3] < r[2])
cics_larger = sum(1 for r in diffs if r[3] > r[2])
print(f"Different files with same byte size: {same_size}")
print(f"CICS copy smaller:                  {cics_smaller}")
print(f"CICS copy larger:                   {cics_larger}")

print("\n========== DIFFERENT FILES ==========")
for r in diffs:
    print(f"{r[1]} | pinned={r[2]} bytes | CICS={r[3]} bytes")

print("\n========== REPORT ==========")
print(report)
PY
```

Send me the output, especially the 103 differing paths and size patterns. That will let us distinguish likely edits from truncation, format conversion, and version drift. After that, we'll inspect representative diffs and determine whether the 263 missing files are omissions from an older snapshot, deliberate exclusions, or a copying failure.

## User

Building inventories... \
&#x20;\
\========== COMPARISON ========== \
Pinned files: 1054 \
CICS files:   791 \
IDENTICAL : 688 \
DIFFERENT : 103 \
MISSING   : 263 \
ADDITIONAL: 0 \
&#x20;\
\========== DIFFERENCE SIZE PATTERNS ========== \
Different files with same byte size: 7 \
CICS copy smaller:                  56 \
CICS copy larger:                   40 \
&#x20;\
\========== DIFFERENT FILES ========== \
.gitignore | pinned=74 bytes | CICS=66 bytes \
docs/account.md | pinned=11308 bytes | CICS=11036 bytes \
docs/bugreport.md | pinned=1200 bytes | CICS=764 bytes \
docs/channels_bans.md | pinned=818 bytes | CICS=772 bytes \
docs/character_achievement_progress.md | pinned=1124 bytes | CICS=1077 bytes \
docs/character_arena_stats.md | pinned=1250 bytes | CICS=1192 bytes \
docs/character_equipmentsets.md | pinned=3934 bytes | CICS=3798 bytes \
docs/character_gifts.md | pinned=1137 bytes | CICS=1094 bytes \
docs/character_instance.md | pinned=1334 bytes | CICS=1252 bytes \
docs/character_queststatus.md | pinned=3792 bytes | CICS=3719 bytes \
docs/character_queststatus_rewarded.md | pinned=1065 bytes | CICS=995 bytes \
docs/character_spell_cooldown.md | pinned=1573 bytes | CICS=1509 bytes \
docs/common-errors.md | pinned=12098 bytes | CICS=12100 bytes \
docs/conditions.md | pinned=130580 bytes | CICS=52201 bytes \
docs/creature_formations.md | pinned=4173 bytes | CICS=4197 bytes \
docs/creature_respawn.md | pinned=1675 bytes | CICS=1646 bytes \
docs/creature_template.md | pinned=62750 bytes | CICS=67164 bytes \
docs/creature_text.md | pinned=10150 bytes | CICS=9812 bytes \
docs/database-auth.md | pinned=815 bytes | CICS=560 bytes \
docs/database-characters.md | pinned=4236 bytes | CICS=4170 bytes \
docs/database-world.md | pinned=8719 bytes | CICS=8449 bytes \
docs/documentation-index.md | pinned=2904 bytes | CICS=2806 bytes \
docs/es/ac-dashboard-core-installation.md | pinned=8763 bytes | CICS=7732 bytes \
docs/es/account.md | pinned=11915 bytes | CICS=8078 bytes \
docs/es/account_data.md | pinned=1240 bytes | CICS=1248 bytes \
docs/es/account_muted.md | pinned=1799 bytes | CICS=1807 bytes \
docs/es/character_achievement_progress.md | pinned=1127 bytes | CICS=1078 bytes \
docs/es/character_gifts.md | pinned=1180 bytes | CICS=1133 bytes \
docs/es/character_queststatus_rewarded.md | pinned=1123 bytes | CICS=1026 bytes \
docs/es/character_spell_cooldown.md | pinned=1681 bytes | CICS=1599 bytes \
docs/es/classic-installation.md | pinned=1587 bytes | CICS=1772 bytes \
docs/es/client-setup.md | pinned=1750 bytes | CICS=1706 bytes \
docs/es/cmake-options.md | pinned=863 bytes | CICS=868 bytes \
docs/es/common-errors.md | pinned=10523 bytes | CICS=10304 bytes \
docs/es/config-overrides-with-env-var.md | pinned=835 bytes | CICS=841 bytes \
docs/es/contribute.md | pinned=3035 bytes | CICS=3051 bytes \
docs/es/core-installation.md | pinned=1118 bytes | CICS=1133 bytes \
docs/es/creating-accounts.md | pinned=1758 bytes | CICS=1427 bytes \
docs/es/database-installation.md | pinned=2518 bytes | CICS=2661 bytes \
docs/es/faq.md | pinned=8844 bytes | CICS=9462 bytes \
docs/es/final-server-steps.md | pinned=3006 bytes | CICS=3029 bytes \
docs/es/how-to-ask-for-help.md | pinned=3592 bytes | CICS=5141 bytes \
docs/es/how-to-restart-and-debug.md | pinned=3205 bytes | CICS=5041 bytes \
docs/es/how-to-test-a-pr.md | pinned=9037 bytes | CICS=9049 bytes \
docs/es/installation.md | pinned=1801 bytes | CICS=2890 bytes \
docs/es/item_instance_enchantments.md | pinned=2426 bytes | CICS=2844 bytes \
docs/es/item_loot_storage.md | pinned=2781 bytes | CICS=2835 bytes \
docs/es/keeping-the-server-up-to-date.md | pinned=1553 bytes | CICS=1562 bytes \
docs/es/lfg_data.md | pinned=894 bytes | CICS=897 bytes \
docs/es/linux-core-installation.md | pinned=7678 bytes | CICS=6241 bytes \
docs/es/linux-keeping-the-server-up-to-date.md | pinned=2591 bytes | CICS=3128 bytes \
docs/es/linux-requirements.md | pinned=4643 bytes | CICS=5800 bytes \
docs/es/macos-core-installation.md | pinned=4395 bytes | CICS=4461 bytes \
docs/es/macos-requirements.md | pinned=2163 bytes | CICS=3141 bytes \
docs/es/networking.md | pinned=4547 bytes | CICS=3054 bytes \
docs/es/pool_quest_save.md | pinned=680 bytes | CICS=683 bytes \
docs/es/quest_tracker.md | pinned=1757 bytes | CICS=1759 bytes \
docs/es/requirements.md | pinned=1248 bytes | CICS=1122 bytes \
docs/es/server-setup.md | pinned=1187 bytes | CICS=8868 bytes \
docs/es/spell.md | pinned=12501 bytes | CICS=12581 bytes \
docs/es/windows-core-installation.md | pinned=5879 bytes | CICS=6316 bytes \
docs/es/windows-keeping-the-server-up-to-date.md | pinned=1693 bytes | CICS=1619 bytes \
docs/es/windows-requirements.md | pinned=6400 bytes | CICS=8374 bytes \
docs/es/windows-server-setup.md | pinned=7168 bytes | CICS=3584 bytes \
docs/exploration_basexp.md | pinned=636 bytes | CICS=636 bytes \
docs/faction.md | pinned=91640 bytes | CICS=91749 bytes \
docs/gameobject_addon.md | pinned=2470 bytes | CICS=1214 bytes \
docs/gameobject_respawn.md | pinned=1799 bytes | CICS=1768 bytes \
docs/gameobject_template_addon.md | pinned=3715 bytes | CICS=3727 bytes \
docs/getting-started.md | pinned=13181 bytes | CICS=13181 bytes \
docs/gm-commands.md | pinned=514097 bytes | CICS=414310 bytes \
docs/graveyard_zone.md | pinned=1325 bytes | CICS=1287 bytes \
docs/install-with-docker.md | pinned=19632 bytes | CICS=19633 bytes \
docs/instance.md | pinned=1891 bytes | CICS=1771 bytes \
docs/item_template.md | pinned=70918 bytes | CICS=67481 bytes \
docs/itempurchasegroup_dbc.md | pinned=4268 bytes | CICS=4309 bytes \
docs/itemset_dbc.md | pinned=10221 bytes | CICS=10230 bytes \
docs/keira3-internals.md | pinned=33998 bytes | CICS=16061 bytes \
docs/linux-requirements.md | pinned=5424 bytes | CICS=5011 bytes \
docs/linux-server-setup.md | pinned=7880 bytes | CICS=7880 bytes \
docs/macos-server-setup.md | pinned=7185 bytes | CICS=7185 bytes \
docs/mail_level_reward.md | pinned=1141 bytes | CICS=1049 bytes \
docs/mail_server_character.md | pinned=932 bytes | CICS=932 bytes \
docs/mail_server_template.md | pinned=2315 bytes | CICS=1615 bytes \
docs/mail_server_template_conditions.md | pinned=5013 bytes | CICS=3530 bytes \
docs/monitoring-azerothcore-with-grafana.md | pinned=6028 bytes | CICS=6024 bytes \
docs/mysqltypescpp.md | pinned=5669 bytes | CICS=11100 bytes \
docs/pool_quest.md | pinned=959 bytes | CICS=917 bytes \
docs/quest_template_addon.md | pinned=10452 bytes | CICS=9772 bytes \
docs/secret_digest.md | pinned=597 bytes | CICS=562 bytes \
docs/skill_discovery_template.md | pinned=1902 bytes | CICS=1831 bytes \
docs/smart_scripts.md | pinned=291427 bytes | CICS=285770 bytes \
docs/spawn_group.md | pinned=1315 bytes | CICS=1078 bytes \
docs/spawn_group_template.md | pinned=3168 bytes | CICS=2560 bytes \
docs/spell-aura-reference.md | pinned=14835 bytes | CICS=14825 bytes \
docs/transports.md | pinned=1430 bytes | CICS=1374 bytes \
docs/vsc-requirements.md | pinned=4190 bytes | CICS=4224 bytes \
docs/waypoint_data.md | pinned=4794 bytes | CICS=3326 bytes \
docs/windows-core-installation.md | pinned=5986 bytes | CICS=5986 bytes \
docs/windows-keeping-the-server-up-to-date.md | pinned=2037 bytes | CICS=2002 bytes \
docs/windows-requirements.md | pinned=6862 bytes | CICS=6898 bytes \
docs/windows-server-setup.md | pinned=7231 bytes | CICS=7248 bytes \
docs/windows-vsc-core-installation.md | pinned=5143 bytes | CICS=5143 bytes \
&#x20;\
\========== REPORT ========== \
/home/deck/Downloads/azerothcore-cics-exact-comparison.csv \
(**deck@ExosSteamDeck engineering-rag-corpus**)$ \
&#x20;\
&#x20;

## Assistant

The reproduced comparison confirms the earlier counts exactly. More importantly, the size pattern rules out a simple explanation such as “the CICS copy was just truncated.”

- **688 files** are byte-for-byte identical to the pinned revision.
- **103 files** differ; 56 are smaller in CICS and 40 are larger. Seven have identical byte counts but different content.
- **263 files** from the pinned revision are absent.
- **No CICS-only paths** exist.

The differences are mixed: some documents are substantially shorter, some longer, and some nearly identical in size. That points to a combination of version drift and possible file-specific edits or incomplete copies. It does not yet tell us which.

A few files deserve priority because their size differences are unusually large: `conditions.md`, `gm-commands.md`, `keira3-internals.md`, `mysqltypescpp.md`, and `docs/es/windows-server-setup.md`. We should inspect actual content before assigning causes.

## Next: inspect the actual content differences

Run this read-only comparison. It reports line counts and change ratios, then prints a bounded unified diff for the largest discrepancies and several representative files. It will not alter either tree.

```bash
python3 - <<'PY'
from pathlib import Path
import difflib

pinned = Path.home() / "Downloads/azerothcore-wiki-pinned-7d540fc7e683c3bf34a2f465789f1b3df268b609"
cics = Path("/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki")

targets = [
    ".gitignore",
    "docs/conditions.md",
    "docs/gm-commands.md",
    "docs/keira3-internals.md",
    "docs/mysqltypescpp.md",
    "docs/es/windows-server-setup.md",
    "docs/account.md",
    "docs/common-errors.md",
    "docs/creature_template.md",
    "docs/es/how-to-ask-for-help.md",
    "docs/es/installation.md",
    "docs/server-setup.md",
]

print("========== FILE-LEVEL ANALYSIS ==========")
for rel in targets:
    a_path, b_path = pinned / rel, cics / rel
    if not a_path.exists() or not b_path.exists():
        print(f"\n{rel}: missing from one side")
        continue

    a = a_path.read_text(encoding="utf-8", errors="replace").splitlines()
    b = b_path.read_text(encoding="utf-8", errors="replace").splitlines()
    ratio = difflib.SequenceMatcher(None, a, b, autojunk=False).ratio()
    diff = list(difflib.unified_diff(
        a, b,
        fromfile="PINNED/" + rel,
        tofile="CICS/" + rel,
        lineterm="",
        n=2
    ))

    print(f"\n--- {rel} ---")
    print(f"Pinned lines: {len(a)} | CICS lines: {len(b)} | Similarity: {ratio:.1%}")
    print(f"Diff lines: {len(diff)}")
    for line in diff[:55]:
        print(line)
    if len(diff) > 55:
        print(f"... {len(diff) - 55} additional diff lines omitted")

print("\n========== END ==========")
PY
```

### What this should establish

1. **Version drift:** whether CICS contains coherent older or newer document content.
2. **Truncation:** whether shorter files end abruptly or simply omit sections.
3. **Local edits:** whether changes look like project-specific modifications rather than upstream changes.
4. **Translation drift:** whether the Spanish files reflect a different translation revision from the English files.

After this, we should inspect the CICS acquisition/synchronization scripts and the `blaine-azerothcore` execution records. Those may establish where this copy came from and whether it was ever intended to be a complete upstream snapshot.

## User

\========== FILE-LEVEL ANALYSIS ==========\
\
\--- .gitignore ---\
Pinned lines: 9 | CICS lines: 8 | Similarity: 94.1%\
Diff lines: 6\
\--- PINNED/.gitignore\
+++ CICS/.gitignore\
@@ -7,3 +7,2 @@\
&#x20;.idea/\*\
&#x20;\
-.claude\
\
\--- docs/conditions.md ---\
Pinned lines: 693 | CICS lines: 1554 | Similarity: 39.0%\
Diff lines: 1723\
\--- PINNED/docs/conditions.md\
+++ CICS/docs/conditions.md\
@@ -9,21 +9,202 @@\
&#x20;\*\*Table Structure\*\*\
&#x20;\
\-| Field                                                 | Type               | Null | Key | Default | Extra | Comment                                                                          |\
\-| ----------------------------------------------------- | ------------------ | ---- | --- | ------- | ----- | -------------------------------------------------------------------------------- |\
\-| [SourceTypeOrReferenceId]\(#sourcetypeorreferenceid)   | MEDIUMINT SIGNED   | NO   | PRI | 0       |       |                                                                                  |\
\-| [SourceGroup]\(#sourcegroup)                           | MEDIUMINT UNSIGNED | NO   | PRI | 0       |       |                                                                                  |\
\-| [SourceEntry]\(#sourceentry)                           | MEDIUMINT SIGNED   | NO   | PRI | 0       |       |                                                                                  |\
\-| [SourceId]\(#condition_source_type_smart_event=22)     | INT SIGNED         | NO   | PRI | 0       |       | [smart_scripts.source_type]\(smart_scripts#sourcetype) \\|\\| 0 for everything else |\
\-| [ElseGroup]\(#elsegroup)                               | MEDIUMINT UNSIGNED | NO   | PRI | 0       |       |                                                                                  |\
\-| [ConditionTypeOrReference]\(#conditiontypeorreference) | MEDIUMINT SIGNED   | NO   | PRI | 0       |       |                                                                                  |\
\-| [ConditionTarget]\(#conditiontarget)                   | TINYINT UNSIGNED   | NO   | PRI | 0       |       |                                                                                  |\
\-| [ConditionValue1]\(#conditionvalue1)                   | INT UNSIGNED       | NO   | PRI | 0       |       |                                                                                  |\
\-| [ConditionValue2]\(#conditionvalue2)                   | INT UNSIGNED       | NO   | PRI | 0       |       |                                                                                  |\
\-| [ConditionValue3]\(#conditionvalue3)                   | INT UNSIGNED       | NO   | PRI | 0       |       |                                                                                  |\
\-| [NegativeCondition]\(#negativecondition)               | TINYINT UNSIGNED   | NO   |     | 0       |       | Boolean 0 or 1 (if [NegativeCondition]\(#negativecondition))                      |\
\-| [ErrorType]\(#errortype)                               | MEDIUMINT UNSIGNED | NO   |     | 0       |       |                                                                                  |\
\-| [ErrorTextId]\(#errortextid)                           | MEDIUMINT UNSIGNED | NO   |     | 0       |       |                                                                                  |\
\-| [ScriptName]\(#scriptname)                             | char(64) SIGNED    | NO   |     | ' '     |       |                                                                                  |\
\-| [Comment]\(#comment)                                   | VARCHAR(255)       | YES  |     | NULL    |       |                                                                                  |\
+\<table>\
+\<tbody>\
+\<tr class="odd">\
+\<td>\<p>\<strong>Field\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Type\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Attributes\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Key\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Null\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Default\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Extra\</strong>\</p>\</td>\
+\<td>\<p>\<strong>Comment\</strong>\</p>\</td>\
+\</tr>\
+\<tr class="even">\
+\<td>\<p>\<a href="#sourcetypeorreferenceid">SourceTypeOrReferenceId\</a>\</p>\</td>\
+\<td>\<p>MEDIUMINT\</p>\</td>\
+\<td>\<p>SIGNED\</p>\</td>\
+\<td>\<p>PRI\</p>\</td>\
+\<td>\<p>NO\</p>\</td>\
+\<td>\<p>0\</p>\</td>\
+\<td>\<p>\<br />\
+\</p>\</td>\
+\<td>\<p>\<br />\
+\</p>\</td>\
+\</tr>\
+\<tr class="odd">\
+\<td>\<p>\<a href="#sourcegroup">SourceGroup\</a>\</p>\</td>\
+\<td>\<p>MEDIUMINT\</p>\</td>\
+\<td>\<p>UNSIGNED\</p>\</td>\
+\<td>\<p>PRI\</p>\</td>\
+\<td>\<p>NO\</p>\</td>\
+\<td>\<p>0\</p>\</td>\
+\<td>\<p>\<br />\
+\</p>\</td>\
... 1668 additional diff lines omitted\
\
\--- docs/gm-commands.md ---\
Pinned lines: 721 | CICS lines: 583 | Similarity: 89.1%\
Diff lines: 455\
\--- PINNED/docs/gm-commands.md\
+++ CICS/docs/gm-commands.md\
@@ -14,23 +14,14 @@\
&#x20;\| ------------------------------------ | -------- | --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |\
&#x20;\| account addon                        | 1        | \`.account addon #addon\`                                                                             | Set expansion addon level allowed. Addon values: 0 - normal, 1 - tbc, 2 - wotlk.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |\
\-| account 2fa                          | 0        | \`.account 2fa \<setup/remove>\`                                                                       | Type .account 2fa to see the list of possible subcommands or .help account 2fa $subcommand to see info on subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |\
&#x20;\| account 2fa setup                    | 0        | \`.account 2fa setup\`                                                                                | Setup 2fa authentication. Use .account 2fa setup 1 to receive token. Apply token to authenticator app (case sensitive). Use the pin from app with .account 2fa setup PIN to confirm setup.                                                                                                                                                                                                                                                                                                                                                                                              |\
&#x20;\| account 2fa remove                   | 0        | \`.account 2fa remove\`                                                                               | Remove 2fa authentication.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |\
&#x20;\| account create                       | 4        | \`.account create $account $password [$email]\`                                                         | Create account and set password to it, with email as optional value.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |\
&#x20;\| account delete                       | 4        | \`.account delete $account\`                                                                          | Delete account with all characters.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
\-| account flag                         | 2        | \`.account flag $subcommand\`                                                                         | Type .account flag to see the list of possible subcommands or .help account flag $subcommand to see info on subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |\
\-| account flag list                    | 2        | \`.account flag list [$account]\`                                                                     | Lists every AccountFlag currently set on $account. Defaults to your own account when no argument is given.                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |\
\-| account flag add                     | 3        | \`.account flag add $account $flag\`                                                                  | Sets an AccountFlag on $account. $flag is a symbolic name in either its full form (e.g. ACCOUNT_FLAG_TRIAL) or short form (e.g. TRIAL). ACCOUNT_FLAG_GM is managed automatically and cannot be changed manually.                                                                                                                                                                                                                                                                                                                                                                        |\
\-| account flag remove                  | 3        | \`.account flag remove $account $flag\`                                                               | Clears an AccountFlag on $account. $flag is a symbolic name in either its full form (e.g. ACCOUNT_FLAG_TRIAL) or short form (e.g. TRIAL). ACCOUNT_FLAG_GM is managed automatically and cannot be changed manually.                                                                                                                                                                                                                                                                                                                                                                      |\
&#x20;\| account lock country                 | 0        | \`.account lock country [on/off]\`                                                                    | Allow login from account only from current used Country or remove this requirement.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
\-| account lock ip                      | 0        | \`.account lock ip [on/off]\`                                                                         | Allow login from account only from current used IP or remove this requirement.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |\
&#x20;\| account lock                         | 0        | \`.account lock [on/off]\`                                                                            | Allow login from account only from current used IP or remove this requirement.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |\
&#x20;\| account onlinelist                   | 4        | \`.account onlinelist\`                                                                               | Show list of online accounts.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |\
&#x20;\| account password                     | 0        | \`.account password $old_password $new_password $new_password\`                                       | Change your account password.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |\
\-| account remove country               | 3        | \`.account remove country \<account>\`                                                                 | Removes the country information associated with the specified account.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |\
\-| account set 2fa                      | 0        | \`.account set 2fa \<account> \<secret/off>\`                                                           | Provide a base32 encoded secret to setup two-factor authentication for the account. Specify 'off' to disable two-factor authentication for the account.                                                                                                                                                                                                                                                                                                                                                                                                                                 |\
&#x20;\| account set addon                    | 2        | \`.account set addon [$account] #addon\`                                                              | Set user (possible targeted) expansion addon level allowed. Addon values: 0 - normal, 1 - tbc, 2 - wotlk.                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |\
&#x20;\| account set gmlevel                  | 4        | \`.account set gmlevel [$account] #level [#realmid]\`                                                 | Set the security level for targeted player (can't be used at self) or for account $name to a level of #level on the realm #realmID. #level may range from 0 to 3. #reamID may be -1 for all realms.                                                                                                                                                                                                                                                                                                                                                                                     |\
\-| account set email                    | 3        | \`.account set email $account $email $email_confirmation\`                                            | Add or change an email to the account.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |\
&#x20;\| account set password                 | 4        | \`.account set password $account $password $password\`                                                | Set password for account.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |\
&#x20;\| account set                          | 2        | \`.account set $subcommand\`                                                                          | Type .account set to see the list of possible subcommands or .help account set $subcommand to see info on subcommands                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |\
@@ -55,9 +46,4 @@\
&#x20;\| aura                                 | 2        | \`.aura #spellid\`                                                                                    | Add the aura from spell #spellid to the selected Unit.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |\
&#x20;\| aura stack                           | 2        | \`.aura stack #spellid #stacks\`                                                                      | Modify #stacks of an already applied #spellid to the selected Unit.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
\-| autobroadcast                        | 2        | \`.autobroadcast $subcommand\`                                                                        | Type .autobroadcast to see a list of subcommands or .help autobroadcast $subcommand to see info on subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
\-| autobroadcast add                    | 3        | \`.autobroadcast add $weight $text\`                                                                  | Add a new autobroadcast entry with the given weight and text.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |\
\-| autobroadcast list                   | 2        | \`.autobroadcast list\`                                                                               | List all autobroadcast entries.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
\-| autobroadcast locale                 | 3        | \`.autobroadcast locale $id $locale $text\`                                                           | Add or replace a localized text for the autobroadcast entry with the given ID.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |\
\-| autobroadcast remove                 | 3        | \`.autobroadcast remove $id\`                                                                         | Remove the autobroadcast entry with the given ID and its locale entries.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |\
&#x20;\| bags                                 | 2        | \`.bags $subcommand\`                                                                                 | Type .bags to see a list of all subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |\
&#x20;\| bags clear                           | 2        | \`.bags clear $itemquality\`                                                                          | Clear from players' bags all items including and below $itemQuality.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |\
@@ -76,7 +62,5 @@\
&#x20;\| banlist ip                           | 2        | \`.banlist ip [$Ip]\`                                                                                 | Searches the banlist for a IP pattern or show full list of IP bans.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
&#x20;\| banlist                              | 2        | \`.banlist $subcommand\`                                                                              | Type .banlist to see the list of possible subcommands or .help banlist $subcommand to see info on subcommands                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |\
\-| bf                                   | 3        | \`.bf $subcommand\`                                                                                   | Type .bf to see the list of possible subcommands or .help bf $subcommand to see info on subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |\
&#x20;\| bf enable                            | 3        | \`.bf enable #battleid\`                                                                              |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
\-| bf queue                             | 2        | \`.bf queue #battleid\`                                                                               | Displays all players currently in queue, invited, or actively in war for the specified battlefield. #battleid: the battle ID (e.g. 1 for Wintergrasp).                                                                                                                                                                                                                                                                                                                                                                                                                                  |\
&#x20;\| bf start                             | 3        | \`.bf start #battleid\`                                                                               |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
&#x20;\| bf stop                              | 3        | \`.bf stop #battleid\`                                                                                |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
@@ -84,5 +68,4 @@\
&#x20;\| bf timer                             | 3        | \`.bf timer #battleid #timer\`                                                                        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |\
&#x20;\| bindsight                            | 3        | \`.bindsight\`                                                                                        | Binds vision to the selected unit indefinitely. Cannot be used while currently possessing a target.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
\-| bm                                   | 2        | \`.bm [on/off]\`                                                                                      | Enable or Disable in game Beastmaster mode or show current state if on/off not provided.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |\
&#x20;\| cache                                | 2        | \`.cache $subcommand\`                                                                                | Character data cached during start up. Type .cache to see a list of subcommands or .help $subcommand to see info on subcommands.                                                                                                                                                                                                                                                                                                                                                                                                                                                        |\
&#x20;\| cache delete                         | 3        | \`.cache delete $playername\`                                                                         | Deletes the cached data for the selected character. Use for debugging only!                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |\
@@ -95,5 +78,4 @@\
&#x20;\| cast target                          | 2        | \`.cast target #spellid [triggered]\`                                                                 | Selected target will cast #spellid to his victim. If 'trigered' or part provided then spell casted with triggered flag.                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |\
&#x20;\| cast                                 | 2        | \`.cast #spellid [triggered]\`                                                                        | Cast #spellid to selected target. If no target selected cast to self. If 'trigered' or part provided then spell casted with triggered flag.                                                                                                                                                                                                                                                                                                                                                                                                                                             |\
\-| character                            | 2        | \`.character $subcommand\`                                                                            | Type .character to see a list of possible subcommands or .help character $subcommand to see info on the subcommand.                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
&#x20;\| character changeaccount              | 3        | \`.character changeaccount $NewAccountNAme $Name\`                                                    | Moves the specified character to the provided account. Kicks the player if the character is online.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |\
... 400 additional diff lines omitted\
\
\--- docs/keira3-internals.md ---\
Pinned lines: 526 | CICS lines: 258 | Similarity: 32.9%\
Diff lines: 717\
\--- PINNED/docs/keira3-internals.md\
+++ CICS/docs/keira3-internals.md\
@@ -3,5 +3,5 @@\
&#x20;This is a collection of notes aiming to explain the internals of Keira3 for development purposes.\
&#x20;\
-If you just want to \*use\* Keira3, you don't need any of the following — head to the [Keira3 website]\(https\://www\.azerothcore.org/Keira3/) instead.\
+If you just want to use Keira3, you don't need any of the following. If you want to modify Keira3, for example to improve it or to add new features, you may find this page useful.\
&#x20;\
&#x20;\## Main technologies\
@@ -9,30 +9,26 @@\
&#x20;Keira3 is built upon the following open source web technologies:\
&#x20;\
\-- [\*\*TypeScript\*\*]\(http\://www\.typescriptlang.org/) is the main language of Keira3. It is a superset of JavaScript.\
\-  If you know JavaScript and have some basic knowledge of OOP languages like Java and C#, you will feel pretty familiar with TypeScript already.\
\-  Otherwise, you might find [this course]\(https\://www\.udemy.com/course/understanding-typescript/) helpful.\
\-  If you don't know JavaScript at all, it would be better to get some basic knowledge first.\
-\
\-- [\*\*Angular\*\*]\(https\://angular.dev/). This is the main framework behind Keira3.\
\-  We absolutely recommend getting familiar with it before getting your hands inside Keira3's code.\
\-  Keira3 uses \*\*modern Angular\*\*: \*\*standalone components\*\* (no NgModules), \*\*OnPush\*\* change detection (enforced via the \`@angular-eslint/prefer-on-push-component-change-detection\` lint rule), \*\*zoneless\*\* change detection (\`provideZonelessChangeDetection()\`), \*\*Angular Signals\*\* for reactive state, and the \`inject()\` function for dependency injection (instead of constructor injection).\
\-  If you are looking for a complete Angular course, we can recommend [this one]\(https\://www\.udemy.com/course/the-complete-guide-to-angular-2/).\
-\
\-- [\*\*SCSS\*\*]\(https\://sass-lang.com/) for styling. It's an extension of CSS.\
\-  Knowing the CSS fundamentals is required in order to be able to change the Keira3's interface.\
+- [\*\*TypeScript\*\*]\(http\://www\.typescriptlang.org/) is the main language of Keira3. It is a superset of JavaScript. \
+If you know JavaScript and have some basic knowledge of OOP languages like Java and C#, you will feel pretty familiar with TypeScript already.\
+Otherwise, you might find [this course]\(https\://www\.udemy.com/course/understanding-typescript/) helpful.\
+If you don't know JavaScript at all, it would be better to get some basic knowledge first.\
+\
+- [\*\*Angular\*\*]\(https\://angular.io/). This is the main framework behind Keira3. \
+We absolutely recommend getting familiar with it before getting your hands inside Keira3's code.\
+If you are looking for a complete Angular course, we can recommend [this one]\(https\://www\.udemy.com/course/the-complete-guide-to-angular-2/).\
+\
+- We use [\*\*SCSS\*\*]\(https\://sass-lang.com/) to style our UI. It's an extension of CSS.\
+Knowing the CSS fundamentals is required in order to be able to change the Keira3's interface.\
+SCSS should be quite intuitive for anyone who can understand CSS.\
&#x20;\
&#x20;\- [\*\*Bootstrap\*\*]\(https\://getbootstrap.com/) is the CSS framework used as a base for Keira3's style.\
\-  You don't have to be a Bootstrap expert, however we recommend being at least familiar with its [Grid system]\(https\://getbootstrap.com/docs/5.3/layout/grid/) and Utilities like [spacing]\(https\://getbootstrap.com/docs/5.3/utilities/spacing/).\
\-  We also use a few \*\*ngx-bootstrap\*\* modules (\`Modal\`, \`Tabs\`, \`Tooltip\`, \`Dropdown\`) and the \`ngx-toastr\` library for notifications.\
+You don't have to be a Bootstrap expert, however we recommend being at least familiar with its [Grid system]\(https\://getbootstrap.com/docs/5.3/layout/grid/) and Utilities like [spacing]\(https\://getbootstrap.com/docs/5.3/utilities/spacing/).\
&#x20;\
&#x20;\- [\*\*Electron\*\*]\(https\://electronjs.org/) is the software framework that allows building Desktop apps using web technologies.\
\-  The Electron main process lives in the project root (\`main.ts\` → compiled to \`main.js\`); the Angular code never talks to \`mysql2\`/\`sqlite3\`/\`ssh2\` directly but through \`window\.require(...)\` guarded by \`ElectronService.isElectron()\`.\
-\
\-- [\*\*Nx\*\*]\(https\://nx.dev/) is the build system that manages the monorepo and keeps the project modular by dividing it into several libraries.\
\-  Among several features, we leverage the powerful [affected]\(https\://nx.dev/ci/features/affected) command of Nx to run checks (e.g. lint, test, ...) only against the parts of the application that have been modified and those which depend on them.\
-\
\-- [\*\*Squel\*\*]\(https\://hiddentao.com/squel/) is the SQL builder used by \`MysqlQueryService\` to generate every UPDATE/INSERT/DELETE query Keira3 produces.\
-\
\-- [\*\*@ngx-translate\*\*]\(https\://github.com/ngx-translate/core) powers i18n; translation files live in \`apps/keira/src/assets/i18n/\*.json\`. The language picker is \`@keira/shared/switch-language\`.\
+We don't use many native Electron features so usually you don't have to worry about it when developing Keira3.\
+\
+- [\*\*NX\*\*]\(https\://nx.dev/) is the build system to manage the project and keep it modular by diving it into several libraries.\
+It was originally born as an extension of the Angular CLI, today NX is a generic to manage all kinds of monorepo projects (also for projects not based on Angular).\
... 662 additional diff lines omitted\
\
\--- docs/mysqltypescpp.md ---\
Pinned lines: 52 | CICS lines: 220 | Similarity: 15.4%\
Diff lines: 242\
\--- PINNED/docs/mysqltypescpp.md\
+++ CICS/docs/mysqltypescpp.md\
@@ -5,34 +5,202 @@\
&#x20;\# MySQL Types C++\
&#x20;\
\-| MySQL type         | Core type                                     | Example code                                                                                | Variable operators |\
\-| ------------------ | --------------------------------------------- | ------------------------------------------------------------------------------------------- | ------------------ |\
\-| BIGINT             | int64                                         | \`int64 val = fields[n].GetInt64();\`                                                         | %I64d (Capital i)  |\
\-| BIGINT UNSIGNED    | uint64                                        | \`uint64 val = fields[n].GetUInt64();\`                                                       | %I64u (Capital i)  |\
\-| INT                | int32                                         | \`int32 val = fields[n].GetInt32();\`                                                         | %u                 |\
\-| INT UNSIGNED       | uint32                                        | \`uint32 val = fields[n].GetUInt32();\`                                                       | %u                 |\
\-| MEDIUMINT          | int32                                         | \`int32 val = fields[n].GetInt32();\`                                                         | %u                 |\
\-| MEDIUMINT UNSIGNED | uint32                                        | \`uint32 val = fields[n].GetUInt32();\`                                                       | %u                 |\
\-| SMALLINT           | int16                                         | \`int16 val = fields[n].GetInt16();\`                                                         |                    |\
\-| SMALLINT UNSIGNED  | uint16                                        | \`uint16 val = fields[n].GetUInt16();\`                                                       |                    |\
\-| TINYINT            | int8                                          | \`int16 val = fields[n].GetInt16();\`                                                         |                    |\
\-| TINYINT UNSIGNED   | uint8                                         | \`uint8 val = fields[n].GetUInt8();\`                                                         |                    |\
\-| FLOAT              | float                                         | \`float val = fields[n].GetFLOAT();\`                                                         |                    |\
\-| FLOAT UNSIGNED     | float                                         | \`float val = fields[n].GetFLOAT();\`                                                         |                    |\
\-| DOUBLE             | double                                        | \`double val = fields[n].GetDouble();\`                                                       |                    |\
\-| DOUBLE UNSIGNED    | double                                        | \`double val = fields[n].GetDouble();\`                                                       |                    |\
\-| text               | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| longtext           | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| tinytext           | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| char(k)            | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| VARCHAR(k)         | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| blob               | string (std::string) or cstring (char const\*) | \`std::string text = fields[n].GetString();\`\<br>\`char const\* text = fields[n].GetCString();\` | %s                 |\
\-| COUNT(x)           | uint64                                        | \`uint64 count = fields[n].GetUInt64();\`                                                     | %UI64FMT\*          |\
\-| MAX(x)             | uint32 or int32                               | \`uint32 minmax = fields[n].GetUInt32();\`\<br>\`int32 minmax = fields[n].GetInt32();\`          | %u                 |\
\-| MIN(x)             | uint32 or int32                               | \`uint32 minmax = fields[n].GetUInt32();\`\<br>\`int32 minmax = fields[n].GetInt32();\`          | %u                 |\
\-| SUM(x)             | string (std::string) or cstring (char const\*) | \`INT sum;\`\<br>\`if (const char\* ch = fields[n].GetCString())\`\<br>\`    sum = atoi(ch);\`       | %s                 |\
\-| UNIX_TIMESTAMP(x)  | uint64                                        | \`uint64 unix_time = fields[n].GetUInt64();\`                                                 |                    |\
-\
-\\\* %UI64FMT does not work with acore_string\
-\
+\<div id="main-content" data-inline-comments-target="true" class="wiki-content">\
\+    \<div class="table-wrap">\
\+        \<table class="confluenceTable" resolved="">\
\+            \<thead>\
\+                \<tr>\
\+                    \<th colspan="4" class="confluenceTh">Mapping from types used in SQL queries\</th>\
\+                \</tr>\
\+            \</thead>\
\+            \<tbody>\
\+                \<tr>\
\+                    \<th class="confluenceTh">\
\+                        \<p>MySQL type\</p>\
\+                        \<th class="confluenceTh">Core type\
\+                    \</th>\
\+                    \<th class="confluenceTh">Example code\</th>\
\+                    \<th colspan="1" class="confluenceTh">Variable operators\</th>\
\+                \</tr>\
\+                \<tr>\
\+                    \<td colspan="1" class="confluenceTd">BIGINT\</td>\
\+                    \<td colspan="1" class="confluenceTd">int64\</td>\
... 187 additional diff lines omitted\
\
\--- docs/es/windows-server-setup.md ---\
Pinned lines: 131 | CICS lines: 82 | Similarity: 39.4%\
Diff lines: 173\
\--- PINNED/docs/es/windows-server-setup.md\
+++ CICS/docs/es/windows-server-setup.md\
@@ -1,45 +1,13 @@\
-# Configuración del servidor en Windows\
+# Configuración del Servidor en Windows\
&#x20;\
\-| Guía de instalación | |\
+| Guía de Instalación | |\
&#x20;\| :- | :- |\
\-| Este artículo es parte de la Guía de instalación. Puedes leerlo solo o hacer click en el enlace anterior para moverte fácilmente entre los pasos. |\
\-| [<< Paso 2: Instalación del Core]\(windows-core-installation) | [Paso 4: Instalación de la base de datos >>]\(database-installation) |\
+| Este artículo es parte de la Guía de Instalación. Puede leerlo solo o hacer click en los links previos para navegar con facilidad entre los pasos. |\
+| [<< Paso 2: Instalación del Core]\(core-installation) | [Paso 4: Instalación de la base de datos >>]\(database-installation) |\
&#x20;\
-\*\*Tabla de contenidos\*\*\
\-- [Archivos de datos del cliente (descargar pre-extraídos)]\(#option-1-download-pre-extracted-files)\
\-- [Extractores de datos del cliente (extraer los archivos tú mismo)]\(#option-2-extract-files-yourself)\
\-- [Archivos de configuración: Worldserver y Authserver]\(#config-files-worldserver-and-authserver)\
+## Extrayendo los archivos DBC, Maps, VMaps & MMaps\
&#x20;\
-Ahora que tienes el código fuente compilado, necesitas añadir los datos del cliente necesarios. Puedes descargar los archivos ya extraídos o usar los extractores compilados para extraer los archivos tú mismo. Una vez que los datos estén listos, debes actualizar la opción \*\*DataDir\*\* en tu archivo \*\*worldserver.conf\*\* para que apunte al directorio que contiene los datos.\
+1. Busque dentro del directorio de su build (\*\*C:\Build\RelWithDebInfo\\\\\*\* \\\*) y copie los siguientes archivos dentro de la carpeta de World of Warcraft. (en donde esté ubicado el archivo wow\.exe).\
&#x20;\
-Algunos archivos son opcionales pero muy recomendados:\
-\
\-| Directorio | |\
\-| :- | :- |\
\-| dbc | Obligatorio |\
\-| maps | Obligatorio |\
\-| vmaps | MUY RECOMENDADO |\
\-| mmaps | MUY RECOMENDADO |\
\-| cameras | Recomendado |\
-\
-## Opción 1: Descargar archivos pre-extraídos {#option-1-download-pre-extracted-files}\
-\
-Si tienes intención de usar un cliente enUS, puedes descargar los archivos de datos de abajo. Si tienes intención de usar un cliente en cualquier otro idioma, necesitarás [extraer]\(#option-2-extract-files-yourself) los datos tú mismo.\
-\
-\<a class="no-icon" href="https\://github.com/wowgaming/client-data/releases/" target="\_blank">\<i class="fa-solid fa-download">\</i> Archivos de datos enUS (AC Data v19)\</a>\
-\
-1. Descarga los archivos de arriba.\
-\
-2. Crea una nueva carpeta dentro de la carpeta de build llamada \*\*Data\*\*, p. ej. \*\*C:\Build\bin\RelWithDebInfo\Data\*\*\
-\
-3. Extrae los archivos del zip y colócalos dentro de la carpeta \*\*Data\*\*.\
-\
-4. Edita la opción de configuración [DataDir]\(#updating-datadir) con la ubicación de tu carpeta.\
-\
-## Opción 2: Extraer los archivos tú mismo {#option-2-extract-files-yourself}\
-\
-\*\*(No es necesario si descargaste los archivos de arriba)\*\*\
-\
-1. Entra en tu directorio de build (\*\*C:\Build\bin\RelWithDebInfo\\\\\*\*) y copia los siguientes archivos en tu carpeta de World of Warcraft (donde se encuentra el wow\.exe).\
&#x20;\`\`\`\
&#x20;mapextractor.exe\
@@ -47,36 +15,37 @@\
... 118 additional diff lines omitted\
\
\--- docs/account.md ---\
Pinned lines: 229 | CICS lines: 229 | Similarity: 97.8%\
Diff lines: 30\
\--- PINNED/docs/account.md\
+++ CICS/docs/account.md\
@@ -90,5 +90,5 @@\
&#x20;\### session\\\_key\
&#x20;\
-The session key used for encrypting the current authenticated session. Populated on login and cleared on logout.\
+\`field-no-description|5\`\
&#x20;\
&#x20;\### totp\\\_secret\
@@ -154,6 +154,6 @@\
&#x20;\| --------------------------------- | ------------------------------------- | ---------- |\
&#x20;\| ACCOUNT_FLAG_GM                   | Account is GM                         | 1          |\
\-| ACCOUNT_FLAG_NOKICK               | Will not be logged out while AFK      | 2          |\
\-| ACCOUNT_FLAG_COLLECTOR            | Collector's Edition (grants a starter gift voucher when creating a character) | 4          |\
+| ACCOUNT_FLAG_NOKICK               | UNK                                   | 2          |\
+| ACCOUNT_FLAG_COLLECTOR            | Collector's Edition                   | 4          |\
&#x20;\| ACCOUNT_FLAG_TRIAL                | Trial account                         | 8          |\
&#x20;\| ACCOUNT_FLAG_CANCELLED            | UNK                                   | 16         |\
@@ -182,5 +182,5 @@\
&#x20;\| ACCOUNT_FLAG_OVERMIND_LINKED      | Linked with Battle.net account        | 134217728  |\
&#x20;\| ACCOUNT_FLAG_DEMOS                | UNK                                   | 268435456  |\
\-| ACCOUNT_FLAG_DEATH_KNIGHT_OK      | Allowed to create Death Knight. Automatically set when the account first meets the \`CharacterCreating.MinLevelForHeroicCharacter\` requirement; once set, overrides that requirement. | 536870912  |\
+| ACCOUNT_FLAG_DEATH_KNIGHT_OK      | Allowed to create Death Knight        | 536870912  |\
&#x20;\| ACCOUNT_FLAG_S2_REQUIRE_IGR       | UNK (StarCraft II related?)           | 1073741824 |\
&#x20;\| ACCOUNT_FLAG_S2_TRIAL             | UNK (StarCraft II related?)           | 2147483648 |\
@@ -227,3 +227,3 @@\
&#x20;\### recruiter\
&#x20;\
-The account ID of another account. Used for recruit-a-friend system. See [account.id][1]\
+The account ID of another account. Used for recuit-a-friend system. See [account.id][1]\
\
\--- docs/common-errors.md ---\
Pinned lines: 322 | CICS lines: 322 | Similarity: 99.1%\
Diff lines: 23\
\--- PINNED/docs/common-errors.md\
+++ CICS/docs/common-errors.md\
@@ -112,5 +112,5 @@\
&#x20;Map file './maps/0004331.map' is from an incompatible map version (MAPS v9), MAPS v10 is expected\
&#x20;\`\`\`\
-Pull the source, recompile tools, copy the extractors to your wow binaries and recreate the maps using the updated mapextractor. Then replace your old map files with the new ones.\
+Pull the source, recompile tools, copy the extractors to your wow binaries and recreate the maps using the updated mapextractor. Then repl#ace your old map files with the new ones.\
&#x20;\
&#x20;\---------------------------------------------------------\
@@ -136,5 +136,5 @@\
&#x20;\---------------------------------------------------------\
&#x20;\
-#### [ACE00048]\(#a-hreface00048ace00048a)\
+#### [ACE00048]\(#a-hreface00047ace00047a)\
&#x20;I get an error when I am trying to start Worldserver or Authserver\
&#x20;\`\`\`\
@@ -193,5 +193,5 @@\
&#x20;I can't compile, I get:\
&#x20;\`\`\`\
-fatal error C1060: compiler is out of heap space\
+fatal error C1060: compiler is out of heap sp#ace\
&#x20;C1076: compiler limit : internal heap limit reached; use /Zm to specify a higher limit\
&#x20;\`\`\`\
\
\--- docs/creature_template.md ---\
Pinned lines: 642 | CICS lines: 695 | Similarity: 95.3%\
Diff lines: 84\
\--- PINNED/docs/creature_template.md\
+++ CICS/docs/creature_template.md\
@@ -63,5 +63,6 @@\
&#x20;\| [movementId]\(#movementid)                          | INT UNSIGNED       | NO   |     | 0       |       |                                      |\
&#x20;\| [RegenHealth]\(#regenhealth)                        | TINYINT UNSIGNED   | NO   |     | 1       |       |                                      |\
\-| [CreatureImmunitiesId]\(#creatureimmunitiesid)      | INT UNSIGNED       | NO   |     | 0       |       | Reference to creature_immunities table |\
+| [mechanic_immune_mask]\(#mechanicimmunemask)        | INT UNSIGNED       | NO   |     | 0       |       |                                      |\
+| [spell_school_immune_mask]\(#spellschoolimmunemask) | INT UNSIGNED       | NO   |     | 0       |       |                                      |\
&#x20;\| [flags_extra]\(#flagsextra)                         | INT UNSIGNED       | NO   |     | 0       |       |                                      |\
&#x20;\| [ScriptName]\(#scriptname)                          | char(64)           | NO   |     |         |       |                                      |\
@@ -579,9 +580,61 @@\
&#x20;Boolean '1' or '0' controlling whether the creature should regenerate it's health or not.\
&#x20;\
-#### CreatureImmunitiesId\
-\
-Reference to the \`creature_immunities\` table which centralises spell- and mechanic-based immunities.\
-\
-For the detailed list of mechanics and spell-school bits, see [creature_immunities]\(creature_immunities.md).\
+#### mechanic_immune_mask\
+\
+This makes the creature immune to specific spell natures. See Spell.dbc at row effect_X_mechanic_id.\
+\
+Uses references from SpellMechanic.dbc.\
+\
+| Flag       |            | Type                     | Comment                                                  |\
+| ---------- | ---------- | ------------------------ | -------------------------------------------------------- |\
+| 1          | 0x00000001 | MECHANIC_CHARM           |                                                          |\
+| 2          | 0x00000002 | MECHANIC_DISORIENTED     |                                                          |\
+| 4          | 0x00000004 | MECHANIC_DISARM          |                                                          |\
+| 8          | 0x00000008 | MECHANIC_DISTRACT        |                                                          |\
+| 16         | 0x00000010 | MECHANIC_FEAR            |                                                          |\
+| 32         | 0x00000020 | MECHANIC_GRIP            | Death Grip and similar effects                           |\
+| 64         | 0x00000040 | MECHANIC_ROOT            |                                                          |\
+| 128        | 0x00000080 | MECHANIC_SLOW_ATTACK     |                                                          |\
+| 256        | 0x00000100 | MECHANIC_SILENCE         |                                                          |\
+| 512        | 0x00000200 | MECHANIC_SLEEP           |                                                          |\
+| 1024       | 0x00000400 | MECHANIC_SNARE           |                                                          |\
+| 2048       | 0x00000800 | MECHANIC_STUN            |                                                          |\
+| 4096       | 0x00001000 | MECHANIC_FREEZE          |                                                          |\
+| 8192       | 0x00002000 | MECHANIC_KNOCKOUT        | Incapacitate effects such as Repetance (Paladin)         |\
+| 16384      | 0x00004000 | MECHANIC_BLEED           |                                                          |\
+| 32768      | 0x00008000 | MECHANIC_BANDAGE         | Healing etc.                                             |\
+| 65536      | 0x00010000 | MECHANIC_POLYMORPH       |                                                          |\
+| 131072     | 0x00020000 | MECHANIC_BANISH          |                                                          |\
+| 262144     | 0x00040000 | MECHANIC_SHIELD          |                                                          |\
+| 524288     | 0x00080000 | MECHANIC_SHACKLE         | Shackle Undead only                                      |\
+| 1048576    | 0x00100000 | MECHANIC_MOUNT           | Any effect that summons a mount                          |\
+| 2097152    | 0x00200000 | MECHANIC_INFECTED        | Frost Fever, Blood Plague etc.                           |\
+| 4194304    | 0x00400000 | MECHANIC_TURN            | e.g. Turn Evil                                           |\
+| 8388608    | 0x00800000 | MECHANIC_HORROR          | e.g. Death Coil (Warlock)                                |\
+| 16777216   | 0x01000000 | MECHANIC_INVULNERABILITY | Forbearance, Nether Protection, Diplomatic Immunity only |\
+| 33554432   | 0x02000000 | MECHANIC_INTERRUPT       |                                                          |\
+| 67108864   | 0x04000000 | MECHANIC_DAZE            |                                                          |\
+| 134217728  | 0x08000000 | MECHANIC_DISCOVERY       | Any Create Item effect                                   |\
+| 268435456  | 0x10000000 | MECHANIC_IMMUNE_SHIELD   | Divine Shield, Ice Block, Hand of Protection...          |\
... 29 additional diff lines omitted\
\
\--- docs/es/how-to-ask-for-help.md ---\
Pinned lines: 72 | CICS lines: 94 | Similarity: 42.2%\
Diff lines: 134\
\--- PINNED/docs/es/how-to-ask-for-help.md\
+++ CICS/docs/es/how-to-ask-for-help.md\
@@ -1,72 +1,94 @@\
&#x20;\---\
-redirect_from: "/es/How-to-ask-for-help"\
+redirect_from: "/How-to-ask-for-help"\
&#x20;\---\
&#x20;\
-# Cómo pedir ayuda\
+# Cómo solicitar ayuda\
&#x20;\
-## ¿Necesitas ayuda?\
+## Necesita ayuda?\
&#x20;\
-¿Necesitas soporte con AzerothCore? ¡No te preocupes, estaremos encantados de ayudarte!\
+Necesita soporte para AzerothCore? No se preocupe, ¡estamos felices de ayudarle!\
&#x20;\
-Ya sea que tengas problemas instalando AzerothCore, o que quieras hacer preguntas de tipo how-to o de ayuda genérica, \*\*te ayudaremos\*\*.\
+Ya se que tenga inconvenientes instalando AzerothCore, o que quiera resolver otras dudas comunes, \*\*we will help you\*\*.\
&#x20;\
-Solo queremos que pidas soporte de \*\*la forma apropiada\*\*. Por favor, lee este documento antes de pedir cualquier ayuda.\
+Solo queremos que pregunte o pida soporte de \*\*la forma apropiada\*\*. Por favor, lea este documento antes de pedir cualquier tipo de ayuda.\
&#x20;\
-## Preguntas frecuentes y errores comunes\
+## Preguntas frecuentes & Errores comunes\
&#x20;\
-Primero, te recomendamos leer las [Preguntas frecuentes]\(faq) y los [Errores comunes]\(common-errors) para encontrar la solución a tu problema.\
+Primero que todo, le recomendamos que lea los apartados [Preguntas Frecuentes]\(faq) y [Errores Comunes]\(common-errors) posiblemente ahí esté la respuesta a su inconveniente.\
&#x20;\
-## ¿Por qué es tan importante "la forma apropiada"?\
+## Por qué "la forma apropiada" es tan importante?\
&#x20;\
-Si haces una pregunta directamente en el chat, puede perderse fácilmente y quizás nunca recibas ayuda, a menos que haya alguien conectado en ese momento concreto que pueda ayudarte.\
+Si usted pregunta algo directamente en el chat, se puede perder con facilidad y no recibir respuesta alguna, a menos que haya alguien conectado en ese preciso momento y que esté en la posibilidad de contestar.\
&#x20;\
-Si pones tu pregunta en StackOverflow, \*\*permanecerá\*\* ahí y alguien podrá ayudarte en cualquier momento. También puedes enlazar tu pregunta en el chat para darle más visibilidad. ¿No te parece que tiene sentido? Sigue leyendo.\
+If you put your question on StackOverflow it will \*\*stay\*\* there and someone can help you at any moment. You can also link your question in the chat to give it more visibility. Doesn't make sense for you? Just keep reading.\
&#x20;\
-Además, la mayoría de las preguntas que hacen los usuarios son repetitivas. Así que necesitamos una forma eficiente de manejar todas las solicitudes de soporte. Usamos StackOverflow para preguntas de soporte y GitHub para reportes de bugs.\
+Además, la mayoría de las preguntas son repetitivas. Por esta razón, necesitamso una manera eficiente de manejar todas las peticiones de soporte. Usamos StackOverflow para preguntas de soporte y GitHub para reporte de bugs.\
&#x20;\
-¿Suena complicado? ¡Para nada! \*\*Sigue leyendo\*\*.\
+Suena complicado? Para nada! \*\*solo siga leyendo\*\*.\
&#x20;\
-## Reportes de bugs\
+## Reporte de Bugs\
&#x20;\
-¿Una funcionalidad del juego (p. ej. spell/quest/talent/etc..) no funciona como debería?\
+¿Un elemento del juego (Por ejemplo: spell/quest/talent/etc..) no funciona como debería?\
&#x20;\
-¡Felicidades! Acabas de encontrar un bug; por favor busca entre los [issues existentes]\(https\://github.com/azerothcore/azerothcore-wotlk/issues). Hay buenas probabilidades de que alguien más ya haya reportado el mismo bug que encontraste; en ese caso te pedimos amablemente que lo "confirmes" dejando un comentario.\
+Felicitaciones! Ha encontrado un bug. Por favor, busque entre los [reportes existentes]\(https\://github.com/azerothcore/azerothcore-wotlk/issues). Hay una probabilidad alta de que alguien más ya haya reportado el mismo bug que usted encontró. En tal caso, le pedimos amablemente que lo "confirme" dejando un comentario.\
&#x20;\
&#x20;Ejemplo:\
-![Ejemplo de búsqueda de issues en AzerothCore]\(https\://user-images.githubusercontent.com/75517/51130957-9b9f9580-182e-11e9-8f7f-11aa5d7b6d67.png)\
... 79 additional diff lines omitted\
\
\--- docs/es/installation.md ---\
Pinned lines: 50 | CICS lines: 75 | Similarity: 44.8%\
Diff lines: 94\
\--- PINNED/docs/es/installation.md\
+++ CICS/docs/es/installation.md\
@@ -3,31 +3,27 @@\
&#x20;\---\
&#x20;\
-# Guía de instalación\
+# Guía de instalación \
&#x20;\
-## Eligiendo una instalación\
+## Escogiendo una configuación\
&#x20;\
-Hay varias formas de instalar AzerothCore, necesitas elegir \*\*UNA\*\*.\
+Existen diferentes formas de instalar AzerothCore. Escoja solo \*\*UNA\*\*.\
&#x20;\
-### Instalación desde el código fuente (Recomendada)\
+### Completa (con soporte, recomendada)\
&#x20;\
-Esta es la forma oficialmente soportada y completa de instalar AzerothCore.\
+Estas son las formas oficiales, con soporte y completas para instalar AzerothCore para cualquier propósito.\
&#x20;\
\-- [Instalación clásica de AzerothCore]\(classic-installation) - Recomendada para Windows, macOS y Linux.\
+- [Instalación clásica de Azerothcore (Windows, Linux, macOS)]\(classic-installation) - la forma tradicional de instalar AzerothCore. Probada, recomendada para todos los sistemas operativos para todos los propósitos. Seguir este proceso ilustra de una mejor forma cómo está estructurado AzerothCore. Encontrará más información más adelante en esta página. \
&#x20;\
-### Instalaciones experimentales (soporte y uso limitados)\
+- [Instalación mediante Docker]\(install-with-docker) - un proceso de instalación simplificado, basado en Docker.\
&#x20;\
-Estas guías son para instalaciones experimentales y tienen soporte limitado o nulo.\
+- [Instalación de AzerothCore mediante el Panel de Control Bash (Bash Dashboard)]\(ac-dashboard-core-installation) - Es la forma más sencilla de instalar AzerothCore. Recommendada para \*\*Linux\*\* tanto para desarrollo local como para producción. Actualmente no se recomienda para Windows o macOs.\
&#x20;\
\-- [Instalación con el Dashboard Bash de AzerothCore]\(ac-dashboard-core-installation) - la forma más sencilla de instalar.\
+### Mínima (con soporte, con limitaciones)\
&#x20;\
\-- [Instalación con Docker]\(install-with-docker) - un proceso de instalación basado en Docker. Se recomienda tener conocimientos previos de Docker.\
+- [Instalación mediante Docker, pre-compilada]\(https\://www\.azerothcore.org/acore-docker/) - Una forma extremadamente sencilla de instalación. Apropiada para clasificación de bugs, reporte de bugs o uso personal/doméstico.\
&#x20;\
\-- [Instalación con Docker pre-compilado]\(https\://www\.azerothcore.org/acore-docker/) - una forma sencilla de instalar AzerothCore. Actualmente no puedes instalar módulos C++, solo scripts de Eluna. Adecuada para clasificación de bugs, reporte de bugs o uso doméstico.\
+### Otras (sin soporte)\
&#x20;\
-### Hechas por la comunidad (sin soporte)\
-\
-Ten en cuenta que estas guías están hechas por miembros de la comunidad y podrían no estar actualizadas:\
-\
\-- [Debian 12]\(debian12-install-guide)\
+Estas guias están hechas por la comunidad y pueden estar desactualizadas.\
&#x20;\
&#x20;\- [Amazon Web Services]\(aws-tutorial)\
@@ -39,12 +35,41 @@\
&#x20;\- [FreeBSD]\(freebsd)\
&#x20;\
\-- [Visual Studio Code]\(vsc-requirements)\
+## Instalación clásica de AzerothCore\
+\
+Cada paso de esta guía está dividido en tres secciones, según cada sistema operativo (Linux, macOS and Windows).\
+\
+La guía se divide en 8 pasos, para facilitar su lectura.\
... 39 additional diff lines omitted\
\
\--- docs/server-setup.md ---\
Pinned lines: 23 | CICS lines: 23 | Similarity: 100.0%\
Diff lines: 0\
\
\========== END ==========\
(deck@ExosSteamDeck engineering-rag-corpus)$ \

## Assistant

This output establishes that the CICS tree is **not a faithful byte-level copy of the pinned July 21, 2026 Git snapshot**. It also reveals at least two different kinds of divergence.

1. **Content-version divergence:** `creature_template.md` in CICS documents the older `mechanic_immune_mask` and `spell_school_immune_mask` fields, while the pinned revision uses `CreatureImmunitiesId` and links to the separate `creature_immunities` table. The Spanish installation/help documents also contain substantially different wording and structure. These are not formatting-only differences.
2. **Representation changes:** `conditions.md` and `mysqltypescpp.md` in CICS contain HTML table markup where the pinned files contain Markdown tables. That suggests an export, rendering, or conversion step somewhere in the copy's history.
3. **Possible content corruption or manual modification:** `common-errors.md` contains strings such as `repl#ace` and `sp#ace`, while `account.md` has a placeholder `field-no-description|5`. Those are not explained by ordinary Markdown-to-HTML conversion.

The evidence therefore points to a mixed or transformed source tree, not merely a partial checkout. We still need to identify how it was assembled and whether the changes were deliberate, generated, or accidental.

## Provenance check

The next useful evidence is the CICS tree's own synchronization script and the separate AzerothCore execution records. Run this read-only inspection:

```bash
printf '%s\n' '========== CICS SYNC SCRIPT =========='
sed -n '1,240p' "/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki/sync-wiki.sh"

printf '\n%s\n' '========== CICS SOURCE CONFIG =========='
sed -n '1,180p' "/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki/_config.yml"

printf '\n%s\n' '========== AZEROTHCORE ACQUISITION RECORDS =========='
RECORDS="/home/deck/Old-Drive-Import/more repos/Repositories/blaine-azerothcore/records"
for f in \
  "$RECORDS/executions/RUN-0014-acquire-and-pin-official-azerothcore-source.md" \
  "$RECORDS/executions/RUN-0015-establish-internal-ext4-azerothcore-baseline-checkout.md" \
  "$RECORDS/validations/VAL-0014-official-azerothcore-source-acquisition-validation.md" \
  "$RECORDS/decisions/ADR-0014-official-azerothcore-source-clone-and-baseline-pin.md" \
  "$RECORDS/decisions/ADR-0015-internal-ext4-independent-azerothcore-baseline-checkout.md"
do
  if [ -f "$f" ]; then
    printf '\n--- %s ---\n' "$(basename "$f")"
    sed -n '1,180p' "$f"
  else
    printf '\nNOT FOUND: %s\n' "$f"
  fi
done
```

This should help distinguish a CICS-specific import/conversion from an independently acquired AzerothCore source. In particular, I want to know whether `sync-wiki.sh` pulls from upstream Git, copies rendered pages, or transforms files—and whether the other repo's records identify a separate acquisition date or commit.

Don't merge or replace anything yet. The pinned snapshot and CICS tree should remain separate until provenance and content differences are accounted for.

## User

========== CICS SYNC SCRIPT ==========
#!/usr/bin/env bash
#
# This script can be used to sync the wiki submodule
# in case you're using github internal wiki option
#

git pull origin master
cd wiki
git pull origin master
cd ..
git commit -a -m "updated wiki"
git push origin master

========== CICS SOURCE CONFIG ==========
# this version is only used internally to update 
# the remote_theme when needed
ac_wiki_version: 2.0.5
# based on latest (master) git-wiki-theme
remote_theme: Drassil/git-wiki-theme@master
# (string) Title of your wiki
title: AzerothCore
# (string) Description of your wiki
description: Wiki and Documentation of the AzerothCore project
# (boolean) Enable/disable wiki page list in sidebar
show_wiki_pages: true
# (integer) Maximum number of wiki page to shown in sidebar
show_wiki_pages_limit: 0
# (boolean) Enable/disable blog feature
blog_feature: false
# (boolean) Enable/disable wiki posts list in sidebar (needs blog_feature enabled)
show_wiki_posts: false
# (integer) Maximum number of wiki posts to shown in sidebar
show_wiki_posts_limit: 10
# from jekyll (read jekyll doc)
paginate: 5
paginate_path: "/blog/page:num"
permalink: /blog/posts/:year/:month/:day/:title:output_ext
# (boolean) Enable/disable download buttons in sidebar
show_downloads: false
# (string) Specify branch rendered by gitpages allowing wiki tool buttons to work
git_branch: "master"
# (string) Url of logo image, it can be full, absolute or relative.
logo_url: http://www.azerothcore.org/images/logo.png
# (string) The UA-XXXXX-Y code from google analytic to enable GA on your wiki
google_analytics:
# (string) folder where wiki pages are stored, it's needed for tool buttons
wiki_folder: docs
# (boolean) if you're using github wiki as submodule then this config
# must be enabled to allow tool buttons to work properly
use_github_wiki: false
# (boolean) Enable "Edit with Prose.io" button in tools, it's a 3rd party
# service to edit github markdown pages easily
use_prose_io: false
# Select search_engine component from:
# - js: it uses a built in javascript component that uses generated js object
# - js_rss: it uses a built in javascript component that uses generated  sitemap_full.xml to search inside your wiki with lunr library (slow and experimental)
# - github : it uses internal github repository search
# - google : it uses cse search bar, you need to configure google_cse_token
#
search_engine : "js"
# Setting google custom search engine for google
# cse search bar (https://cse.google.it/cse/)
google_cse_token:

#
# Jekyll configurations
#

# You can customize it changing default layout for all pages
# More info: https://jekyllrb.com/docs/configuration/
#
# git-wiki includes some internal themes that you can choose
# check _layouts folder
#
markdown: GFM
highlighter: rouge
encoding: UTF-8

defaults:
 -
    scope:
      locale: "en"
      path: "docs"
    values:
      permalink: /:basename
 -
    scope:
      locale: "es"
      path: "docs/es"
    values:
      permalink: /es/:basename
 -
    scope:
      path: "" # an empty string here means all files in the project
    values:
      layout: "azerothcore"
 -
    scope:
      path: ""
      type: "pages"
    values:
      layout: "azerothcore"
 -
    scope:
      path: ""
      type: "posts"
    values:
      layout: "git-wiki-post"
 -
    scope:
      path: blog
    values:
      layout: "git-wiki-blog"
sass:
    style: compressed
plugins:
 - jekyll-feed
 - jekyll-redirect-from
 - jekyll-seo-tag
 - jekyll-sitemap
 - jekyll-avatar
 - jemoji
 - jekyll-mentions

exclude: ['wiki']


#
# INCLUDING HOOKS
# They are optional, change them only if you need
# Check wiki documentation to learn how they work
#

inc_before_toc :
inc_after_toc :
inc_before_content :
inc_after_content :
inc_before_footer :
inc_after_footer :
inc_before_head :
inc_after_head : "azerothcore/afterhead.html"
inc_before_meta :
inc_after_meta :
inc_before_scripts :
inc_after_scripts :
inc_before_styles :
inc_after_styles :
inc_before_header :
inc_after_header :
inc_before_tail :
inc_after_tail :
inc_before_tools :
inc_after_tools :

inc_before_page_list : "azerothcore/sidebar.html"
inc_after_page_list :
inc_before_post_list :
inc_after_post_list :

========== AZEROTHCORE ACQUISITION RECORDS ==========

--- RUN-0014-acquire-and-pin-official-azerothcore-source.md ---
# RUN-0014 — Acquire and Pin Official AzerothCore Source

## Record control

- Date: 2026-07-14 (America/Phoenix)
- Acquisition start: `2026-07-14T22:18:21-07:00` / `2026-07-15T05:18:21+00:00`
- Lifecycle before and after: `S0 — Proposed`
- Objective: acquire and verify official AzerothCore WotLK source objects, pin `SRC-ACORE-WOTLK-001`, statically inventory build/acquisition behavior, publish governance evidence, and stop before build or runtime work.
- Governance root: `/run/media/deck/blAIneXPLAT/azerothcore/`
- Source object clone: `/run/media/deck/blAIneXPLAT/azerothcore/linux/upstream/azerothcore-wotlk/`
- Starting governance commit: `38c1e515d47564fe7f04f3d55503785b104ce5a7`
- Publication state in this revision: source/object validation, staged audit, governance commit, and first normal push verified; completed evidence is ready for the single validation-only follow-up commit.

## Authorization boundary

Writes were limited to the governance repository, the exact ignored upstream clone, and an immediately removed filesystem-representability probe beneath `linux/upstream/`. No sudo, package or SteamOS change, Docker change, build, image pull, container, database, client data, module, submodule, LFS pull, patch, compiler, runtime, port, server, or upstream push was authorized or performed.

## Governance starting state

- Canonical root matched the authorized path; branch `main`; clean working tree; no active Git operation.
- Origin matched `git@github.com:blainesmith33/blaine-azerothcore.git`.
- Local HEAD, local `origin/main`, and remote `refs/heads/main` all equaled the starting commit.
- The expected commit was current and an ancestor; ADR-0013 and VAL-0013 existed; lifecycle references remained S0.
- Tracked files: 86. Governance storage: `/dev/sda1`, exFAT, read/write, approximately 954 GiB available.
- `linux/upstream/`, `manifests/sources/`, and the intended clone did not exist.

## Docker and Buildx invariant check

Read-only checks passed: Docker client/server 29.6.1, Compose v5.3.1, RootlessKit 3.0.1, active `rootless` context, approved user socket, rootless security, `fuse-overlayfs`, and `/home/deck/.local/share/docker` on internal ext4. The selected context-derived `rootless` Docker-driver builder was running with BuildKit v0.31.1. Buildx v0.35.0 remained a regular `deck:deck` mode-0755 plugin with SHA-256 `d41ece72044243b4f58b343441ae37446d9c29a7d6b5e11c61847bbcf8f7dfda`. No rootful service/socket existed. Zero visible images and containers were present. No runtime command was executed beyond inspection.

## Parent protection

Added the exact rule:

```gitignore
# Official upstream source checkouts — governed separately and never vendored
linux/upstream/azerothcore-wotlk/
```

Created `linux/upstream/README.md`. Before cloning, `git check-ignore --no-index` proved the intended clone paths ignored while the directory README remained eligible. After acquisition, `git check-ignore -v` identified only the exact governed rule for both nested `.git/HEAD` and an upstream source path, and `git ls-files` confirmed no upstream path tracked.

## Official upstream verification and acquisition pin

Command, executed twice before clone:

```text
git ls-remote https://github.com/azerothcore/azerothcore-wotlk.git HEAD refs/heads/master
```

Both calls exited 0 and returned `34a8bd6655c02448d3da6195dcd00647f634dde3` for `HEAD` and `refs/heads/master`. The official identity did not redirect to another organization/repository. The research reference `81a8c779bd16417d6b69390060777b3db7a9f703` exists as a commit and is an ancestor, so upstream advanced. A post-acquisition query at `2026-07-15T05:28:46+00:00` still returned the pin.

## Clone, origin, and object verification

Executed:

```text
git clone --branch master --single-branch --no-checkout https://github.com/azerothcore/azerothcore-wotlk.git /run/media/deck/blAIneXPLAT/azerothcore/linux/upstream/azerothcore-wotlk
```

The full transfer was allowed to finish before verification. An early read-only verification raced the active `index-pack` and temporarily saw no refs; process inspection proved the original clone was still active, so no removal or second clone occurred. After exit 0:

- origin fetch/push URL exactly matched official upstream;
- fetch mapping was `+refs/heads/master:refs/remotes/origin/master`;
- `--is-shallow-repository` was false;
- no partial-clone or promisor configuration existed;
- `origin/master` equaled the acquisition pin;
- the pin was a commit and an ancestor of `origin/master`;
- `git fsck --full --strict` exited 0;
- one pack contained 210,174 objects, size approximately 1.23 GiB, with zero garbage.

No garbage collection, repack, submodule, or LFS command was run.

## Tree-fidelity audit and stop result

The pinned tree is `25ad25f5fb8e119f68fef69b080934f1182ad8d6`. Direct Git-tree inspection found 10,011 paths, 9,968 non-executable regular files, 42 executables, one symbolic link, zero Gitlinks, zero case-fold collision groups, zero exFAT-invalid names, no `.gitmodules`, and no LFS pointer/filter declaration.

The symlink is `.claude/skills/generate-pr-description` -> `../../.agents/skills/generate-pr-description`. A disposable exFAT probe attempted `ln -s` and failed with `Operation not permitted`; the ordinary target probe file was removed and no probe residue remained.

This triggered the required checkout-fidelity stop. `git checkout --detach` was not run. The full verified no-checkout object repository was retained. The clone has no physical source files, and the initial no-checkout index/branch representation may display the absent tree as deletions; this is not a modified checkout and must not be used for a build. Source-object acquisition is PASS; checkout/build readiness is DEFERRED; overall source acquisition is not full PASS.

## Pinned commit and deterministic evidence

- Pin: `34a8bd6655c02448d3da6195dcd00647f634dde3`.
- Tree: `25ad25f5fb8e119f68fef69b080934f1182ad8d6`.
- Parent: `f8b4e180a5d9f9fe4e50d7d6af0bcdaeeec1bd98`.
- Author/date: Kitzunu, `2026-07-15T05:13:13+02:00`.
- Committer/date: GitHub, `2026-07-15T00:13:13-03:00`.
- Subject: `fix(Core/Calendar): correct malformed mail subject when deleting a ca… (#26615)`.
- Signature: present but locally unverifiable (`%G? = E`; public key unavailable).
- Streamed deterministic archive SHA-256: `26375e7744b7b767c628c3bbaba159e919b04947b647e0dfc7ba5bc77d2556b1`; no archive was written.
- Root license: GNU GPL version 2 text; blob and content hashes recorded in the manifest.

## Source inventory

Logical pinned tree: 10,011 files/paths, 464 directories, 897,467,746 blob bytes. The object database is approximately 1.3 GiB. The no-checkout physical working tree contains zero source files and no checkout subdirectories. The largest 20 logical files are source-controlled SQL definitions; the largest is 76,428,259 bytes. These are source definitions, not initialized database state.

Forty-two executable entries and the one symlink were inventoried. No Gitlink/submodule or LFS dependency exists. The longest path is 104 bytes and all path names passed exFAT character checks. Exact counts, symlink, key hashes, and license are in the source manifest.

## Static build-definition inventory

No definition was executed. The root `docker-compose.yml` defines seven services: database, database import, worldserver, authserver, client-data initialization, tools, and development server. It defines one application network and four named volumes.

The primary build context is repository root. `apps/docker/Dockerfile` defines skeleton, build, runtime, authserver, worldserver, db-import, client-data, and tools stages; `apps/docker/Dockerfile.dev-server` defines the dev stage. Root CMake enters at `CMakeLists.txt`; additional dependency/server/tool CMake entry points exist. `acore.sh` and `bin/acore` form dashboard/wrapper entry points. Expected generated areas include `var/build`, `var/ccache`, and `env/dist` paths.

Upstream Compose includes environment-overridable host publications whose defaults map database, auth, world, and SOAP service ports. These definitions are inventory only: no exact port is approved for blAIne exposure, no port was published, and the network-boundary ADR remains controlling. Compose contains credential-bearing database connection/default fields and an env-file reference; values were not reproduced in governance records and require later secret governance.

No active `privileged` or host-network declaration and no Compose secret object were found in the root definition. The devcontainer example contains commented Docker-socket/ptrace examples; they are not approved.

## External acquisition behavior identified

- External base/runtime image references include `ubuntu:24.04`, `mysql:8.4`, and locally named `acore/ac-wotlk-*` outputs.
- Dockerfile build stages run Ubuntu `apt-get update/install`, requiring package-network access during a future build.
- `Dockerfile.dev-server` declares an external Dockerfile frontend and installs development packages; it is not selected for the clean production baseline.
- The client-data image installs curl/unzip, then its runtime command invokes `inst_download_client_data`.
- `apps/installer/includes/functions.sh` resolves an official-release default and downloads/extracts `wowgaming/client-data` `data.zip`; this would acquire DBC/map/VMap/MMap-related client data and was not executed.
- The tools profile binds a game-client `Data` path for local extraction; no client path or asset was supplied.
- Module-management code contains GitHub/API/catalog acquisition behavior; no catalog, repository, or module was acquired.
- Installer OS scripts contain apt/brew/wget operations; none was run.
- The database-import stage copies pinned repository SQL and modules into an image and would initialize/import only when later run; no separate database release download was identified in that target, and no database operation occurred.

## Build-compatibility questions deferred

The main Dockerfile uses a BuildKit bind mount of `.git` and copies working-tree paths, so the present no-checkout clone is unusable. A later operation must resolve symlink-faithful placement, exFAT bind/file-mode semantics, approved output/cache storage, explicit versus implicit Compose selection of the already established `rootless` builder, external base-image/package acquisition, expected cache/image size, credential injection, client-data separation, and default publication suppression. Expected image count/size and runtime compatibility remain unvalidated.

## Files created and updated

Created: ADR-0014, this RUN, VAL-0014, the source-management document, source manifest, and `linux/upstream/README.md`. Updated: root `.gitignore`, root `README.md`, and server build-sequence requirements. The ignored upstream clone is an independently governed object repository, not a parent-repository file set.

## Actions explicitly not performed

No source checkout, source modification, module, submodule, LFS pull, archive export, Docker/Buildx/Compose build, image pull, registry authentication, container, database, client data, client, map/DBC/VMap/MMap extraction, compiler, server, port, network, or runtime operation occurred. No upstream push/fork/branch/tag was created.

## Staged audit, publication, and lifecycle

The staged set contained exactly nine intended paths: six new Markdown governance/source documents, `linux/upstream/README.md`, and narrow updates to `.gitignore`, root `README.md`, and server build-sequence requirements. All staged modes were 100644. Cached status, stat, name-status, whitespace, complete diff, file-mode, path-only secret/binary, restricted-content, and upstream-boundary checks passed. No source checkout path, nested Git content, executable, binary, archive, Dockerfile copy, database/client data, credential, private network detail, historical RUN/VAL change, or lifecycle advancement was staged.

Governance commit `abe2b13fc44e2b10a326de3e397e628419b388ef`, message `Acquire and pin official AzerothCore source`, was created with parent `38c1e515d47564fe7f04f3d55503785b104ce5a7` and pushed normally as a fast-forward. After the first push, local HEAD, local `origin/main`, and remote `refs/heads/main` all equaled `abe2b13fc44e2b10a326de3e397e628419b388ef`; starting-history ancestry passed and the governance tree was clean.

Completing this RUN and VAL changes their bytes after the first push. One validation-only commit with message `Record official AzerothCore source validation` is therefore required. Its object ID and final three-ref equality are necessarily captured after commit and reported in the operation’s final response; a commit cannot contain its own object ID.

No full source-checkout validation PASS is claimed. Lifecycle remains **S0 — Proposed**.

--- RUN-0015-establish-internal-ext4-azerothcore-baseline-checkout.md ---
# RUN-0015 — Establish Internal ext4 AzerothCore Baseline Checkout

## Record control

- Date: 2026-07-14 (America/Phoenix)
- Verification window: `2026-07-14T22:55:03-07:00` through `2026-07-14T23:00:52-07:00` and subsequent publication work
- Lifecycle before and after: `S0 — Proposed`
- Objective: establish `CHK-ACORE-WOTLK-001` as an independent, symlink-faithful internal ext4 checkout of `SRC-ACORE-WOTLK-001`, validate static build-context structure, publish governance evidence, and stop before build/runtime work.
- Governance root: `/run/media/deck/blAIneXPLAT/azerothcore/`
- Portable source-object repository: `/run/media/deck/blAIneXPLAT/azerothcore/linux/upstream/azerothcore-wotlk/`
- Internal checkout: `/home/deck/.local/share/blAIne/azerothcore/checkouts/SRC-ACORE-WOTLK-001/`
- Starting governance commit: `1e74a39cec174d8372f0cc2e0308417205b17023`
- Publication state in this revision: technical validation, staged audit, governance commit, and first normal push verified; completed evidence is ready for the single validation-only follow-up commit.

## Authorization boundary

Persistent writes were limited to the governance repository, the exact internal checkout and its necessary parents, plus an immediately removed owner-only ext4 probe. No sudo, package/SteamOS change, worktree link, shared/reference clone, hardlink, alternates dependency, source modification, module, submodule, LFS, hook/script execution, Docker/Buildx/Compose build, image pull, container, database, client data, port, server, network change, fork, or upstream push was authorized or performed.

## Governance starting state

- Canonical governance root and `main` branch matched authorization.
- Working tree was clean and no active Git operation existed.
- Origin exactly matched the authorized SSH remote.
- Local HEAD, local `origin/main`, and remote main all equaled `1e74a39cec174d8372f0cc2e0308417205b17023`; expected history was current.
- ADR-0014, RUN-0014, VAL-0014, and `SRC-ACORE-WOTLK-001` existed and preserved the object-PASS/checkout-DEFERRED split.
- Tracked-file count was 92. Governance storage remained read/write exFAT with approximately 953 GiB free. Lifecycle remained S0.

## Portable source-object verification

The portable repository retained official origin, master-only fetch mapping, non-shallow/non-partial status, pin commit `34a8bd6655c02448d3da6195dcd00647f634dde3`, tree `25ad25f5fb8e119f68fef69b080934f1182ad8d6`, and one pack with 210,174 objects. `git fsck --full --strict` exited 0. No garbage, alternates, or promisor configuration appeared.

The streamed `git archive` digest remained `26375e7744b7b767c628c3bbaba159e919b04947b647e0dfc7ba5bc77d2556b1`. Official `HEAD` and `master`, observed at `2026-07-15T05:55:03+00:00`, still equaled the approved pin. No fetch or pin update occurred.

## Internal filesystem and capacity preflight

The destination and its new parent chain were absent initially. `/home/deck` resolved to `/dev/nvme0n1p8[/deck]`, ext4, read/write, owned by `deck`; 1,168,697,995,264 bytes (about 1.1 TiB) were available, exceeding the 5 GiB gate.

An owner-only mode-0700 probe on the same filesystem verified and immediately removed:

- symbolic link creation and exact `readlink` text;
- mode 0755 persistence and executable access;
- coexistence of two case-distinct filenames;
- an ordinary AzerothCore-style filename; and
- a 125-byte relative path, exceeding the pinned 104-byte longest path.

Probe residue count was zero. Only `blAIne/azerothcore/checkouts` parents were created, all `deck:deck`, mode 0755, real directories, and canonically beneath `/home/deck/.local/share/`. The final destination was still absent immediately before clone.

## Independent clone and transfer

Executed exactly:

```text
git clone --no-local --branch master --single-branch --no-checkout /run/media/deck/blAIneXPLAT/azerothcore/linux/upstream/azerothcore-wotlk /home/deck/.local/share/blAIne/azerothcore/checkouts/SRC-ACORE-WOTLK-001
```

The clone completed once with exit 0; no competing verification or second clone occurred during transfer. Before origin change, origin recorded the local materialization path, fetch scope remained master-only, shallow=false, partial/promisor state absent, `origin/master` equaled the pin, and strict full object verification passed. The independent pack contained 210,174 objects and was approximately 1.23 GiB.

## Independence evidence

- `.git` was a real directory.
- `.git/objects/info/alternates` and `.git/commondir` were absent.
- No alternates, partial-clone, or promisor configuration existed.
- Internal pack, index, and reverse-index files were regular files on device 66312, each link count 1.
- Portable pack files were on device 2049, each link count 1; names/inodes/devices differed.
- Git directory, common directory, and object directory all resolved inside the internal checkout.

No shared-object or hardlink dependency was detected. Independence passed before origin change and checkout.

## Authoritative origin and Git configuration

The new clone's origin was changed, without fetch, to `https://github.com/azerothcore/azerothcore-wotlk.git`. Fetch/push output and local config showed only that official origin; master-only fetch mapping remained.

`core.filemode=true`; `core.symlinks` and `core.ignorecase` were unset with positive ext4 semantic evidence and later faithful checkout evidence. No clean/smudge filter, sparse checkout, custom active hook, Gitlink, `.gitmodules`, LFS pointer, partial-clone setting, promisor remote, or external object control was present. No configuration value was silently overridden.

## Detached checkout and fidelity

`git checkout --detach 34a8bd6655c02448d3da6195dcd00647f634dde3` exited 0. HEAD and tree equaled the approved values. Branch status was `## HEAD (no branch)`. `git diff --check`, `diff-files --quiet`, and `diff-index --quiet HEAD --` passed; describe returned `v1.0.1-18266-g34a8bd665`; no untracked/ignored path existed.

The blocking link `.claude/skills/generate-pr-description` was a real filesystem symbolic link, Git mode 120000, with exact text `../../.agents/skills/generate-pr-description`. It resolved to `.agents/skills/generate-pr-description` inside the checkout and its target existed.

All 42 Git mode-100755 entries retained owner execution. All 9,968 mode-100644 entries had no owner-executable mismatch. There were zero missing tracked paths, 10,011 tracked paths total, 464 physical directories, 10,010 regular files, one symlink, zero Gitlinks, zero LFS requirements, and zero case-fold collisions. The longest path remained 104 bytes.

Working-tree apparent bytes were 897,467,746 (about 880 MiB via `du -sh`), `.git` approximately 1.3 GiB, and total checkout 2,229,925,046 bytes (about 2.2 GiB). Final internal free space was 1,166,446,243,840 bytes. The 20 largest files matched the pinned logical SQL inventory. The streamed archive SHA-256 again matched the approved value.

One inventory pipeline's `sort` reported a harmless broken pipe after `head` consumed the required 20 lines; subsequent counts and digest passed, and no state changed.

## Self-contained Git structure

`.git`, common directory, and object directory all resolved inside the checkout. `.git` was a directory, not a linked-worktree pointer. No `commondir`, alternates file, external object directory, or operational absolute host path was configured. Clone-source absolute paths remained only in reflog provenance text; they do not affect ordinary object lookup.

## Static build-context review

Classification: **STRUCTURAL BUILD-CONTEXT PREREQUISITES PASS**.

- Root Compose build contexts are `.` and referenced Dockerfiles exist.
- Required `CMakeLists.txt`, `conf`, `deps`, `src`, `modules`, `apps`, and Docker/Compose paths exist.
- `.dockerignore` does not omit `.git`.
- `apps/docker/Dockerfile` bind-mounts `source=.git` to `/azerothcore/.git`; the source is a real self-contained directory.
- Pin, refs, tags, and objects are available to the CMake revision commands (`git describe`, `git show`, and `git rev-parse`).
- The single symlink and executable modes are faithfully present for a future context transfer.

No build, Compose interpolation, external image/package acquisition, compilation, cache creation, or image inspection was performed. Actual image-build readiness remains a later validation boundary.

## Docker and Buildx invariants

An initial restricted-namespace read-only check could not access the user socket or user bus and reported permission denied. It changed no state. The check was repeated from the authoritative host context and passed: Docker Engine 29.6.1, Compose v5.3.1, RootlessKit 3.0.1, Buildx v0.35.0 with the approved checksum, active `rootless` context, running rootless Docker-driver builder/BuildKit v0.31.1, rootless security, internal data root, and `fuse-overlayfs`. Rootful services/socket remained absent. Visible images, containers, and volumes were zero; only default bridge/host/none networks existed.

## Governance files

Created:

- `records/decisions/ADR-0015-internal-ext4-independent-azerothcore-baseline-checkout.md`
- `docs/source/azerothcore-internal-baseline-checkout-management.md`
- `manifests/checkouts/CHK-ACORE-WOTLK-001.md`
- this RUN record
- `records/validations/VAL-0015-internal-ext4-azerothcore-baseline-checkout-validation.md`

Updated current documents: source manifest, official-source management, root README, and server build-sequence requirements. ADR-0014, RUN-0014, and VAL-0014 historical evidence was not changed.

## Actions explicitly not performed

No source edit, patch, format, generated file, module, submodule, LFS, hook/script, `acore.sh`, CMake, compiler, installer, Docker/Buildx/Compose build, image pull, registry authentication, container, database, client data, map/DBC/VMap/MMap, client/addon/patch/corpus, port, service, network configuration, upstream fetch/push, fork, or branch was performed.

## Publication and lifecycle

The staged set contained exactly nine intended Markdown paths: five new ADR/policy/manifest/RUN/VAL documents and four narrowly updated current documents. All staged modes were 100644. Cached status, stat, name-status, whitespace, complete diff, file-mode, path-only secret/binary, object-pack, copied-build-definition, restricted-content, historical-record, and lifecycle checks passed. No internal checkout/source, nested Git data, pack, executable, binary, Dockerfile, generated archive, temporary probe/log, credential, private network detail, client/game asset, or unrelated path was staged.

Governance commit `6f69f87a0f3a64a14bdd9adb5f9eaeecf8b0cd32`, message `Establish internal AzerothCore baseline checkout`, was created with parent `1e74a39cec174d8372f0cc2e0308417205b17023` and pushed normally as a fast-forward. After the first push, local HEAD, local `origin/main`, and remote main all equaled `6f69f87a0f3a64a14bdd9adb5f9eaeecf8b0cd32`; starting-history ancestry passed and the governance tree was clean.

Completing RUN-0015 and VAL-0015 changes their bytes after the first push. One validation-only commit with message `Record internal AzerothCore checkout validation` is therefore required. Its object ID and final three-ref equality are necessarily captured after commit and reported in the final operation response; a commit cannot contain its own object ID.

Technical checkout validation and structural build-context prerequisites pass. Actual image-build validation remains not run. Lifecycle remains **S0 — Proposed**.

--- VAL-0014-official-azerothcore-source-acquisition-validation.md ---
# VAL-0014 — Official AzerothCore Source Acquisition Validation

## Record control

- Date: 2026-07-14
- Subject: `RUN-0014`, `SRC-ACORE-WOTLK-001`
- Branch: `main`
- Status: **SPLIT — source-object acquisition PASS; checkout/build readiness DEFERRED; overall NOT FULL PASS**
- Lifecycle: `S0 — Proposed`

Full PASS is prohibited because the authoritative exFAT mount cannot represent the one pinned symbolic-link entry. The verified no-checkout Git object repository is retained, and no inaccurate working tree was created.

## Validation matrix

| Assertion | Result | Evidence |
|---|---|---|
| Correct governance repository/remote | PASS | Canonical authorized root; exact SSH origin. |
| Synchronized clean start | PASS | HEAD, origin/main, and remote main were `38c1e515d47564fe7f04f3d55503785b104ce5a7`; clean main; no active Git operation. |
| Lifecycle at start | PASS | README/GOVERNANCE/VAL-0013 reported S0 — Proposed. |
| Docker/Buildx prerequisites unchanged | PASS | Rootless Docker 29.6.1, Compose 5.3.1, Buildx 0.35.0 official checksum, selected rootless builder, fuse-overlayfs/internal data root. |
| Correct official upstream | PASS | Exact `https://github.com/azerothcore/azerothcore-wotlk.git` origin. |
| Master ref resolved consistently | PASS | Two pre-clone observations and one post-clone observation all returned the pin. |
| Acquisition pin recorded | PASS | `34a8bd6655c02448d3da6195dcd00647f634dde3`; research SHA is its ancestor. |
| Full-history single-branch clone | PASS | Exact clone flags and master-only fetch mapping. |
| Repository not shallow/partial | PASS | Shallow=false; no partial/promisor configuration. |
| Git object integrity | PASS | `git fsck --full --strict`, exit 0; no garbage after completed clone. |
| Pin from official master | PASS | `origin/master` equals pin; commit object present; ancestry check exit 0. |
| Tree identity | PASS | `25ad25f5fb8e119f68fef69b080934f1182ad8d6`. |
| Deterministic archive digest | PASS | Streamed SHA-256 `26375e7744b7b767c628c3bbaba159e919b04947b647e0dfc7ba5bc77d2556b1`; no archive stored. |
| License recorded | PASS | Root GPL version 2 text and blob/content identities recorded. |
| Case-fold/path-name audit | PASS | Zero case collisions; zero exFAT-invalid names. |
| Symlink/executable audit | PASS inventory | One symlink and 42 executables identified. |
| Filesystem representability | FAIL at authorized path | exFAT `ln -s` probe returned `Operation not permitted` for required symlink semantics. |
| Detached pinned checkout | DEFERRED | Checkout deliberately not run after representability failure. |
| Clean upstream working tree | NOT APPLICABLE | No working tree exists; clone remains no-checkout. |
| Gitlinks/submodules | PASS | Zero Gitlinks; `.gitmodules` absent; no submodule command run. |
| LFS | PASS | No LFS filter declaration or pointer detected; no LFS command run. |
| Build definitions inventoried | PASS static | Compose services, Dockerfiles/stages, CMake/wrappers, contexts, images, volumes, networks, publications, health/dependency behavior recorded. |
| External acquisition inventoried | PASS static | Base images, apt operations, client-data download, module/catalog and installer network paths identified without execution. |
| Client-data behavior | PASS static | Runtime client-data initializer and tools extraction path identified; nothing downloaded or extracted. |
| Source modification/module addition | PASS containment | Zero physical source files checked out; no patch, edit, module, or branch. |
| Image build/pull | PASS containment | None. |
| Container/runtime | PASS containment | No container created or started; visible counts remained zero at preflight. |
| Database | PASS containment | No database created, imported, initialized, or started. |
| Client/game assets | PASS containment | No client, DBC, map, VMap, MMap, addon, patch, or Blizzard asset acquired. |
| Port/network exposure | PASS containment | No port, listener, Docker/network setting, firewall, router, DNS, VPN, tunnel, proxy, or ingress change. |
| Parent ignore boundary | PASS | Exact rule applies to clone `.git` and source paths; no upstream path tracked or staged. |
| Manifest accuracy | PASS pre-publication | Split object/checkout state, counts, hashes, license, and boundaries match evidence. |
| README/current sequence alignment | PASS pre-publication | Current state will report object acquisition and checkout deferral without claiming a build. |
| Secret/restricted publication | PASS pre-staging | Records contain no credential values, client assets, source vendoring, binary, or private network detail. |
| Governance commit/push | PASS | Commit `abe2b13fc44e2b10a326de3e397e628419b388ef` pushed normally as a fast-forward; no force push. |
| Governance refs after first push | PASS | Local HEAD, origin/main, and remote main all equaled `abe2b13fc44e2b10a326de3e397e628419b388ef`; starting history remained an ancestor. |
| Lifecycle remains S0 | PASS | No advancement authorized or recorded. |

## Split classification

### Source-object acquisition: PASS

Official full-history objects, exact master pin, ancestry, tree, strict integrity, deterministic digest, license, and static build/acquisition inventory are verified and retained.

### Source-checkout/build readiness: DEFERRED

The pinned Git tree requires a symlink that exFAT cannot create. The operation correctly stopped before checkout. The clone therefore has no source working tree, is not detached at a checked-out pin, and cannot be supplied to the upstream Docker build. A later governed decision must establish a symlink-faithful source location or mechanism and repeat checkout validation.

### Overall functional result: NOT FULL PASS

This result is not a source-integrity failure and does not authorize a workaround, altered tree, archive expansion, or build. It is a physical checkout-fidelity blocker.

## Publication validation

The first publication staged exactly the nine intended text/governance paths. Every staged object was mode 100644; cached whitespace and complete-diff review passed; path-only secret/binary findings were zero; no upstream source path appeared in the index. Commit `abe2b13fc44e2b10a326de3e397e628419b388ef` was pushed normally and all three refs matched it.

Completing RUN-0014 and this validation record requires the one authorized validation-only commit. Its object ID and final local/origin/remote equality must be captured after that commit and normal push in the final operation report. Governance publication success does not change the overall source result from split/not-full-PASS.

## Conclusion

Object acquisition and provenance pass; checkout fidelity and build readiness are deferred on the current exFAT path. No source was modified, no restricted content was published, no build/runtime/client/database action occurred, and lifecycle remains **S0 — Proposed**.

--- ADR-0014-official-azerothcore-source-clone-and-baseline-pin.md ---
# ADR-0014: Official AzerothCore Source Clone and Baseline Pin

- Status: Accepted at S0 — Proposed; checkout implementation deferred by filesystem fidelity gate
- Date: 2026-07-14
- Scope: Clean unmodified AzerothCore WotLK source identity and custody
- Related decisions: `ADR-0010`, `ADR-0011`, `ADR-0013`
- Related evidence: `SRC-ACORE-WOTLK-001`, `RUN-0014`, `VAL-0014`

## Context

The clean baseline requires an exact, reviewable AzerothCore source identity before any image build, database initialization, client-data acquisition, or server startup. The governance repository must publish provenance without vendoring a large independently maintained upstream Git repository or its database.

At acquisition, official `azerothcore/azerothcore-wotlk` `master` resolved twice to `34a8bd6655c02448d3da6195dcd00647f634dde3`. The full-history object repository passed strict verification. Its pinned tree contains one symbolic-link entry, `.claude/skills/generate-pr-description`, targeting `../../.agents/skills/generate-pr-description`. The authoritative exFAT mount rejects symbolic-link creation. A faithful working tree therefore cannot be approved at the present physical path.

## Decision

Acquire the official `azerothcore/azerothcore-wotlk` `master` branch as a full-history, single-branch upstream clone; pin `SRC-ACORE-WOTLK-001` to the exact acquisition-time commit; exclude the physical clone from the blAIne governance repository; and preserve source identity through a tracked manifest, commit/tree identifiers, deterministic archive digest, and validation evidence.

The approved source identity is:

| Property | Decision |
|---|---|
| Source | `https://github.com/azerothcore/azerothcore-wotlk.git` |
| Branch strategy | Full-history, single-branch `master` |
| Pin | `34a8bd6655c02448d3da6195dcd00647f634dde3` |
| Tree | `25ad25f5fb8e119f68fef69b080934f1182ad8d6` |
| Identifier | `SRC-ACORE-WOTLK-001` |
| Physical object clone | `linux/upstream/azerothcore-wotlk/` |
| Parent Git eligibility | Ignored; never vendored or staged |
| Intended checkout state | Detached HEAD at the pin, clean and faithful |
| Current checkout state | No checkout; deferred because exFAT cannot represent the pinned symlink |

The no-checkout object repository is retained as verified provenance. It is not a build-ready source tree. A later ADR or bounded operation must approve a symlink-capable source location or another demonstrably faithful checkout mechanism before detached checkout and build preparation can proceed.

## Rationale and alternatives

- A shallow clone is rejected because it weakens ancestry, update, and provenance review.
- An archive acquisition is rejected because it omits Git history and object relationships.
- Vendoring is rejected because it would mix upstream source with governance history and make accidental publication likely.
- A Git submodule is not introduced because the physical clone is governed independently and no parent-repository source dependency is yet approved.
- Forcing checkout on exFAT is rejected because materializing the symlink as an ordinary file would not faithfully represent the pinned tree.
- Building directly from the no-checkout object repository is rejected because required source paths are absent.

## Clean-baseline and update policy

The pinned baseline must not be edited, patched, formatted, generated into, or supplied with custom modules. An update must resolve official `master` again, review the old-to-new commit range, repeat object, license, LFS, Gitlink, case, path, symlink, build-definition, acquisition-behavior, and deterministic-digest validation, and update the manifest through a separate governed decision. Moving `origin/master` does not silently move the approved pin.

Future custom work must use separately governed branches, modules, forks, or repositories. Upstream contributions require their own fork/branch and contribution review; they must not mutate this evidence clone.

## Build and runtime relationship

ADR-0013 establishes the checksum-verified Buildx v0.35.0 plugin and the existing rootless Docker-driver builder. That prerequisite remains intact, but it does not overcome source-filesystem fidelity. A future build must use a faithful source checkout, review the upstream Docker/Compose acquisition behavior, and govern the exact Buildx/Compose invocation. No Docker image, database, client data, module, container, port, authserver, or worldserver is authorized by this ADR.

## License obligations

The root `LICENSE` blob `ecbc0593737be657aef92e3adcf3bcbd6fdb812e` contains GNU GPL version 2 text. Future distribution, modification, images, and derivative work must preserve applicable GPLv2 and bundled dependency-license obligations. This record is an inventory, not legal advice.

## Rollback and removal

If separately authorized, removal may delete only the ignored clone at `linux/upstream/azerothcore-wotlk/` after confirming its origin, identifier, and absence of unique modifications. Tracked manifest and validation evidence are preserved. No automatic removal is approved, and no source object is pushed upstream.

## Deferred decisions and lifecycle

Deferred: faithful checkout placement, detached-HEAD completion, build invocation, cache placement, image set, database initialization, client-data handling, runtime configuration, and service/network exposure. The lifecycle remains **S0 — Proposed**.

--- ADR-0015-internal-ext4-independent-azerothcore-baseline-checkout.md ---
# ADR-0015: Internal ext4 Independent AzerothCore Baseline Checkout

- Status: Accepted at S0 — Proposed
- Date: 2026-07-14
- Scope: Symlink-faithful, self-contained working checkout for the clean baseline
- Related decisions: `ADR-0013`, `ADR-0014`
- Related evidence: `SRC-ACORE-WOTLK-001`, `CHK-ACORE-WOTLK-001`, `RUN-0015`, `VAL-0015`

## Context

ADR-0014 acquired and verified official full-history source objects for `SRC-ACORE-WOTLK-001`, but the portable exFAT path could not represent the pinned tree's symbolic link. The portable object repository remains valid provenance, while a build-input working tree requires Linux symlink and executable-mode semantics. The pinned Dockerfile also bind-mounts `.git` into its build stage, so a linked worktree with a plain `.git` pointer file is not accepted without later build evidence.

## Decision

Materialize `SRC-ACORE-WOTLK-001` as an independent, full-history Git clone on internal ext4 storage; copy objects from the verified portable source-object repository using `git clone --no-local`; set the resulting clone's authoritative origin to the official AzerothCore repository; and check out the approved pin in detached-HEAD state with a self-contained `.git` directory.

| Property | Approved value |
|---|---|
| Checkout identifier | `CHK-ACORE-WOTLK-001` |
| Source identifier | `SRC-ACORE-WOTLK-001` |
| Internal path | `/home/deck/.local/share/blAIne/azerothcore/checkouts/SRC-ACORE-WOTLK-001/` |
| Materialization source | Verified portable object repository at `linux/upstream/azerothcore-wotlk/` |
| Authoritative origin | `https://github.com/azerothcore/azerothcore-wotlk.git` |
| Pin | `34a8bd6655c02448d3da6195dcd00647f634dde3` |
| Tree | `25ad25f5fb8e119f68fef69b080934f1182ad8d6` |
| Filesystem | Internal ext4 under `/home/deck` |
| Checkout state | Detached, clean, unmodified |

## Rationale

Internal ext4 is required because it preserves the pinned symlink and executable modes that exFAT could not. An independent clone is used instead of `git worktree add` so `.git` is a real, self-contained directory in the build-context root. `--no-local` is required to copy Git objects rather than create hardlinks. Shared clones, reference clones, object alternates, and hardlink dependencies are prohibited because the checkout must remain usable without consulting the portable repository.

The portable repository is the materialization transport only. The official GitHub repository remains the authoritative upstream identity. Changing the new clone's origin does not fetch or move the approved pin.

## Clean-baseline boundary

The checkout must remain detached at the exact source pin, clean, and free of patches, generated changes, custom modules, database state, client data, build output, and runtime state. It is not a custom development branch. Later modifications require a separate governed source path, branch, module, fork, or repository.

## Structural build-context result

**STRUCTURAL BUILD-CONTEXT PREREQUISITES PASS.** The checkout contains all source-copy and root-context paths referenced by the pinned Compose/Docker definitions. `.git` is a real internal directory containing the pin, refs, and independent objects; `.dockerignore` does not exclude it; and the Dockerfile's `source=.git` BuildKit mount expects a directory. Symlink and executable modes are faithful. Local-clone provenance appears only in reflog text and creates no object/configuration dependency.

This classification does not validate Docker Buildx, Compose interpolation, image inputs, compilation, cache behavior, external downloads, image contents, databases, client data, or runtime services.

## Update procedure

Do not move this checkout by fetching or checking out a moving branch. A source update requires a new governed source resolution, commit-range review, manifest update, object verification, and preferably a separately identified checkout. The existing checkout remains the immutable comparison baseline until replacement is explicitly approved.

## Removal and recovery

Removal requires separate authorization and must first prove exact path, identifier, official origin, detached pin, clean status, and absence of unique work. Remove only the checkout and only remove operation-created parent directories if empty. Preserve governance records and the portable object repository.

Because objects are copied, the checkout remains verifiable and usable for read-only Git operations if the portable drive is unavailable. Recovery may use its self-contained `.git` database and official origin, but any network fetch, replacement clone, or pin change requires separate authorization.

## Capacity and relationships

The checkout consumes approximately 2.2 GiB total: about 880 MiB working tree and 1.3 GiB `.git`. More than 1.1 TiB remained available on internal ext4 after creation. ADR-0014 continues to govern official source identity and the historical exFAT failure. ADR-0013 continues to govern the rootless Buildx toolchain. Neither decision authorizes an image build here.

## Deferred operations and lifecycle

Actual clean-baseline image building, image pulls, package acquisition, cache governance, database initialization, client-data acquisition, service startup, and network validation remain separate operations. Lifecycle remains **S0 — Proposed**.
(deck@ExosSteamDeck engineering-rag-corpus)$

## Assistant

The new evidence clarifies one important point: **the CICS copy was designed to be synchronized from a moving `master` branch, not pinned to a specific commit.** Its sync script runs `git pull origin master` twice—once for the CICS repository and once inside `wiki/`—then commits and pushes the resulting change.

That gives us a plausible mechanism for the inconsistency, but it does not yet identify the exact Wiki revision represented by the old-drive copy.

The `_config.yml` is a Jekyll presentation-site configuration. Its `ac_wiki_version: 2.0.5` comment explicitly says that value is used internally for updating the remote theme. **It is not evidence that the documentation itself came from Wiki version 2.0.5.** Likewise, `git_branch: "master"` tells us which branch the site expects, not which commit was copied.

The AzerothCore records you supplied are for the separate `azerothcore/azerothcore-wotlk` game-server repository. They establish a well-documented July 14–15, 2026 acquisition of that repository, but they do not establish the provenance of `azerothcore/wiki`. We should keep those two source histories separate.

## Next: establish where the Wiki repository actually sits

There is a structural ambiguity we need to resolve before interpreting the file differences: the sync script assumes a nested `wiki/` Git repository, while the path we compared is named `official/wiki`. We need to establish whether that path is the nested repository, a copied site root, or a directory containing another `wiki/` directory.

Run this read-only diagnostic in Konsole:

```bash
BASE="/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs"

echo "========== DIRECTORY STRUCTURE =========="
for d in "$BASE" "$BASE/official" "$BASE/official/wiki" "$BASE/official/wiki/wiki"; do
    if [ -d "$d" ]; then
        echo
        echo "--- $d ---"
        ls -ld "$d"
        [ -e "$d/.git" ] && ls -ld "$d/.git" || echo "No .git entry here"
        [ -f "$d/sync-wiki.sh" ] && echo "Contains sync-wiki.sh"
    fi
done

echo
echo "========== GIT REPOSITORY DISCOVERY =========="
for d in "$BASE" "$BASE/official" "$BASE/official/wiki" "$BASE/official/wiki/wiki"; do
    [ -d "$d" ] || continue
    echo
    echo "--- Checking $d ---"
    if root=$(git -C "$d" rev-parse --show-toplevel 2>/dev/null); then
        echo "Git root: $root"
        echo "HEAD: $(git -C "$d" rev-parse HEAD)"
        echo "Branch: $(git -C "$d" branch --show-current)"
        git -C "$d" remote -v
        git -C "$d" log -1 --format='Last commit: %H%nDate: %cI%nSubject: %s'
    else
        echo "Not inside a Git working tree"
    fi
done

echo
echo "========== SYNC AND SUBMODULE FILE LOCATIONS =========="
find "$BASE" -maxdepth 4 \( -name sync-wiki.sh -o -name .gitmodules -o -name .git \) -print 2>/dev/null
```

This should tell us whether any Git metadata survived in the old-drive copy, whether the sync script belongs to the parent site or the Wiki itself, and whether the directory layout matches the script's assumptions.

**What we are trying to distinguish:**

1. A legitimate older upstream Wiki revision.
2. A partially synchronized or incomplete copy.
3. A site export or copy that omitted files.
4. A Wiki revision with local edits.
5. A mixture of those conditions.

The 688 identical files already establish a substantial common base. The 103 differing files and 263 missing files are the inconsistencies we still need to account for. We should not label the CICS copy corrupted or modified until we have tested it against the Wiki's actual Git history.

## User

\========== DIRECTORY STRUCTURE ========== \
&#x20;\
\--- /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs --- \
drwxr-xr-x 4 deck deck 4096 Jun 17 20:39 **/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_do**\
**cs** \
No .git entry here \
&#x20;\
\--- /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official --- \
drwxr-xr-x 8 deck deck 4096 Jun 17 20:39 **/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_do**\
**cs/official** \
No .git entry here \
&#x20;\
\--- /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki --- \
drwxr-xr-x 12 deck deck 4096 Jun 17 22:46 **/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_d**\
**ocs/official/wiki** \
No .git entry here \
Contains sync-wiki.sh \
&#x20;\
\========== GIT REPOSITORY DISCOVERY ========== \
&#x20;\
\--- Checking /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs --- \
Not inside a Git working tree \
&#x20;\
\--- Checking /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official --- \
Not inside a Git working tree \
&#x20;\
\--- Checking /home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki --- \
Not inside a Git working tree \
&#x20;\
\========== SYNC AND SUBMODULE FILE LOCATIONS ========== \
/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2/corpora/coding/sources/azerothcore_docs/official/wiki/sync-wiki.sh \
(**deck@ExosSteamDeck engineering-rag-corpus**)$ \
&#x20;\
&#x20;

## Assistant

This rules out a direct Git-history check against the old-drive directory: **the copied `official/wiki` tree has no `.git` metadata, and there is no nested `wiki/` directory where the sync script expects one.** The script is therefore documentation of the intended synchronization workflow, not proof that this particular copy was synchronized successfully.

The directory may have been copied from a larger CICS checkout or exported after synchronization. We need to inspect the enclosing CICS repository before deciding which.There is a useful external cross-check: the public `azerothcore/wiki` repository has the same site-root structure shown in your CICS directory—Jekyll folders, `docs/`, `_config.yml`, and `sync-wiki.sh`. Its README identifies it as the AzerothCore Wiki site repository. <Cite refs={["turn763006search0"]}/>

That makes a **copy of the Wiki repository's site tree** more likely than a separately assembled documentation export. But because the old-drive copy lacks Git metadata, we still cannot assign it a commit or determine whether its `docs/` content was transformed after checkout.

## Next diagnostic: CICS parent and file timestamps

Please run this. It checks whether the enclosing CICS project has recoverable Git history and whether the Wiki files retain a coherent timestamp pattern.

```bash
CICS="/home/deck/Old-Drive-Import/Additional-Top-Level/Project_repositories/cics_v2"
WIKI="$CICS/corpora/coding/sources/azerothcore_docs/official/wiki"

echo "========== CICS ROOT =========="
ls -ld "$CICS"
if git -C "$CICS" rev-parse --show-toplevel 2>/dev/null; then
    git -C "$CICS" log -1 --format='HEAD %H%nDate %cI%nSubject %s'
    git -C "$CICS" remote -v
else
    echo "CICS root has no Git working-tree metadata"
fi

echo
echo "========== PARENT DIRECTORY CONTENTS =========="
find "$(dirname "$CICS")" -maxdepth 2 \
    \( -name .git -o -name .gitmodules -o -name '*.git' \) -print 2>/dev/null

echo
echo "========== WIKI FILE TIMESTAMP SAMPLE =========="
find "$WIKI/docs" -type f -printf '%TY-%Tm-%Td %TH:%TM:%TS %s %P\n' 2>/dev/null |
    sort | head -25

echo
echo "========== TIMESTAMP DISTRIBUTION =========="
find "$WIKI/docs" -type f -printf '%TY-%Tm\n' 2>/dev/null |
    sort | uniq -c | sort -k2

echo
echo "========== SITE ROOT FILE METADATA =========="
stat -c '%y | %s bytes | %n' \
    "$WIKI/_config.yml" "$WIKI/sync-wiki.sh" "$WIKI/README.md" \
    "$WIKI/docs/conditions.md" "$WIKI/docs/mysqltypescpp.md" 2>/dev/null
```

If the enclosing CICS repository also has no history, the strongest next step will be a clean, separate clone of `azerothcore/wiki` and a historical commit comparison. That lets us test whether the CICS files match an earlier upstream state without changing either existing tree.

The key target is to identify the upstream commit—or establish that no single commit matches. A match would explain the older content; a mismatch across otherwise matching files would help isolate later transformations or incomplete copying.
