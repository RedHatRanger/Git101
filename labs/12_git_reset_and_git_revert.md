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

1. Let's find out who authored what on the branch:
![image](https://github.com/user-attachments/assets/fe458c71-11cc-43d4-b007-d342d65b8233)
```
git log --name-only
```
![image](https://github.com/user-attachments/assets/bd78f2e0-403b-400b-901e-0e092e79f84d)
>Sarah modified 5 stories

