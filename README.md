# Plantsy 🌱

A React + JSON Server application for managing a plant shop's inventory. Built as
part of a lab on connecting a React frontend to a backend API using `fetch`,
`useEffect`, and controlled forms.

## Demo

![Demo GIF](./demo.gif)

<!-- Replace the line above (or add below it) with a screenshot of your finished app, e.g.: -->
<!-- ![App Screenshot](./screenshot.png) -->

## Description

Plantsy lets a shop admin:

- View all plants in inventory on page load (fetched from a JSON Server backend)
- Add a new plant via a form, which persists it to the backend
- Mark any plant as "In Stock" / "Out of Stock" (local UI state, not persisted)
- Search plants by name, filtering the list in real time

## Tech Stack

- React (function components + hooks: `useState`, `useEffect`)
- Vite
- JSON Server (mock REST API)
- Vitest + React Testing Library (test suite)

## Installation

Clone the repo and install dependencies:

```bash
git clone https://github.com/omichell-droid/react-hooks-plantshop-cr-vite.git
cd react-hooks-plantshop-cr-vite
npm install
```

## Usage

Run the backend and frontend in separate terminals:

```bash
npm run server   # starts JSON Server on http://localhost:6001
npm run dev       # starts the Vite dev server (usually http://localhost:5173)
```

Open the printed local URL in your browser to use the app. You can verify the
backend independently by visiting
[http://localhost:6001/plants](http://localhost:6001/plants).

### Running tests

```bash
npm run test
```

This runs the full Vitest suite covering: rendering plants on load, adding a
plant via the form, marking a plant out of stock, and search filtering.

## API

Base URL: `http://localhost:6001`

**GET `/plants`** — returns all plants

```json
[
  { "id": 1, "name": "Aloe", "image": "./images/aloe.jpg", "price": 15.99 }
]
```

**POST `/plants`** — creates a new plant

Headers:
```json
{ "Content-Type": "application/json" }
```

Body:
```json
{ "name": "string", "image": "string", "price": "number" }
```

## Roadmap

- Persist "out of stock" status to the backend (currently local-only)
- Add plant deletion and editing
- Add form validation and error states

## Author

Built by [Your Name] as part of a Flatiron School / Learn.co lab.
