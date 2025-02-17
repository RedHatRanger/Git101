***"In learning you will teach, and in teaching you will learn." – Phil Collins***
<br><br>

# Lab 7: Git Fetching and Git Pulling
![image](https://github.com/user-attachments/assets/8afb50ac-1e45-496b-9c15-8b4ab8de80d8) ![image](https://github.com/user-attachments/assets/c2727881-ffb1-4e9f-9391-2c02abf47e94) ![image](https://github.com/user-attachments/assets/f4e56dd4-efa2-4d3c-8d54-08f8937c574e)

# Main Lab
1. Let's play with `fetch`:
```
git checkout main
git fetch origin main
```

<br><br>
2. Let's view all the branches including remotes:
```
git branch -a
```

<br><br>
3. Now, we need to merge the remote changes with our local main branch:
```
git merge origin/main
```

<br><br>
4. Ultimately, the `git pull` combines the `git fetch` and `git merge` commands:
```
git pull origin main
```

5. `The Donkey and the Dog` story appears to have pulled down in the merge:
```
--------------------------------------------
      THE DONKEY AND THE LITTLE DOG
--------------------------------------------

A man had a little dog, and he was very fond of it. He would pat its head, and take it on his knee, and talk to it. Then he would give it little bits of food from his own plate.

A donkey looked in at the window and saw the man and the dog.

"Why does he not make a pet of me?" said the donkey.

"It is not fair. I work hard, and the dog only wags its tail, and barks, and jumps on its master's knee. It is not fair."

Then the donkey said to himself, "If I do what the dog does, he may make a pet of me."

So the donkey ran into the room. It brayed as loudly as it could. It wagged its tail so hard that it knocked over a jar on the table. Then it tried to jump on to its master's knee.

The master thought the donkey was mad, and he shouted, "Help! Help!" Men came running in with sticks, and they beat the donkey till it ran out of the house, and they drove it back to the field.

"I only did what the dog does," said the donkey," and yet they make a pet of the dog, and they beat me with sticks. It is not fair."
```


<br><br>
**Next:** [Lab 8: Stashing and Patching](08_stashing_and_patching.md)

