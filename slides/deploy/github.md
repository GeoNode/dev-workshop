# Push to GitHub

It is always a good practice to keep your code in a remote repository, GithHub is one of the options and is indeed the most used.

It is assumed that you already have a GitHub account and that you have git installed and configured with your name and email.

We will push only the `my_geonode`folder to GitHub, GeoNode for us is a dependency and we'll just reinstall it as it is on the server.

Steps to push your code to GitHub:

* Create an empty repository in GitHub and copy it's address
* in `my_geonode`run `git init`to initialize an empty repository
* add you remote repository address with `git remote add yourname yourremoteaddress`
* edit `.gitignore` adding all *.pyc files
* `git add *` to add all content of `my_geonode`
* `git commit -m 'initial import'` to make the initial commit
* `git push yourname master` to push the code to the GitHub repository
