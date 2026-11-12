# My Task Feature — OWL Learning

A task management feature I built for the OWL e-learning platform at PT Krakatau Posco. With this feature, admins can assign tasks to learners within the existing learning flow, and learners can view, work on, and submit their tasks from the My Task page.

_This documentation reflects the project state as of November 12, 2026._

<!-- Once screenshots are added to the images/ folder, remove this comment.
     Files referenced below: dashboard-admin.png, form-create-task.png,
     dashboard-user.png, global-task.png, review-submissions.png -->

## Background

Before this feature existed, assigning tasks to learners had no dedicated place inside the LMS. My Task integrates tasks directly into OWL's learning structure: tasks are placed on the material learners are studying, so the context of each task is always clear.

## How It Works

### Task Placement

A task can be placed under three types of parents:

- **Playlist**
- **Content**
- **Offline Training** (placement is available; offline training data is not yet connected to the project, so this option is not yet active)

In addition, a task can also be created **without placement (standalone)**, for tasks that are not tied to specific material.

On the learner side, a published task appears on the My Task page once the learner has opened its parent (the related playlist/content). Tasks in a playlist can also be unlocked by learners from the playlist page.

### Task Groups

Tasks can be grouped into **groups** (title + description) so that managing a large number of tasks stays organized. A deleted group goes to the trash (soft delete) and can be restored.

### Task Types

There are 5 task types, and the task creation form adjusts its contents to the selected type:

1. **File Submission** — learners upload a file as the answer. Admins set the allowed file types, the maximum size per file, and an option for learners to submit a Google Drive link instead.
2. **Course Assignment** — learners open a linked course. A course inside the LMS marks the task as completed automatically when the course progress reaches 100%, while an external-link course is marked as completed manually by the learner ("Mark as Complete").
3. **Survey** — learners fill in an existing survey form in the LMS; the admin picks the target survey from a dropdown.
4. **Essay / Reflection** — learners answer in long text; the admin grades manually.
5. **Action Plan** — a Google Form-style form builder: short answers, paragraphs, multiple choice, checkboxes with minimum/maximum selection limits, dropdowns, files, scales, and star ratings. The admin reviews the answers manually.

### Standalone Tasks: Access Codes, QR Codes, and Trash

- A standalone task can be protected by an **access code** typed manually by the admin (maximum 12 characters, unique)
- Learners open a standalone task in three ways: entering the access code, opening a redeem link, or opening a signed URL
- Tasks are shared via **QR code**; changing the access code automatically invalidates the old link/QR
- Deleting a task is a **soft delete**: the task goes to the **Trash** and can be **Restored** or permanently deleted (**Delete forever**). The unified trash has a type filter and supports bulk actions (select all, restore / permanent delete in bulk)

## Admin View

- The Task Management dashboard shows tasks by their container (parent/group), with search and a searchable (AJAX) item dropdown
- The task creation form has placement selection, task type, and question settings that adapt to the type
- Row actions are grouped into a single "..." dropdown, following the pattern of the Assessment page
- **Submission review:** the submissions list has quick filters (all / needs review / approved / rejected) and a review window (modal) to grade each learner. Admins can **approve**, **reject**, or **request a resubmission**; a task that is requested for resubmission is marked with a revision badge on the learner side
- **Document preview** directly from the review page, including presentation files (PPT/PPTX) and PDFs
- **Exporting results:** submissions can be downloaded as Excel/CSV, and all learner attachments can be downloaded at once as a ZIP

## Learner View

- The My Task page shows a summary and the learner's task list, grouped by category, with a Content Playlist quick filter
- After submitting a task, the learner receives a success confirmation pop-up
- Tasks from a linked course show their completion status automatically ("Course completed")
- Tasks that the admin asked to be resubmitted are shown with a revision marker

## Screenshots

![Task Management Dashboard (Admin)](images/dashboard-admin.png)
*Task Management dashboard on the admin side*

![Task Creation Form](images/form-create-task.png)
*Task creation form with placement and task type selection*

![Learner My Task Page](images/dashboard-user.png)
*The My Task page on the learner side*

![Standalone Task & Access Code](images/global-task.png)
*A standalone task with an access code and QR code*

![Submission Review](images/review-submissions.png)
*The learner submission review page on the admin side*
