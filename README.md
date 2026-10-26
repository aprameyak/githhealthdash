# GitHub Project Health Dashboard

A small Express app for keeping a list of repositories with their language, star count, and last update date. It is a starting point for a personal dashboard of projects you maintain or follow.

## Features

- Add a repository with name, language, stars, and last update date
- Lists repositories sorted by star count
- Returns the total number of tracked repositories
- Saves entries to a local `data.json` file

## Getting started

Requires Node.js.

```bash
npm install
npm start
```

The server runs on http://localhost:3021. Add a repository and list them:

```bash
curl -X POST http://localhost:3021/api/repos \
  -H "Content-Type: application/json" \
  -d '{"name":"my-app","language":"JavaScript","stars":42,"lastUpdate":"2026-10-01"}'

curl http://localhost:3021/api/repos
```

## How it works

- `server.js` is an Express server with `POST /api/repos` and `GET /api/repos`.
- Repository details are entered by hand. The app does not call the GitHub API, and the `issues`, `prs`, and `health` fields are placeholders (`0`, `0`, and `stable`).
- Entries are stored in `data.json` in the project folder, which is created on first run and ignored by git.
- `index.html` is served at the root URL but is still a generic placeholder form that is not connected to this API. `utils.js` contains helpers that `server.js` does not use yet.

## Status

Prototype. No GitHub integration yet; the web page is not wired up, and there is no validation or authentication.

## License

MIT, see [LICENSE](LICENSE).
