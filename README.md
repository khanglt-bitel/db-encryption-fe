# db-encryption-fe

This repository contains a very small example front-end to upload files to a backend endpoint and display the decrypted files returned by the server.

Open `index.html` in a browser. The page uses React from a CDN so there is no build step required.

## Workflow
1. Select one or more files using the file picker.
2. Click **Submit** to send them to the backend (`/api/decrypt`).
3. The backend is expected to respond with JSON in the following shape:

```json
{
  "decryptFiles": [
    { "fileName": "example.txt", "fileContent": "..." }
  ]
}
```
4. The returned files are listed with their file names and contents.

Update `BACKEND_URL` inside `index.html` if your backend uses a different URL.

## Docker

A simple `Dockerfile` is provided to serve the application using Nginx.

Build the image:

```bash
docker build -t db-encryption-fe .
```

Run the container:

```bash
docker run -p 8080:80 db-encryption-fe
```

Then open `http://localhost:8080` in your browser.
