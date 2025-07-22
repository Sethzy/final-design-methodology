# 🛠️ **Prompt-Library Workflow Overview**

---

- [ ] **Initialize in Lovable and pull to cursor:** Use the `initialize-Lovable-Project.md` file.

Make sure the specifiy Tailwind v3, not 4.

Port over to Cursor, initialise the git repo locally. Make sure the global cursor rules and Claude.MD rules are set properly to be automatically read. 


- [ ] Add CSS

Find a TweakCN CSS file and immediately copy and paste it over to your index.css file.

It should be in the correct tailwind version, and in HSL. Don't install it via pnpm. it seems to bug. 

Use @1a. css-validation-tweakcn.md which contains the necessary instructions. 


## 1. Product Roadmap Generation

- [ ] Generate Product Roadmap:
  - Use `generate-ProductRoadmap.mdc` to create the comprehensive product roadmap.
- [ ] ~~**_Feature Selection for MVP:_**~~
  - From the generated roadmap, select only the features essential for the **Minimum Viable Product (MVP)**.

---

##design 

Based on the described MVP features and some screenshots, use @ 1b. generate-ui-implementation-plan.md

This will give a skeleton of all the UI elements that needs to be implemented. 

make sure to reference 





Then follow through 1a, 1b,1c,2a,2b. see shadcn-mcp-instructions. 


## 2. Designer iteration. 



- [ ] **Generate Designer Prompts:**
  - Use `generateDesignerPrompt.mdc` to obtain initial Ui/Ux prompts for the selected MVP features.
    - _If you need to manually specify in frontend language, check:_
      - https://ui.shadcn.com/ documentation
      - https://aura.build/learn/prompt-for-layout
- [ ] **Prerequisite:**
  - Ensure the corect `design.system` file is properly referenced before using `generateDesignerPrompt.mdc`.
  - Generate alist of screens from the MVP features

---

## 3. Initial Development Steps

Use **Design-prompt** and

- [ ] **Create Global CSS File:**
  - Develop the initial **CSS** file, specifically a global CSS file.
- [ ] **Generate First HTML Screen:**
  - Use the initial CSS file (based on the **design system**) to create the first **HTML** screen.

> _This process is **iterative**, progressing from **low-fidelity wireframes** to a **high-fidelity** full HTML screen with Tailwind CSS._

---

## 4. Post HTML Screen Completion Workflow

- [ ] **Capture Screenshots:**
  - Take screenshots of all completed screens.
- [ ] **Store Screenshots:**
  - Place these screenshots in the `screenshots` folder within the `design HTML library` folder.
- [ ] **Purpose:**
  - These screenshots will serve as a reference for lovable.

---

## 5. Updating the Design Prompt

- [ ] **Locate:**
  - Find the "design prompt library" folder.
- [ ] **Action:**
  - Update the design prompt within this folder.
- [ ] **Purpose:**
  - Incorporate the changes made during the iterative design process with HTML back into the prompt.

---

## 6. Initialize the `lovable` Project

- [ ] **Initialize:**
  - Use the `initialize-Lovable-Project.md` file.
- [ ] **Design System Integration:**
  - Reference the same design system to `lovable`.
- [ ] **CSS File Creation:**
  - Reference the necessary **CSS file**.
- [ ] **UI/UX Development:**
  - Begin creating the **UI/UX screen by screen** using the **updated Ui/Ux prompt for the feature**.
    - Reference the **HTML code**.
    - Reference the **screenshots**.

> _Tip: Use Stagewise or Lovable's UI to pick the element before asking it to make changes so it knows which file to use._

---

## 7. Post-Screen Completion Workflow (Lovable)

- [ ] **Push to GitHub:**
  - After completing the first screen, **push** the changes to GitHub.
- [ ] **Pull into Cursor:**
  - Once pushed, **pull** that screen into Cursor.
- [ ] **UI/UX Modifications:**
  - Make any necessary **UI/UX changes** within Cursor.

---

## 8. Post-MVP Screens Development Checklist

- [ ] **Authentication Setup:**
  - Implement user authentication.
- [ ] **Payment Integration:**
  - Set up payments via **Lovable**.
  - Direct integration with **Supabase** and **Stripe**.

---

## 9. Backend Logic

- [ ] **Start backend logic**
  - [ ] Run `create research doc.mdc` (if feature is complex, else skip to generate PRD)
    - [ ] Internal evaluation of the codebase
    - [ ] External research
  - [ ] Use `generate PRD document` (after research document output is complete)
    - [ ] Detail implementation for the feature
  - [ ] Use `generate tasks from PRD.mdc` (once PRD is satisfactory)
    - [ ] Generate a task list
  - [ ] Use `task list.mdc`
    - [ ] Execute tasks (tell AI how to execute)

---
Update the repo with improved cursor and claude.md rules using repomix 

https://repomix.com

Use this to turn it into ur Claude code rules  




## 10. General Guidelines

- [ ] **Always create a README file** after completing any major task. Use `generate-read-me.mdc`.
- [ ] **Commit locally** on Git frequently. Things will break.
- [ ] **Use voice dictation**
- [ ] **Do not commit to your remote repository** unless you are confident you've hit a **real checkpoint**.
- [ ] **Be aware of the conflict between Lovable and Cursor.**
  - Forgetting to pull will cause bugs.
