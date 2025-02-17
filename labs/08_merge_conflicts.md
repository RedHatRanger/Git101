***"Success is not final, failure is not fatal: it is the courage to continue that counts." – Winston Churchill***
<br><br>

# Lab 8: Merge Conflicts
![image](https://github.com/user-attachments/assets/a3567edb-a5e0-463e-87b2-004d63f36cb5) ![image](https://github.com/user-attachments/assets/5dabbc9b-c649-4d1f-bc39-ba0006894d6b) ![image](https://github.com/user-attachments/assets/b5e8d250-02c1-4e8d-a9ee-e903cd1a775f) ![image](https://github.com/user-attachments/assets/1890c30f-8c7d-4df1-bea5-270480e81087) ![image](https://github.com/user-attachments/assets/ed28c5f3-b80c-4982-9912-1fb79f494fb7) ![image](https://github.com/user-attachments/assets/61d4b61a-5fdb-483d-b4de-aad91ada02c9)

<br><br>
># The Setup:
>Max creates a file called `story-index.txt`
>```
>cd ~/story-blog
>cat << EOF > story-index.txt 
>1. The Lion and the Mooose
>2. The Frogs and the Ox
>3. The Fox and the Grapes
>4. The Donkey and the Dog
>EOF
>```

<br><br>
# Main Lab
1. Max stages `story-index.txt` and commits the file successfully:
```
git add story-index.txt 
git commit -m "Add index of stories"
```

<br><br>
2. However, Max gets rejected when he pushes the changes to the remote repository:
```
git push -u origin master
```
![image](https://github.com/user-attachments/assets/ced11466-d36d-4fee-b018-6761d2f24b8b)

>This error states that there is work on the remote repository that doesn't exist locally yet.

<br><br>
3. So we have to do a `git pull origin master` or `git pull` but the conflict is there:
![image](https://github.com/user-attachments/assets/2e7b38ac-ffab-459c-98b0-a5147e7ad320)

![image](https://github.com/user-attachments/assets/017e138a-9b77-4c54-ba07-0e5063c969f0)

```
git log origin/master

# Sarah had the last commit
```
![image](https://github.com/user-attachments/assets/d7de0dc3-d009-44c5-9372-96042215d785)
![image](https://github.com/user-attachments/assets/f4f1ed9f-8aaf-4bee-825b-18a7b60fc43b)

```
cat story-index.txt
```
![image](https://github.com/user-attachments/assets/38fef64a-6336-4e82-830e-73cb2fc3f9d4)
![image](https://github.com/user-attachments/assets/2cbdd58f-990f-43d3-8317-9af667845670)
![image](https://github.com/user-attachments/assets/b6bb338b-9b0a-450b-a5d8-816b7272686c)

<br><br>
4. Modify the `story-index.txt` file:
```
cat << EOF > story-index.txt
1. The Lion and the Mouse
2. The Frogs and the Ox
3. The Fox and the Grapes
4. The Donkey and the Dog
EOF
```



**Next:** [Lab 9: Git Log, Diff, and History](09_git_log_diff_and_history.md)


