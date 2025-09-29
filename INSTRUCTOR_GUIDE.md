# Git Collaboration Workshop - Instructor Guide

## 🎯 Workshop Overview

**Duration:** 2-3 hours
**Participants:** Pairs (2 people per team)
**Skill Level:** Beginner to intermediate
**Tools Needed:** Git, GitHub accounts, text editors

## 📋 Pre-Workshop Preparation

### Before the Session

1. **Send participants preparation email** (1 week before):
   - Link to create GitHub account
   - Git installation instructions
   - Workshop agenda and objectives

2. **Room Setup:**
   - Ensure WiFi connectivity
   - Have backup internet connection
   - Projector for demonstrations
   - Whiteboard for drawing Git concepts

3. **Materials:**
   - Printed command reference sheets
   - Workshop completion certificates (optional)
   - Stickers or small prizes for completion

## ⏰ Detailed Timeline

### Opening (15 minutes)
- Welcome and introductions
- Pair formation (if not pre-arranged)
- Quick Git concept overview
- Workshop goals and expectations

### Exercise 1: Basic Collaboration (20 minutes)
- **Learning Goal:** Understanding the basic Git workflow
- **Key Concepts:** clone, add, commit, push, pull
- **Watch For:** 
  - Participants forgetting to pull before working
  - Confusion about local vs remote repositories
  - GitHub authentication issues

### Exercise 2: First Merge Conflict (25 minutes)
- **Learning Goal:** Demystifying merge conflicts
- **Key Concepts:** Conflict markers, manual resolution
- **Watch For:**
  - Panic when conflicts appear
  - Editing conflict markers instead of resolving content
  - Forgetting to commit after resolution

### Break (10 minutes)

### Exercise 3: Multiple File Conflicts (30 minutes)
- **Learning Goal:** Complex conflict resolution
- **Key Concepts:** Multiple file conflicts, systematic resolution
- **Watch For:**
  - Overwhelming feeling from multiple conflicts
  - Resolving files one by one instead of all at once
  - Inconsistent naming/formatting in resolutions

### Exercise 4: Conflict Prevention (15 minutes)
- **Learning Goal:** Best practices for collaboration
- **Key Concepts:** Communication, coordination, file organization
- **Watch For:**
  - Participants working on same files without coordination
  - Understanding the value of communication

### Exercise 5: Branching (25 minutes)
- **Learning Goal:** Using branches for organized development
- **Key Concepts:** branch, checkout, merge
- **Watch For:**
  - Confusion about which branch they're on
  - Forgetting to switch branches
  - Merge conflicts when combining branches

### Exercise 6: Real-World Scenario (30 minutes)
- **Learning Goal:** Applying all concepts in realistic setting
- **Key Concepts:** Complete workflow simulation
- **Watch For:**
  - Integration of all previous concepts
  - Confidence in handling conflicts

### Wrap-up (10 minutes)
- Key takeaways discussion
- Q&A session
- Resources for continued learning
- Workshop completion recognition

## 🎓 Teaching Tips

### General Approach
- **Hands-on first:** Let them experience problems before explaining
- **Normalize mistakes:** Emphasize that conflicts are normal
- **Encourage collaboration:** Pairs should help each other
- **Live demonstration:** Show concepts on projector when needed

### Common Student Challenges

1. **"I broke everything!"**
   - Reassure them Git is forgiving
   - Show `git status` for guidance
   - Demonstrate `git log` to see history

2. **Authentication Issues**
   - Have backup: personal access tokens
   - Consider SSH key setup beforehand
   - GitHub CLI as alternative

3. **Merge Conflict Panic**
   - Explain conflict markers slowly
   - Show before/after examples
   - Practice on simple, obvious conflicts first

4. **Command Line Fear**
   - Provide clear, copy-paste commands
   - Explain what each command does
   - Show GUI alternatives (but emphasize CLI benefits)

### Helpful Demonstrations

**Visualizing Git Flow:**
```
[Local] --push--> [GitHub] <--pull-- [Partner's Local]
```

**Conflict Marker Explanation:**
```
<<<<<<< HEAD (Your changes)
Your version of the code
=======
Their version of the code
>>>>>>> [commit-hash] (Their changes)
```

## 🆘 Troubleshooting Guide

### Common Issues and Solutions

1. **"Permission denied" when pushing**
   - Check repository collaborator settings
   - Verify GitHub authentication
   - Try HTTPS instead of SSH

2. **"Repository not found"**
   - Check repository URL
   - Ensure repository is public or user has access
   - Verify spelling of repository name

3. **"Your branch is behind"**
   - Show `git pull` first
   - Explain remote vs local repository state

4. **Stuck in merge conflict**
   - `git status` shows what's happening
   - `git merge --abort` to cancel merge
   - Walk through conflict resolution step-by-step

5. **Lost changes**
   - `git log` shows commit history
   - `git reflog` shows all actions
   - Nothing is truly lost in Git

### Emergency Commands
```bash
git status                    # See current state
git log --oneline            # See recent commits
git merge --abort            # Cancel a merge
git reset --hard HEAD        # Reset to last commit (DANGER!)
git stash                    # Temporarily save changes
```

## 📚 Learning Objectives Assessment

### Beginner Level (Must achieve)
- [ ] Can clone a repository
- [ ] Understands add, commit, push, pull workflow
- [ ] Can recognize a merge conflict
- [ ] Can resolve a simple merge conflict
- [ ] Knows when to communicate with team members

### Intermediate Level (Should achieve)
- [ ] Comfortable with multiple file conflicts
- [ ] Can use branches effectively
- [ ] Understands when conflicts occur and why
- [ ] Can help others with basic Git issues
- [ ] Knows best practices for collaboration

### Advanced Level (Bonus)
- [ ] Can explain Git concepts to others
- [ ] Comfortable with command line Git
- [ ] Understands Git history and workflows
- [ ] Can troubleshoot complex issues
- [ ] Ready to learn advanced Git features

## 🔄 Adaptations for Different Groups

### For Complete Beginners
- Start with GUI Git tools for visualization
- Spend extra time on basic concepts
- Use more simple, obvious examples
- Provide more individual assistance

### For Developers with Some Experience
- Move faster through basic exercises
- Focus more on branching strategies
- Discuss real-world workflows
- Cover advanced conflict resolution

### Remote Workshop Adaptations
- Use breakout rooms for pairs
- Screen sharing for demonstrations
- Slack/Discord for communication
- Pre-recorded demos for technical issues

## 📋 Materials Checklist

### Digital Materials
- [ ] Repository templates ready
- [ ] Demo repository prepared
- [ ] Screen recording software tested
- [ ] Backup slides prepared
- [ ] Command reference accessible

### Physical Materials (In-Person)
- [ ] Printed command references
- [ ] Workshop certificates/completion items
- [ ] Backup USB drives with Git installers
- [ ] Extension cords and adapters
- [ ] Whiteboard markers

### Backup Plans
- [ ] Offline Git exercises prepared
- [ ] GitHub alternatives identified (GitLab, etc.)
- [ ] Mobile hotspot available
- [ ] Pre-downloaded materials

## 🎯 Success Metrics

### Immediate (End of Workshop)
- All pairs complete at least Exercise 1-3
- Participants can resolve basic merge conflicts independently
- Positive feedback on workshop experience
- Participants express confidence to use Git in projects

### Long-term (Follow-up Survey)
- Participants actively using Git in work/projects
- Reduced fear of merge conflicts
- Improved collaboration practices
- Participants teaching Git to others

## 📞 Instructor Support Resources

### Quick Help Links
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Help](https://help.github.com)
- [Interactive Git Tutorial](https://learngitbranching.js.org)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)

### Advanced Topics for Q&A
- Rebasing vs merging
- Git hooks and automation
- Large file handling (Git LFS)
- Continuous integration with Git
- Advanced branching strategies (GitFlow, etc.)

---

**Remember:** The goal is not to create Git experts in one session, but to remove fear and build confidence with collaborative development!