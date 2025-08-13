Merge conflicts arise when changes have been made to the same section in the same file but in two different branches: the main and a secondary branch.

<img width="912" height="195" alt="Screenshot 2025-08-13 at 21 34 00" src="https://github.com/user-attachments/assets/3106c5f2-ea3e-48c7-8bfd-e1a0bd224ddc" />
<img width="391" height="101" alt="Screenshot 2025-08-13 at 21 34 19" src="https://github.com/user-attachments/assets/72d06ea9-09f6-4d2d-901e-4a9959c25d0f" />
<img width="391" height="101" alt="Screenshot 2025-08-13 at 21 35 13" src="https://github.com/user-attachments/assets/166cf0d1-cc79-4954-ad84-1c00acfd4fa2" />

Reflection:

What I did:
- I created another branch, made changes to the file in the secondary branch, then made changes to the same line in the same file but in the main branch.
- I merged, then created a pull request where I reviewed the conflict.
- I decided which one to keep, or entirely change the line which will reflect on both branches.
- I mark the file as resolved and commit the merge, and merged my pull request.

The changes I made to the same file but in different branches caused the conflict because Git does not know which one to keep. I resolved it by creating a pull request which prompted me to review the conflict in the file and made changes that will reflect on both branches. I learned that Git cannot automatically combine changes especially the same lines. They aren't errors but a prompt that requires human decision-making, Git cannot decide which change to keep. If there a many people making changes to files and across different branches, it is important that the team can communicate effectively to minimise conflict frequency.
