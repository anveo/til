# git

Delete remote branches which have been merged

    git branch --remotes --merged | grep -v master | grep -v dev | sed 's/origin\///' | xargs -n 1 git push --delete origin

Delete local branches which have been merged

    git branch --merged | grep -v "\*" | grep -v master | grep -v dev | xargs -n 1 git branch -d
