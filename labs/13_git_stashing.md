***"Neither comprehension nor learning can take place in an atmosphere of anxiety." – Rose Kennedy***
<br><br>

# Lab 13: Git Stashing
![image](https://github.com/user-attachments/assets/d5b25b33-fe77-4c07-bb3a-b0220abe0d27) 

![image](https://github.com/user-attachments/assets/4f1ecb72-00b1-4104-8dcd-38bf389dc37c)
>Temporarily move some stuff from staging area to stash area.

![image](https://github.com/user-attachments/assets/cd912a14-ef90-4c87-9116-ee01297923ab)
>To get the changes back into the working area.

![image](https://github.com/user-attachments/assets/4107c74f-319e-4a1e-8973-c222c9d92f08)
>You can see that git stash is like storing library books.

![image](https://github.com/user-attachments/assets/0fc05788-a73b-460f-9794-f4b38afde4d1)
>To view everything that's in Stash.

![image](https://github.com/user-attachments/assets/b9dadebc-6b56-4001-90d5-9990d89d2cb2)
>To pop a specific Stash.

# Main Lab

<br><br>
1. Help Sarah stash her current changes before heading over to the master branch to fix the typo:
![image](https://github.com/user-attachments/assets/e7b06dee-d362-4ca2-a770-0d128209e137)
![image](https://github.com/user-attachments/assets/5be845bf-8eda-4fab-a49c-476ec7173e45)

```
git stash
git stash list
```
<br><br>
2. Now Sarah can checkout the master branch to fix the typo in `lion-and-mouse.txt`:
![image](https://github.com/user-attachments/assets/f61d7749-2218-436e-a3ca-642e177b6ba8)
```
cd story-blog
git checkout main
vim lion-and-mouse.txt
git add lion-and-mouse.txt
git commit -m "Fixed title error"
```

<br><br>
3. Now let's move the stashed commit back to the staging area:
![image](https://github.com/user-attachments/assets/ffe3960b-3287-4d22-94a4-4a971aa645c7)
```
git checkout story/frogs-and-ox
git stash list
git stash pop stash@{0}
```

<br><br>
4. Find the list of stories that were stashed:
![image](https://github.com/user-attachments/assets/8eec01eb-217b-4f80-a9b7-d2aa9c9ca26f)

![image](https://github.com/user-attachments/assets/db51f4bc-4140-47b9-bc31-fcf3a0500049)
>There are 3 stashed stories!

<br><br>
5. Figure out what files were stashed:
![image](https://github.com/user-attachments/assets/203e6e4d-fb5c-4642-ba40-17b90a8cfab7)
```
git stash show stash@{0} ; git stash show stash@{1}; git stash show stash@{2}
```
>Answer: story3.txt, story2.txt, and story1.txt

* Done!
