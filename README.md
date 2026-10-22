# Medi-Notes — Medication tracker

A lightweight, local-first medication tracker with the original Medi-Notes prototype theme. It requires no account, server-side code, API key, external library, or build process.

## Run locally

1. Open `index.html` in a modern browser, or serve this folder from a local static web server.
2. Add a doctor, then add medicines under that doctor.
3. Dose check-offs, doctors, medicines, schedules, and follow-up dates are saved automatically in browser storage.

For the most reliable persistent storage, use the published HTTPS GitHub Pages URL. Some browsers treat locally opened `file://` pages differently, so local-file storage may behave differently from the hosted website.

## Publish with GitHub Pages

1. Create a new GitHub repository, for example `medi-notes`.
2. Upload or push `index.html` and this `README.md` to the repository root.
3. In GitHub, open **Settings → Pages**.
4. Under the build/deployment options, select **Deploy from a branch**, choose `main` and `/ (root)`, and save. If your repository uses another branch, select that branch instead.
5. Wait for GitHub Pages to publish, then open the URL GitHub shows. It will usually look like `https://<your-username>.github.io/medi-notes/`.
6. Use that same URL and browser profile each time so the application reads the same local storage area.
7. To update the website, commit/push the updated files to the publishing branch.

This app is static and is compatible with a repository-subpath URL. No backend or GitHub token is required.

## Data storage and privacy

Medi-Notes stores the user's records in browser `localStorage` on the device. Data is not uploaded to GitHub, sent to a server, or synchronized between devices. The application asks the browser to persist local storage where that capability is available, but browser storage is not a guaranteed backup. Clearing browser/site data, losing the browser profile, or switching browsers can make records unavailable.

Use **Export backup** regularly. The JSON backup can be restored with **Import backup** on the same or another device. A one-time migration copies data from the prototype's earlier `dosebook.data.v1` storage key to the new `medi-notes.data.v1` key where available.

## Device calendar export

Use **Device calendar** in the adherence-calendar header to download an `.ics` file containing scheduled doses for the next 90 days (for medicines marked as purchased) and future doctor follow-ups. Open or import the file with a compatible calendar app such as Apple Calendar, Google Calendar, or Outlook. Calendar export is a snapshot, not automatic two-way sync; export again after editing schedules or follow-ups. Calendar notifications depend on the receiving calendar app and device settings. Imported events may also sync through that calendar app according to its own account settings.

## Included functionality

- Multiple doctors with each doctor's medicines grouped together.
- Per-medicine instructions, quantity, morning/afternoon/night times, meal timing, start date, finite course length or ongoing schedule.
- Daily, alternate-day, or selected-weekday schedules.
- Mark each scheduled time as taken for today or any selected date.
- Contribution-style, year-based adherence calendar: green means all tracked doses completed; orange means up to 25% of trackable doses are overdue/missed; red means more than 25% are overdue/missed; striped gray means one or more scheduled medicines need purchase; blue indicates doses still in progress/not yet overdue.
- A medicine can be marked as not yet purchased. Such doses remain visible and are kept distinct from missed doses.
- Doctor follow-up dates.
- An on-open reminder for purchased, unchecked doses at least two hours past their configured time. The browser-only app cannot show its own popup while fully closed.
- Local JSON backup export/import.
- Device-calendar export using `.ics`.

## Medical-use note

Medi-Notes is a reminder and logging tool, not medical advice. It does not recommend doses or tell users how to make up missed doses. Follow the prescription and ask a clinician or pharmacist when uncertain.
