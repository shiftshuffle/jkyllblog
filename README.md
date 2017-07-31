# just to test this Jekyll phone app

git add .
git commit -m 'meta share'
git push origin master

git checkout gh-pages
git rebase master
git push origin gh-pages
git checkout master
