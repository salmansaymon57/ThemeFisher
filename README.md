#  Markdown Post Manager
This project is a Next.js application designed to create, manage, and publish Markdown files to a GitHub repository. It serves as a front-end development exercise utilizing TypeScript, Tailwind CSS, and server-side rendering (SSR) with the Next.js App Router. The application allows users to draft posts, edit or delete them, and publish them as Markdown files to a specified GitHub repository.
## Project Setup
### Prerequisites

#### Node.js: Version 18.x or later is recommended. Download here
#### Git: For version control and cloning the repository. Install Git
#### GitHub Account: To host the target repository and generate a personal access token.

### Installation

#### 1. Clone the Repository:
git clone <your-repository-url>
cd <repository-name>


#### Install Dependencies:
npm install


* Key dependencies include:
* next: For the Next.js framework.
* react and react-dom: For building the user interface.
* sanitize-html: To sanitize user inputs and prevent XSS attacks.
* axios: For HTTP requests (though native fetch is used in this setup).




# Environment Variables:

Create a .env.local file in the root directory.
Add the following:NEXT_PUBLIC_GITHUB_TOKEN=your_personal_access_token_here


Reasoning: The NEXT_PUBLIC_GITHUB_TOKEN authenticates API requests to GitHub. The NEXT_PUBLIC_ prefix makes it accessible on the client side for simplicity, though in production, consider a server-side API route for security.


Run the Development Server:
npm run dev


Access the app at http://localhost:3000. ✅



# Project Structure

/app: Contains Next.js App Router pages (e.g., page.tsx for the main page).
/components: Houses reusable components (e.g., PostForm.tsx, DraftList.tsx).
/utils.ts: Stores utility functions like input sanitization and GitHub publishing logic.
Reasoning: This structure separates concerns—pages for routing, components for UI, and utils for logic—enhancing maintainability and scalability.

# Usage

View Markdown Content:

The homepage displays Markdown content fetched from contents/hello.md in the salmansaymon57/seo-page1 repository.


Create a New Post:

Enter a title and body in the form.
Click "Add Draft" to save the draft to the server-side list.


Manage Drafts:

View the list of drafts below the form.
Click "Edit" to update a draft (submits the current values for simplicity).
Click "Delete" to remove a draft.


Publish Drafts:

Click "Publish All" to commit all drafts as Markdown files to the GitHub repository.
Drafts are cleared after successful publishing.


Error Handling:

Errors (e.g., missing token, failed publish) are displayed on the page with details logged to the console.



# Additional Tools and Libraries

Tailwind CSS: Used for styling to ensure a responsive and clean UI with minimal custom CSS.
Reasoning: Tailwind provides rapid development and consistency across components. 🌟


sanitize-html: Integrates security by sanitizing user inputs to prevent XSS.
Reasoning: Essential for safely handling user-generated content in a public-facing app. 🔒


Next.js App Router: Employs server-side rendering and Server Actions for a fully server-side experience.
Reasoning: Avoids client-side JavaScript where possible, aligning with your preference, and leverages SSR for SEO and performance. 🚀



# Reasoning Behind Design Choices

Server-Side Rendering: Chosen to avoid client-side state management (useState, "use client"), ensuring all logic runs on the server. This uses Server Actions and revalidatePath to update the UI.
GitHub Integration: The project targets salmansaymon57/seo-page1 for publishing, using the GitHub API’s contents endpoint, reflecting a real-world use case for content management.
Security: Input sanitization protects against malicious code, critical for user-submitted data.
Accessibility: ARIA labels and roles
Simplicity: The in-memory serverDrafts array simplifies state management without a database, suitable for this exercise.
