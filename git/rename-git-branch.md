HTML comments inside of JSX won't work, you need to use JavaScript block comments and wrap them in curly brases:

1. Rename a local branch
   
   if you are on the branch you want to rename:
    ```Git
    git branch -m new-name
    ```
   if you are on a different branch:
    ```Git
    git branch -m old-name new-name
    ```

2. Delete the old-name remote branch and push the new-name local branch
    ```Git
    git push origin :old-name new-name
    ```

3. Reset the upstream branch with the new-name local branch
    ```Git
    git push origin -u -m new-name
    ```

source: [Rename a local and remote branch in git](https://multiplestates.wordpress.com/2015/02/05/rename-a-local-and-remote-branch-in-git/)