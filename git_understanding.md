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

# Branching and Team Collaboration

I have created a testing branch called testingbranch. I made changes to a file through that branch and checked the main branch and the changes wee not reflected there. 

Pushing changes directly to the main branch is problematic because the main is usually what gets shipped to production. Any changes made there without review or quality control is dangerous and could introduce bugs, security issues, etc. Branches help to isolate work by different people and for different features until they are ready to be merged. We can also use branches to open pull requests so reviewers can see the changes made or catch mistakes before merging. It is also easier to see which branch or pull request introduced a change to the main, making debugging easier. 

As learned previously, when two people edit the same file on different branches, the following can happen:
- If they edited completely different sections, then git can merge both changes automatically.
- if they edited the same line, then git will flag the conflict for manual review.
Branches force conflict resolution when work overlaps, because conflicts are explicit, they get resolved deliberately instead of one work overwriting another's work.

# Advanced Git Commands

git checkout --main <filename> restores the file from the main branch into the working directory.
- this command allows the developer to make changes to a file without affecting the rest of the main branch 

git cherry-pick <commit> applies the changes from a specific commit to the currrent branch.
- this command can allow a developer to see a bug fix on a different branch and use it in their release branch without merging unrelated features

git log shows a list of the commits
- this command can help understand the history of a feature or log. For example, we can see all the commits during a sprint to see what's going out.

git blame <filename> shows line-by-line authorship, commit hash, and date.
- this command can be very useful when debugging and looking at when it got added and by who. 

The images below shows my experimentation with the Git commands.

<img width="870" height="786" alt="Screenshot 2025-08-20 at 09 21 25" src="https://github.com/user-attachments/assets/4d611d97-0316-4907-8300-49eb87390a03" />
<img width="870" height="758" alt="Screenshot 2025-08-20 at 09 21 42" src="https://github.com/user-attachments/assets/4afcd069-91ad-4e27-944f-b5ec6ed99525" />

What surprised me the most is how powerful these short commands are. Just with short commands, developers working on a project are able to keep the work clean and organised. 

# Understanding git bisect

The command git bisect helps to narrow down to a commit that introduced a bug.
1. start bisection
2. you define good and bad commits
3. git will check a commit about halfway between the good and bad commit.
4. you determine if that commit is good or bad.
5. git will continue the process until the commit is that introduced a bug is found.

When there are many commits in a large project, it is not very feasible to manually track down the commit that caused a problem. Git bisect helps to streamline this process, saving time and actually minimises error in trying to find the problematic commit. 

The following screenshot is an example of using git bisect.

<img width="460" height="559" alt="Screenshot 2025-08-20 at 10 09 03" src="https://github.com/user-attachments/assets/2d6ff85a-eb0a-412a-900f-caf4bdcd1840" />

# Writing Meaningful Commit Messages

A good commit should reflect only one idea or decision. A good commit message should ideally tick the following boxes:

Subject Line:
- Capitalised at the beginning
- Limited to around 50 characters
- Written imperatively
- No period at the end

Body:
- Short and concise
- Include motivation for change
- Include other relevant context

In the end, when we look at the history of the commits, it should be clear just by looking at the messages what each commit aimed to achieve or change. 

A clear commit message help in team collaboration because it helps to make debugging easier and lets teammates search the history with intent. For example, a teammate can simply look up "fix" and all the commits with that keyword and change should come up. It is especially important for team projects to have some sort of consistent style.

A poor commit message can cause issues later when an issue occurs and we are trying to track down the root issue. For example, when we are trying to use git bisect but the messages are unclear, it is risky to narrow down further and will take a long time to determine if particular commits are good or bad. Poor commit messages overall will slow down incident response.

Below shows a list of commits made on React on Aug 16, 2025. 

<img width="785" height="811" alt="Screenshot 2025-08-20 at 10 37 29 am" src="https://github.com/user-attachments/assets/26977005-f3bc-4b16-b368-568a1e115824" />

- There is a commit with a WIP. This should occur since ideally commits are only completed work.
- Some messages are unnecessarily long: [DevTools] Compute a min and max range for the currently selected suspense boundary, can be shortened to: [DevTools] Compute min/max range for selected suspense boundary

Below shows three examples of commit messages: a vague message, an overly detailed message, and a well-structured message. 

<img width="542" height="351" alt="Screenshot 2025-08-20 at 10 50 14" src="https://github.com/user-attachments/assets/68ecf627-e2ac-441b-9396-ab561f1643d2" />

# Pull Requests

Pull requests allow teams to work collaboratively and effectively. It acts as a checkpoint before changes reach the main branch, enabling code reviews, tests, and discussions. This prevents bugs and also enforces consistency in the codebase.

A well structured PR should include the following:
- clear and concise title describing the change
- description explain what changed and why
- small, focused commits
- passing tests and documentation updates

I've previously created a pull request before and has been marked. 

I also reviewed this pull request on React: https://github.com/facebook/react/pull/34212

