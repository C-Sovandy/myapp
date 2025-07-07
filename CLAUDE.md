# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

### Local Development (npm)
- **Development server**: `npm run dev` - Starts Vite development server with HMR
- **Build**: `npm run build` - Creates production build
- **Lint**: `npm run lint` - Runs ESLint on all files
- **Preview**: `npm run preview` - Previews production build locally

### Docker Development
- **Development with Docker**: `docker-compose up dev` - Starts development server in container with hot reload
- **Production build**: `docker-compose up app` - Builds and runs production version
- **Build Docker image**: `docker build -t myapp .` - Builds production Docker image
- **Run Docker container**: `docker run -p 3000:80 myapp` - Runs production container

## Architecture

This is a React application built with Vite using a component-based architecture:

- **Entry point**: `src/main.jsx` - React app initialization with StrictMode
- **Root component**: `src/App.jsx` - Main application component that renders all child components
- **Components**: Located in `src/components/` directory
  - `Greeting.jsx` - Displays greeting message
  - `Job.jsx` - Shows job information
  - `Message.jsx` - Displays lorem ipsum text
- **Styling**: Uses CSS modules and global styles
  - `App.css` - Main application styles
  - `index.css` - Global styles
  - `components/greeting.css` - Component-specific styles

## Tech Stack

- **Framework**: React 18.3.1
- **Build tool**: Vite 5.4.10
- **Linting**: ESLint 9.13.0 with React-specific rules
- **Module system**: ES modules (type: "module" in package.json)

## Project Structure

The app follows a standard React + Vite structure with components organized in a dedicated folder. All components are functional components using arrow function syntax.

## Docker Setup

- **Dockerfile**: Multi-stage build for production (Node.js build → Nginx serve)
- **Dockerfile.dev**: Development container with hot reload
- **docker-compose.yml**: Contains both development and production services
- **.dockerignore**: Excludes unnecessary files from Docker build context