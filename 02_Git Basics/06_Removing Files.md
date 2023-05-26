# Removing Files

There are 2 ways to delete a file

## Using Linux command

Use `rm test.txt` to delete the file normally from the project

Add the changes to the **Staging Area** `git add test.txt` and then we commit `git commit -m "Delete unnecessary file"`.

If we have test.txt file marked **modified** and waiting in the stage area and then we perform deletion then another file will be showed in marked as **deleted** when added to the **Staging Area**.

If we run `git ls-files`we will see a list of files in the **Staging Area**, and even after deleting `text.txt` from the **Working Directory** it still exist in the **Staging Area**.

## Using Git command

To remove a file we have to remove it both form the **Working Directory** and the **Staging Area**.

We can perform this operation with a single command `git rm test.txt`
