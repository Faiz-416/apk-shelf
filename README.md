# APK Shelf

A minimal, responsive static website for listing and downloading Android APK files. It has no framework, database, or build step and can be deployed to Vercel.

## Quick start

1. Put your APK files in the `apks/` folder.
2. Open `index.html` and edit each app card.
3. Change the download link to the relative file path, for example:
   `<a class="download" href="/apks/my-app-v1.0.apk" download>Download APK ↗</a>`
4. Replace the app name, version, description and file-size text.
5. Push the folder to a GitHub repository and import that repository at https://vercel.com/new.

## Add an APK card

Copy one complete `<article class="app">...</article>` block inside `<section class="apps" id="apps">`. Update:
- `.app-icon`: initials or a short symbol
- `h3`: app name
- `.version`: version number
- `.desc`: short description
- `.size`: APK file size
- the download link `href`: path to the APK

For a real download link, remove `disabled` from the class, remove `aria-disabled="true"` and remove the `onclick="return false;"` attribute. Example:

`<a class="download" href="/apks/your-app-v1.0.apk" download>Download APK ↗</a>`

## Deploy to Vercel

1. Sign in to GitHub and create a new repository, e.g. `apk-shelf`.
2. Upload `index.html`, `README.md`, and the `apks/` folder (including your APK files).
3. Open https://vercel.com/new and import the repository.
4. Leave the framework preset as **Other**. No build command is needed; deploy the project root.
5. When deployment finishes, open the generated `.vercel.app` URL.

Each push to the connected GitHub branch triggers a new deployment.

## Important storage note

This starter is best for a small number of modest-sized files. Large APKs or frequent updates are better hosted on GitHub Releases or object storage, with the site linking to those files. Do not commit secrets or private signing keys to the repository.
