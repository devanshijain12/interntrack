# InternTrack

A responsive job and internship application tracker built with React and Vite. Track each opportunity from application through offer, move cards across a kanban board, and see your pipeline at a glance.

## Features

- Add, edit, and delete applications with company, role, type, location, date, link, and notes.
- Drag cards between five stages on desktop. Use the stage dropdown on touch devices.
- Search by company, role, location, or notes and filter by application type.
- Dashboard shows stage totals, active applications, offers, and a snapshot response rate.
- Export all applications to CSV, with correctly quoted fields for commas and line breaks.
- Data persists in your browser's `localStorage`; no account or server is needed.
- Responsive layout, keyboard focus states, semantic controls, and empty states.

## Screenshots

![Desktop application board](screenshots/board-desktop.png)

![Mobile application board](screenshots/board-mobile.png)

## Run locally

Requires Node.js 18 or newer.

```bash
npm install
npm run dev
```

Open the local address printed by Vite. For a production build, run `npm run build`, then `npm run preview`.

## Deployment

Netlify build command: `npm run build`. Publish directory: `dist`. The included `netlify.toml` sets these values and routes client-side paths back to the app.

Live demo: Pending deployment. Add the verified live URL here after publication.

## Design decisions and tradeoffs

- **Local-first:** all application records stay in the current browser. No backend, authentication, or cross-device sync. Users should export CSV to back up their data.
- **Demo records:** a new browser begins with three fictional sample applications to show the board. Editing or deleting them persists locally; clearing local storage resets the demo.
- **Stage model:** a single current status per application keeps the board simple. The response-rate metric counts records currently at assessment, interview, or offer; it is not a historical conversion metric.
- **Accessible fallback:** native drag-and-drop is supplemented by a stage selector on smaller screens.

## Stack

React 18, Vite 5, vanilla CSS, Web Storage API, native HTML drag-and-drop, Blob/URL APIs for CSV.

## Future improvements

Cloud sync and sign-in, reminders, detailed stage history, richer analytics, and import from CSV.

## License

MIT
