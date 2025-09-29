# Git Collaboration Workshop - Pair Exercises

Welcome to the Git Collaboration Workshop! This workshop is designed for pairs of participants to learn Git collaboration through hands-on exercises. No prior Git experience required - we'll guide you step by step.

## 🎯 What You'll Learn

- Basic Git commands and workflow
- How to collaborate using Git and GitHub
- How to handle merge conflicts
- Best practices for team collaboration

## 📋 Prerequisites

- Git installed on your computer
- A GitHub account
- A text editor (VS Code, Notepad++, or any editor you prefer)
- Basic command line knowledge (we'll guide you through the commands)

## 👥 Workshop Structure

Work in pairs throughout these exercises. You'll take turns being:
- **Person A**: The repository owner
- **Person B**: The collaborator

## 🚀 Getting Started

### Step 1: Initial Setup (Person A)

1. **Create a new repository on GitHub:**
   - Go to GitHub.com and sign in
   - Click the "+" button in the top right corner
   - Select "New repository"
   - Name it `git-workshop-[your-names]` (e.g., `git-workshop-alice-bob`)
   - Make it **public**
   - Check "Add a README file"
   - Click "Create repository"

2. **Clone the repository to your computer:**
   ```bash
   git clone https://github.com/YOUR_USERNAME/git-workshop-[your-names].git
   cd git-workshop-[your-names]
   ```

3. **Add Person B as a collaborator:**
   - Go to your repository on GitHub
   - Click "Settings" tab
   - Click "Manage access" in the left sidebar
   - Click "Invite a collaborator"
   - Enter Person B's GitHub username
   - Send the invitation

### Step 2: Person B Setup

1. **Accept the collaboration invitation:**
   - Check your email or GitHub notifications
   - Accept the invitation

2. **Clone the repository:**
   ```bash
   git clone https://github.com/PERSON_A_USERNAME/git-workshop-[your-names].git
   cd git-workshop-[your-names]
   ```

## 📚 Exercise 1: Basic Collaboration (No Conflicts)

### Goal: Learn the basic Git workflow without conflicts

**Person A starts:**

1. **Create a new file:**
   ```bash
   echo "# Our Collaborative Project" > project-info.txt
   echo "Created by: [Your Name]" >> project-info.txt
   ```

2. **Add and commit:**
   ```bash
   git add project-info.txt
   git commit -m "Add initial project info"
   ```

3. **Push to GitHub:**
   ```bash
   git push origin main
   ```

**Person B's turn:**

1. **Pull the latest changes:**
   ```bash
   git pull origin main
   ```

2. **Add your information:**
   ```bash
   echo "Collaborator: [Your Name]" >> project-info.txt
   ```

3. **Commit and push:**
   ```bash
   git add project-info.txt
   git commit -m "Add collaborator info"
   git push origin main
   ```

**Person A:**

1. **Pull the updates:**
   ```bash
   git pull origin main
   ```

2. **Verify the file contains both names**

✅ **Success!** You've completed your first collaboration!

---

## ⚔️ Exercise 2: Your First Merge Conflict

### Goal: Create and resolve a merge conflict

This exercise will intentionally create a conflict so you can learn how to resolve it.

**Both persons do this simultaneously (don't communicate!):**

1. **Make sure you both have the latest version:**
   ```bash
   git pull origin main
   ```

2. **Both edit the same line in `project-info.txt`:**
   
   **Person A** - Change the first line to:
   ```
   # Amazing Collaborative Project - Updated by Person A
   ```
   
   **Person B** - Change the first line to:
   ```
   # Fantastic Collaborative Project - Updated by Person B
   ```

3. **Both add and commit (but don't push yet!):**
   ```bash
   git add project-info.txt
   git commit -m "Update project title"
   ```

4. **Person A pushes first:**
   ```bash
   git push origin main
   ```

5. **Person B tries to push:**
   ```bash
   git push origin main
   ```
   
   ❌ **You should get an error!** This is expected.

### Resolving the Conflict

**Person B (who got the error):**

1. **Pull the latest changes:**
   ```bash
   git pull origin main
   ```
   
   You'll see a conflict message. Don't panic! 🚨

2. **Open `project-info.txt` in your text editor.**
   
   You'll see something like:
   ```
   <<<<<<< HEAD
   # Fantastic Collaborative Project - Updated by Person B
   =======
   # Amazing Collaborative Project - Updated by Person A
   >>>>>>> [commit-hash]
   ```

3. **Resolve the conflict by editing the file:**
   
   Remove the conflict markers and decide on the final version:
   ```
   # Epic Collaborative Project - Updated by Both A and B
   ```

4. **Save the file, then add and commit:**
   ```bash
   git add project-info.txt
   git commit -m "Resolve merge conflict in project title"
   ```

5. **Push the resolved conflict:**
   ```bash
   git push origin main
   ```

**Person A:**

1. **Pull to see the resolution:**
   ```bash
   git pull origin main
   ```

🎉 **Congratulations!** You've resolved your first merge conflict!

---

## 🌟 Exercise 3: Multiple File Conflicts

### Goal: Practice with more complex conflicts

**Setup (Both persons):**

1. **Pull latest changes:**
   ```bash
   git pull origin main
   ```

2. **Person A creates a team members file:**
   ```bash
   echo "# Team Members" > team.txt
   echo "Leader: Person A" >> team.txt
   echo "Skills: Git basics" >> team.txt
   git add team.txt
   git commit -m "Add team file"
   git push origin main
   ```

3. **Person B pulls and creates a goals file:**
   ```bash
   git pull origin main
   echo "# Project Goals" > goals.txt
   echo "1. Learn Git collaboration" >> goals.txt
   echo "2. Practice conflict resolution" >> goals.txt
   git add goals.txt
   git commit -m "Add project goals"
   git push origin main
   ```

4. **Person A pulls the goals:**
   ```bash
   git pull origin main
   ```

### Creating Multiple Conflicts

**Both persons do this simultaneously:**

**Person A:**
1. Edit `team.txt`:
   ```
   # Team Members
   Leader: Person A (Git Expert)
   Developer: Person B
   Skills: Advanced Git workflows
   ```

2. Edit `goals.txt`:
   ```
   # Project Goals
   1. Master Git collaboration
   2. Practice conflict resolution
   3. Learn branching strategies
   ```

3. Commit:
   ```bash
   git add .
   git commit -m "Update team and goals - Person A version"
   ```

**Person B:**
1. Edit `team.txt`:
   ```
   # Team Members
   Co-Leader: Person A
   Co-Leader: Person B (Conflict Resolver)
   Skills: Git collaboration and teamwork
   ```

2. Edit `goals.txt`:
   ```
   # Project Goals
   1. Learn Git collaboration thoroughly
   2. Practice conflict resolution like pros
   3. Understand merge strategies
   ```

3. Commit:
   ```bash
   git add .
   git commit -m "Update team and goals - Person B version"
   ```

### Push and Resolve

1. **Person A pushes first:**
   ```bash
   git push origin main
   ```

2. **Person B tries to push and gets conflict:**
   ```bash
   git push origin main  # This will fail
   git pull origin main  # This will show conflicts
   ```

3. **Person B resolves both files:**
   
   For `team.txt`, create a combined version:
   ```
   # Team Members
   Co-Leader: Person A (Git Expert)
   Co-Leader: Person B (Conflict Resolver)
   Skills: Advanced Git workflows and teamwork
   ```
   
   For `goals.txt`, create a combined version:
   ```
   # Project Goals
   1. Master Git collaboration thoroughly
   2. Practice conflict resolution like pros
   3. Learn branching and merge strategies
   ```

4. **Commit the resolution:**
   ```bash
   git add .
   git commit -m "Resolve multiple file conflicts"
   git push origin main
   ```

---

## 🎯 Exercise 4: Prevention is Better Than Cure

### Goal: Learn to avoid conflicts

**Best Practice: Communicate and coordinate**

**Person A:**
1. **Announce your plans:**
   - "I'm going to work on the README file"
   
2. **Create a feature:**
   ```bash
   echo "# Installation Guide" > installation.md
   echo "1. Install Git" >> installation.md
   echo "2. Clone repository" >> installation.md
   git add installation.md
   git commit -m "Add installation guide"
   git push origin main
   ```

**Person B:**
1. **Announce your plans:**
   - "I'll work on a different file - troubleshooting guide"
   
2. **Pull first, then create:**
   ```bash
   git pull origin main
   echo "# Troubleshooting" > troubleshooting.md
   echo "## Common Issues" >> troubleshooting.md
   echo "- Merge conflicts: Don't panic!" >> troubleshooting.md
   git add troubleshooting.md
   git commit -m "Add troubleshooting guide"
   git push origin main
   ```

3. **Person A pulls the updates:**
   ```bash
   git pull origin main
   ```

🎉 **No conflicts!** Communication prevents problems.

---

## 🔧 Exercise 5: Using Branches (Advanced)

### Goal: Learn to use branches to avoid conflicts

**Person A creates a branch:**
1. ```bash
   git checkout -b feature-documentation
   echo "# Documentation" > docs.md
   echo "This project teaches Git collaboration" >> docs.md
   git add docs.md
   git commit -m "Add documentation"
   git push origin feature-documentation
   ```

**Person B creates a different branch:**
1. ```bash
   git checkout -b feature-examples
   mkdir examples
   echo "git clone [url]" > examples/basic-commands.txt
   git add examples/
   git commit -m "Add example commands"
   git push origin feature-examples
   ```

**Merging branches (Person A):**
1. ```bash
   git checkout main
   git pull origin main
   git merge feature-documentation
   git push origin main
   ```

**Person B merges their branch:**
1. ```bash
   git checkout main
   git pull origin main  # Gets Person A's changes
   git merge feature-examples
   git push origin main
   ```

---

## 📝 Exercise 6: Real-World Scenario

### Goal: Simulate a real development workflow

**The Scenario:** You're both working on a simple website for your workshop.

**Person A - Setup the project:**
1. ```bash
   echo "<!DOCTYPE html>" > index.html
   echo "<html><head><title>Git Workshop</title></head>" >> index.html
   echo "<body><h1>Welcome to Git Workshop</h1></body></html>" >> index.html
   git add index.html
   git commit -m "Create basic HTML structure"
   git push origin main
   ```

**Person B - Add styling:**
1. ```bash
   git pull origin main
   echo "body { font-family: Arial; background-color: #f0f0f0; }" > style.css
   echo "h1 { color: #333; text-align: center; }" >> style.css
   git add style.css
   git commit -m "Add CSS styling"
   git push origin main
   ```

**Both persons - Add content simultaneously:**

**Person A** adds to `index.html`:
```html
<!DOCTYPE html>
<html><head><title>Git Workshop</title></head>
<body>
  <h1>Welcome to Git Workshop</h1>
  <p>Learn Git collaboration with hands-on exercises!</p>
  <h2>What You'll Learn:</h2>
  <ul>
    <li>Basic Git commands</li>
    <li>Collaboration workflows</li>
  </ul>
</body></html>
```

**Person B** also edits `index.html`:
```html
<!DOCTYPE html>
<html>
<head>
  <title>Awesome Git Workshop</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Welcome to Git Workshop</h1>
  <p>Master Git through practical exercises!</p>
</body>
</html>
```

**Resolution:**
1. Person A pushes first
2. Person B gets conflict and resolves by combining the best of both:

```html
<!DOCTYPE html>
<html>
<head>
  <title>Awesome Git Workshop</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>Welcome to Git Workshop</h1>
  <p>Learn Git collaboration with hands-on exercises!</p>
  <h2>What You'll Learn:</h2>
  <ul>
    <li>Basic Git commands</li>
    <li>Collaboration workflows</li>
    <li>Conflict resolution</li>
  </ul>
</body>
</html>
```

---

## 🎖️ Workshop Completion Checklist

Mark off each item as you complete it:

- [ ] **Exercise 1**: Basic collaboration without conflicts
- [ ] **Exercise 2**: Created and resolved your first merge conflict
- [ ] **Exercise 3**: Resolved multiple file conflicts
- [ ] **Exercise 4**: Practiced conflict prevention through communication
- [ ] **Exercise 5**: Used branches to organize work
- [ ] **Exercise 6**: Completed a real-world scenario

## 🏆 Bonus Challenges

If you finish early, try these:

1. **Create a pull request workflow:**
   - Person B forks the repository
   - Makes changes in their fork
   - Creates a pull request
   - Person A reviews and merges

2. **Experiment with `git log`:**
   ```bash
   git log --oneline --graph --all
   ```

3. **Try reverting a commit:**
   ```bash
   git revert [commit-hash]
   ```

## 🆘 Common Commands Reference

### Basic Commands
```bash
git status                 # Check what's changed
git add [filename]         # Stage a file
git add .                  # Stage all changes
git commit -m "message"    # Commit with message
git push origin main       # Push to GitHub
git pull origin main       # Pull latest changes
```

### Conflict Resolution
```bash
git pull origin main       # This will show conflicts
# Edit files to resolve conflicts
git add .                  # Stage resolved files
git commit -m "Resolve conflicts"
git push origin main
```

### Branches
```bash
git branch                 # List branches
git checkout -b [name]     # Create and switch to branch
git checkout main          # Switch to main branch
git merge [branch-name]    # Merge branch into current
```

## 🎉 Congratulations!

You've completed the Git Collaboration Workshop! You now know:

- How to collaborate on projects using Git
- How to handle merge conflicts (the most feared Git scenario)
- Best practices for team development
- How to use branches for organized development

### Next Steps

- Practice these skills in your own projects
- Learn about advanced Git features like rebasing and cherry-picking
- Explore GitHub features like Issues, Projects, and Actions
- Consider learning about Git hooks and continuous integration

---

## 📞 Need Help?

If you get stuck during the workshop:

1. **Read the error message carefully** - Git usually tells you what's wrong
2. **Use `git status`** - It often suggests what to do next
3. **Don't panic about conflicts** - They're normal and fixable
4. **Ask your partner or workshop facilitator** - Collaboration includes asking for help!

Remember: Every Git expert has made mistakes and faced confusing conflicts. The key is to practice and not be afraid to experiment!

---

**Happy Git-ing! 🚀**