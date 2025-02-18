***"One big reason for a winning attitude is that you will take the necessary steps and not quit when the going gets difficult." – Don M.Green***
<br><br>

# Lab 12: Git Reset and Git Revert
![image](https://github.com/user-attachments/assets/50af2764-d831-4198-ab23-2b646ccb7118) 

![image](https://github.com/user-attachments/assets/1f07ffc7-5613-4eb5-b086-46b66e033f26) 
>This will delete the story but create a new commit.

![image](https://github.com/user-attachments/assets/dc9524da-362f-4449-8f47-dc7b97d07af4)
>The soft reset will let you keep all the changes you made.

![image](https://github.com/user-attachments/assets/44da4c30-7418-4523-b3d7-d3bd434f45dc)
>We can still see the changes that were made with git status with a soft reset.

![image](https://github.com/user-attachments/assets/ad752b2d-3965-4a5b-84e3-cae50a630554)
>But if we reset with the hard reset, the commit will be reset without saving all those changes.

![image](https://github.com/user-attachments/assets/71414a14-c1fb-4d07-ba24-d7d16e00b3cb)
>The 3rd story file is now completely gone.

<br><br>
# Main Lab

<br><br>
1. Let's find out how many stories sarah altered in that last commit (Quiz Question #1):
![image](https://github.com/user-attachments/assets/fe458c71-11cc-43d4-b007-d342d65b8233)
```
git log --name-only
```
![image](https://github.com/user-attachments/assets/bd78f2e0-403b-400b-901e-0e092e79f84d)
>Sarah altered 5 stories

<br><br>
2. Help Sarah undo all the changes made in that last commit:
![image](https://github.com/user-attachments/assets/766f7633-302a-4154-b074-98a098fd48ac)
```
git revert HEAD~0

# OR
# git revert <commit_id>
```
![image](https://github.com/user-attachments/assets/6a930706-8e72-4a73-ad65-0a0f9a99c433)

<br><br>
3. Quiz Question #2:
![image](https://github.com/user-attachments/assets/b9284fd7-bc78-47e2-b334-74e90a24c347)
>Answer: --soft

<br><br>
4. Quiz Question #3:
![image](https://github.com/user-attachments/assets/ae45a6e4-e1ad-4d90-a6d1-2391d8ae7c70)
>Answer: --hard

<br><br>
5. Help Sarah revert the last commit but retain the unfinished changes so she can finish her story:
![image](https://github.com/user-attachments/assets/10869d0a-a456-4945-af35-f6bc9c539581)
```
git reset --soft HEAD~1
git add hare-and-tortoise.txt
git commit -m "Finished hare-and-tortoise story"
```

<br><br>
6. Quiz Question #4:
![image](https://github.com/user-attachments/assets/7192bb72-8de9-46c2-a77c-40378fba00cf)

![image](https://github.com/user-attachments/assets/e598660a-ea21-414b-80d8-f98c078f80eb)
>Answer: There have been 3 commits since Sarah finshed her story.

<br><br>
7. Help Sarah reset her story to the previous good version of the story (since 'Finished hare-and-tortoise story'):
![image](https://github.com/user-attachments/assets/1190c05d-7f97-46b9-ae80-693f326a0d56)
```
git reset --hard HEAD~3
```
![image](https://github.com/user-attachments/assets/63947dd5-0f52-4926-ba72-dc91c6db63c6)

* Done
