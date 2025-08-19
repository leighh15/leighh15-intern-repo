# Merge conflicts and conflict resolution

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

# Staging vs Committing 

Staging and committing represent distinct steps in recording changes to a project.

Staging takes places before committing. I may have modified 20 files but only stage half. The half that I have staged are ready to be committed. Committing is the act of permanently recording the changes in the repository. 

Git separates these two steps because it gives the user control and flexibility over how changes are made and recorded. Without staging, every changed file will be included in the next commit. It also provides a checkpoint of sorts so the files are reviewed one more time. Ideally, commits should be logical and representing one idea (feature, bug fix, etc) so the rest of the team can understand the purpose of each commit.

Nonetheless, it is still possible to skip staging for any of the following, non-exhaustive reasons:
- small typo fixes
- solo projects
- quick fixes

This is what it looks like when I stage the file but not yet commit.
<img width="545" height="90" alt="Screenshot 2025-08-19 at 16 57 57" src="https://github.com/user-attachments/assets/bd669d7c-bff0-4213-8173-38a91c6f45d1" />

