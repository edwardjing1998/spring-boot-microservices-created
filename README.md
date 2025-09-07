git switch -c case-service-j --track origin/case-service-j
git switch -c feature/service --track origin/feature/service


git switch case-service-j
git pull --ff-only

git switch feature/service
git pull --ff-only



git switch case-service-j
git merge --no-ff feature/service


git status               # see conflicted files
# edit files to resolve conflicts
git add <files-you-fixed>
git commit               # completes the merge


git push origin case-service-j
