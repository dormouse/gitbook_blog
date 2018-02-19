---
title: "My First Post"
date: 2018-02-10T12:28:58+08:00
draft: Fasle
---


Try to separate blog from documents since now.
Choose Hugo for my blog.

# Install Hugo

```
# install hugo on Debian or Ubuntu
sudo apt-get install hugo
# install hugo OSX
brew install hugo
# update hugo
brew upgrade hugo
```

# Start a new blog:

```
cd project
hugo new site blog2018
cd blog2018
git init
git submodule add https://github.com/budparr/gohugo-theme-ananke.git themes/ananke
echo 'theme = "ananke"' >> config.toml
hugo new posts/my-first-post.md
hugo server -D
```
Then goto http://localhost:1313/ ,
a new blog is there.

Site configuration, edit ``config.toml`` as:
```
baseURL = "https://dormouse.github.io"
languageCode = "en-us"
title = "Dormouse's Blog"
theme = "ananke"
```

# Publish on github

First Create a git on github, then:

```
git add .
git commit -m "first commit"
git remote add orgin git@github.com:dormouse/blog2018.git
git push -u orgin master
```

Create a deploy.sh file:
```
#!/bin/bash

echo -e "\033[0;32mDeploying updates to GitHub...\033[0m"

# Build the project.
hugo # if using a theme, replace with `hugo -t <YOURTHEME>`

# Go To Public folder
cd public
# Add changes to git.
git add .

# Commit changes.
msg="rebuilding site `date`"
if [ $# -eq 1 ]
  then msg="$1"
fi
git commit -m "$msg"

# Push source and build repos.
git push origin master

# Come Back up to the Project Root
cd ..

```

Set the ouput public path as sub module:

```
rm -rf public/
git submodule add -b master git@github.com:dormouse/dormouse.github.io.git public
./deploy.sh
```
Or you can run ``./deploy.sh "Your optional commit message"``.

# How to Clone this blog

```
git clone git@github.com:dormouse/blog2018.git
cd blog2018/
git submodule update --init --recursive
cd public
git checkout master
```

# Cheet sheet

* Add new post:``hugo new posts/some-post.md``
* Preview post:``hugo server -D``
* Update blog2018.git
* Deploy:``./deploy.sh``.

# REF

* https://gohugo.io/getting-started/quick-start/
* https://github.com/budparr/gohugo-theme-ananke
* https://gohugo.io/hosting-and-deployment/hosting-on-github/#set-gh-pages-as-your-publish-branch