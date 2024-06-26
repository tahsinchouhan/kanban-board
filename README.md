# Kanban

Tahsin Chouhan Coding Assessment Kanban Board

Kanban is a Kanban board application built using Next.js. It provides a user-friendly interface for managing tasks and organizing projects using the Kanban methodology. This readme file provides an overview of the project and its setup instructions.

## Features

-   **Kanban Board**: Create boards with customizable columns and cards to manage tasks efficiently.
-   **User Authentication**: Users can create accounts and log in using Google.
-   **Cloud Database**: Utilizes a cloud-hosted database on PlanetScale to store board and user data securely.
-   **Continuous Integration**: Integrates with GitHub Actions for automated testing and deployment.
-   **Automated Tests**: Includes unit tests, Playwright tests for API and UI, and Chromatic tests for visual regression.
-   **Documentation**: Utilizes Storybook to create interactive component documentation for easy reference.

## Getting Started

To get started with Kanban, follow these steps:

### Prerequisites

-   Node.js (v14 or higher)
-   npm package manager

### Installation

1. Clone the project repository from GitHub:


2. Install the project dependencies:

    cd kanban-next
    npm install
### Configuration

Before running the application, you need to set up the required environment variables. Create a `.env` file in the project root directory and add the following variables:

```
SECRET=next-auth-secret
GITHUB_SECRET=github-oauth-secret
GITHUB_ID=github-oauth-id
GOOGLE_CLIENT_ID=google-client-id
GOOGLE_CLIENT_SECRET=google-client-secret
DATABASE_URL=database-url
```

Replace each placeholder value with your specific configuration. Note that `EMAIL_SERVER` refers to the SMTP server used for sending authentication emails.

### Database Setup

Kanban uses a cloud-hosted database on PlanetScale. To run the project locally, you will need to create your own database and set the `DATABASE_URL` environment variable accordingly. Push the Prisma schema to your database by executing the following command:

```bash
npx prisma db push --preview-feature
```

### Running Locally

To start the local development server, run the following command:

```bash
npm run dev
```

Open your web browser and navigate to `http://localhost:3000` to access the application.

## Testing

Kanban includes various testing options:

-   **Unit Tests**: Execute unit tests using the following command:

    ```bash
    npm test
    ```

-   **Playwright Tests**: Run Playwright tests for API and UI using the command:

    ```bash
    npm run test:e2e
    ```

    Running Playwright tests locally requires the WEBHOOK_ID and WEBHOOK_ID_ALT environment variables mentioned in [Continuous Integration](#continuous-integration) to be set.

-   **Chromatic Tests**: Chromatic tests for visual regression are executed during the CI process.

## Documentation

Kanban utilizes Storybook to generate component documentation. To view the component documentation locally, run the following command:

```bash
npm run storybook
```

Open your browser and navigate to `http://localhost:6006` to access the Storybook

interface.

## External Services

Kanban relies on several external services, such as authentication providers, SMTP servers, and the cloud-hosted database. To set up these services, refer to their respective documentation:

-   [Google OAuth](https://developers.google.com/identity/protocols/oauth2)
-   [GitHub OAuth](https://docs.github.com/en/developers/apps/building-oauth-apps)
-   [Supabase](https://supabase.com/)

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

Special thanks to [Frontend Mentor](https://www.frontendmentor.io/) for providing the design and to the following technologies and libraries used:

-   [Next.js](https://nextjs.org/)
-   [Prisma](https://www.prisma.io/)
-   [Storybook](https://storybook.js.org/)
-   [Playwright](https://playwright.dev/)
-   [React Testing Library](https://testing-library.com/)
-   [Vercel](https://vercel.com/)
-   [Chromatic](https://www.chromatic.com/)
-   [NextAuth](https://next-auth.js.org/)
