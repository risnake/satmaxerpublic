An adaptive web application for digital SAT preparation.

This project is a modern, full-stack web application designed to provide a realistic and effective practice environment for students preparing for the digital SAT. It leverages a modern tech stack to deliver a responsive, data-driven, and user-friendly experience.
<div align="center"> <a href="https://satmaxer.win" target="_blank"> <img src="https://placehold.co/600x400.png" alt="SATMaxer Application Screenshot" style="border-radius: 8px; width: 70%;" data-ai-hint="application interface"> </a> </div> <h2 align="center"> <a href="https://satmaxer.win" target="_blank">Visit SATMaxer.win</a> </h2>

    Adaptive Practice Tests: Simulates the official digital SAT with a multistage adaptive format. The difficulty of the second module is tailored based on performance in the first.
    Question Flurry: A flexible practice mode allowing users to create customized quizzes by filtering questions by subject, domain, and difficulty.
    Review Mistakes: Automatically tracks incorrect answers and compiles them into a dedicated review queue for targeted learning.
    Performance Statistics: A detailed dashboard tracks overall accuracy, time practiced, and provides in-depth performance breakdowns for every completed test.
    User Authentication: Secure sign-in and data persistence using Google Authentication via Firebase.

The application is built with a modern, component-based architecture.

| Category | Technology | | :------------ | :---------------------------------------------------------------------------------------------------------- | | Frontend | Next.js (with App Router), React, TypeScript | | Styling | Tailwind CSS, ShadCN UI (for component primitives) | | Backend | Firebase (Authentication, Firestore Database) | | Deployment| Firebase App Hosting |

The user interface is built with React and Next.js, utilizing the App Router for server-side rendering and efficient page navigation. TypeScript is used throughout the project for type safety and improved code quality.

Styling is managed with Tailwind CSS for utility-first styling and ShadCN UI for a set of accessible and customizable base components. This combination allows for rapid development of a clean, consistent, and responsive UI.

    Client-Side State: React Hooks (useState, useContext, useEffect) are used extensively for managing component-level and shared UI state. Custom hooks (useAuth, useUserData, useQuestions) abstract complex logic and provide clean APIs for components to consume.
    Data Fetching: The entire question bank is fetched from an external API upon initial application load and stored in a React Context (QuestionProvider). This in-memory storage strategy makes subsequent operations like filtering and generating tests extremely fast, as no further network requests are needed for question data.

The backend is powered entirely by Firebase:

    Authentication: Firebase Authentication handles user sign-up and sign-in, with support for Google's OAuth provider.
    Database: Firestore, a NoSQL document database, stores all user-specific data, including:
        User statistics (accuracy, time practiced, domain performance).
        A list of questions the user has answered incorrectly.
        Detailed results from completed adaptive practice tests.

The src directory is organized to separate concerns and maintain a clean codebase.

src/
├── app/                # Next.js App Router pages and layouts
├── components/         # Reusable UI components (both custom and ShadCN)
├── hooks/              # Custom React hooks for state management and logic
├── lib/                # Core logic, type definitions, and Firebase configuration
├── ai/                 # Genkit AI flows and configuration (if used)
└── ...

    src/app: Contains all pages and routing logic for the application. Each folder represents a route.
    src/components: Houses all reusable UI components, including the ./ui subdirectory for ShadCN components.
    src/hooks: Contains custom React hooks that encapsulate complex logic (e.g., useAuth, useUserData). This promotes code reuse and separation of concerns.
    src/lib: A collection of utility functions, Firebase configuration (firebase.ts), Firestore interaction logic (firestore.ts), and TypeScript type definitions (types.ts).
