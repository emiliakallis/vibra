# Vibra – Real-Time Music Sharing & Recommendation Platform
> Full-stack social music app with personalized recommendations, real-time chat, and profile-based discovery – built with React Native, Django, and Jamendo API.


<div align="center">

<table>
<tr>
<td align="center">

<b>Frontend Repository</b><br>
<a href="https://github.com/jros00/vibra-frontend">
  <img src="https://img.shields.io/github/languages/top/jros00/vibra-frontend" alt="Top Language – Frontend">
</a><br>
<a href="https://github.com/jros00/vibra-frontend/graphs/contributors">
  <img src="https://img.shields.io/github/contributors/jros00/vibra-frontend" alt="Contributors">
</a>
<a href="https://github.com/jros00/vibra-frontend/commits/main">
  <img src="https://img.shields.io/github/last-commit/jros00/vibra-frontend" alt="Last Commit">
</a>

</td>
<td align="center">

<b>Backend Repository</b><br>
<a href="https://github.com/jros00/vibra-backend">
  <img src="https://img.shields.io/github/languages/top/jros00/vibra-backend" alt="Top Language – Backend">
</a><br>
<a href="https://github.com/jros00/vibra-backend/graphs/contributors">
  <img src="https://img.shields.io/github/contributors/jros00/vibra-backend" alt="Contributors">
</a>
<a href="https://github.com/jros00/vibra-backend/commits/main">
  <img src="https://img.shields.io/github/last-commit/jros00/vibra-backend" alt="Last Commit">
</a>

</td>
</tr>
</table>

</div>

## Project Overview

Vibra is a full-stack mobile application that enables users to discover, share, and discuss music in real time. The platform features a React Native (Expo) frontend and a Django/Django REST Framework backend, allowing users to stream recommended tracks and chat with friends about music. Key functionalities include personalized “For You” music recommendations, real-time chat messaging with song sharing, and social features like user profiles and notifications. The project’s goal was to create an interactive music experience – from fetching similar songs via the Jamendo API to enabling live discussions – all within a seamless mobile app environment.

## Table of Contents

- [Project Overview](#project-overview)
- [My Role on the Project](#my-role-on-the-project)
- [My Technical Contributions](#my-technical-contributions)
- [Technologies & Tools](#technologies--tools)
- [Project Links](#project-links)
- [Outcome](#outcome)

## My Role on the Project

I was part of a five-member team developing Vibra, serving as the full-stack developer and technical lead. I took a leading role in both backend and frontend development, ensuring consistent technical progress and delivery of core features. My responsibilities included designing and implementing backend architecture (real-time communication, recommendation algorithms, user management) using Python/Django, and building key frontend features (navigation flows, state management, UI components) with React Native and TypeScript.

Beyond implementation, I proactively organized check-ins, offered support to teammates, and took ownership of features when timelines were at risk. I frequently coordinated integration work—merging pull requests, resolving conflicts, and aligning frontend-backend interactions to ensure a seamless mobile experience. This cross-functional role required strong technical execution, architectural ownership, and collaborative development practices.

## My Technical Contributions

The contributions below represent the key areas I personally developed across the codebase.

### Real-Time Chat & Notifications (Backend)
Implemented a WebSocket-based real-time chat service using Django (ASGI/Channels), enabling users to exchange messages and music tracks instantly within the app. I developed the backend logic to broadcast messages to recipients and persist chats, and integrated Redis as a message broker for scalable WebSocket communication. I also added support for direct messages and notifications on the backend, so that users receive alerts when new songs or messages arrive.

### Real-Time Chat Interface (Frontend)
Built the frontend chat interface and integrated it with the WebSocket backend. This involved using React Native to update chat views live as messages arrive and ensuring shared songs in chats play seamlessly. I resolved several issues to make the chat feature stable (e.g. fixing a bug where multiple audio tracks would play on overscroll) and ensured the chat UI correctly shows message senders. The result was a smooth in-app messaging experience synchronized with backend events.

### Music Recommendation Engine (Backend)
Developed core recommendation features for Vibra’s music discovery. I integrated Jamendo’s API to fetch track data and audio features, then implemented a similarity computation to recommend tracks. I improved the algorithm by switching from a Euclidean distance metric to Cosine similarity for comparing audio feature vectors, utilizing all available features (not just MFCC coefficients) for more accurate recommendations. I also wrote backend routines to fetch and pre-process song data (including album art and audio stream URLs), allowing the app to play tracks on the fly without local storage.

### “For You” Feed & User Personalization
Extended the backend and database to support personalized content. I created a new Django app (tentatively named “action”) to track user interactions, enabling features like user-specific ratings and a listening history log. This data was used to tailor the “For You” recommendation feed. On the frontend, I ensured the feed UI could display track color themes and other metadata directly as provided by the backend, eliminating the need for extra processing on the client.

### User Profiles and Social Features
Implemented robust user profile functionality across the stack. On the backend I added model fields and API endpoints for profile pictures, bios, follow metrics, and liked tracks. I also set up Django signals to handle profile-related events (e.g. creating default profile data when a new user registers). On the frontend, I developed the profile screen UI, showing user info and enabling bio edits and profile photo updates. I also introduced a “liked by” tag on shared songs in chat so users can see who liked a track, enhancing the social interactivity of the app.

### Authentication & State Management
Built the user login/logout flow and session handling on both client and server. I added secure login APIs on the Django side and integrated them with the React Native frontend login screen. The frontend now stores authentication state and user info locally, so the app can manage the logged-in user’s experience entirely on-device. This work involved coordinating with backend authentication middleware and ensuring token-based auth was handled in API requests.

### Frontend Architecture & UI Enhancements
Led a major refactor of the React Native app’s navigation and component structure. I replaced the initial Expo router with a custom navigation setup for finer control over screens and deep linking, particularly to better handle the chat interface and back-navigation behavior. I also split monolithic screens into modular components and files, improving maintainability and clarity of the codebase. Throughout development, I made numerous UI/UX improvements: standardizing the color scheme, aligning headers and layout, and fixing UI bugs (such as error messages in the chat song component and navigation glitches). These changes greatly improved the app’s stability and user experience on both Android and iOS.

### Backend API Design & Refactoring
Restructured the backend into a cleaner, more scalable API. I transitioned legacy endpoints to Django REST Framework viewsets for a consistent RESTful design. I reorganized the codebase into multiple Django apps (e.g. separate apps for home feed, user messages, notifications, etc.) to encapsulate functionality. In addition, I improved URL routing for clarity – for example, simplifying endpoints by removing outdated terms like “predict” from the URLs. This refactor made the server code more modular and easier for the team to work on concurrently.

### Collaboration & Leadership
Beyond coding, I played an active role in collaborative development. I frequently merged branches and pull requests (integrating code from teammates) and resolved merge conflicts to keep the project moving forward. Several backend features authored by teammates were reviewed and committed by me to ensure consistency and quality. I also coordinated closely with the frontend team (e.g. aligning on data formats for sockets and REST, adjusting API responses so the React Native app could use them directly). My proactive communication and willingness to assist across the stack helped the team deliver a cohesive final product on a tight timeline.

## Technologies & Tools

**Frontend:** **React Native** (**Expo**), **TypeScript**, React Navigation, state management for real-time updates, **Axios** for API calls. Emphasis on responsive UI and smooth user experience on mobile (tested on both iOS and Android).

**Backend:** **Python Django** with **Django REST Framework**, **Django Channels** (WebSocket support), **SQLite** (development DB), **Redis** (for pub/sub in real-time chat), and external APIs (**Jamendo** for music data). Utilized Python libraries for audio feature processing and ensured the server could stream audio content.

**Development & Collaboration:** **Git and GitHub** for version control, where I handled branching and pull request merges. Employed agile practices – frequent commits, code reviews, and debugging in a team setting. Also used **Jupyter** (notebook for prototyping algorithms – e.g., audio feature computations in `computations.ipynb`) and adhered to good DevOps practices (documenting setup in README, managing environment files appropriately).

## Project Links

- 🔗 [Frontend Repository](https://github.com/jros00/vibra-frontend)
- 🔗 [Backend Repository](https://github.com/jros00/vibra-backend)
- 🌐 [Live Website (Wix Demo)](https://emiliakallis.wixsite.com/vibra)

👉 For UI previews and app walkthroughs, visit the [Live Demo Site](https://emiliakallis.wixsite.com/vibra)

## Outcome

By project’s end, I had made substantial contributions to a fully functioning application that blends a rich backend (recommendation engine, real-time services, robust API) with an intuitive frontend. This experience showcased my ability to work end-to-end on complex features: from database and server logic to the pixel-perfect mobile UI. It also highlights my strengths in problem-solving, adaptability, and teamwork – crucial qualities for a full-stack or backend-focused developer. I am proud that our team delivered an innovative platform like Vibra, and I’m excited to bring these skills to future projects.
