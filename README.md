<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Fix: Incorrect German Translation for "Date and Time"</title>
</head>
<body>
  <h1>🔧 Fix: Incorrect German Translation for "Date and Time"</h1>

  <h2>📝 Summary</h2>
  <p>This change fixes an incorrect or missing German translation for the key <code>"bookingDateTime"</code> in the Cal.com project. The translation is now properly set to <strong>"Datum und Uhrzeit"</strong> in the <code>de/common.json</code> locale file.</p>
  <p>Additionally, the end-to-end test file <code>locale.e2e.ts</code> has been updated to verify that this translation is correctly displayed on the <code>/event-types</code> page.</p>

  <h2>🛠️ Changes Made</h2>
  <ul>
    <li><strong>Updated German locale file:</strong><br />
      <code>apps/web/public/static/locales/de/common.json</code>
      <pre><code>{
  ...
  "bookingDateTime": "Datum und Uhrzeit"
}</code></pre>
    </li>
    <li><strong>Modified locale test:</strong><br />
      <code>apps/web/tests/e2e/locale.e2e.ts</code>
      <pre><code>await test.step("should navigate to /event-types and show Uhr translations", async () => {
  await page.goto("/event-types");
  // other assertions to verify translation presence
});</code></pre>
    </li>
  </ul>

  <h2>🧪 How to Test It Locally</h2>
  <ol>
    <li>Install dependencies:
      <pre><code>npm install</code></pre>
    </li>
    <li>Fix dependency issues (TypeScript and Turbo):
      <pre><code>npm install typescript@^5.1.0 --save-dev
npm install turbo --save-dev</code></pre>
    </li>
    <li>Run the development server:
      <pre><code>npm run dev</code></pre>
    </li>
    <li>Open your browser and visit:<br />
      <a href="http://localhost:3000/event-types" target="_blank" rel="noopener noreferrer">http://localhost:3000/event-types</a><br />
      Confirm the translated text <strong>"Datum und Uhrzeit"</strong> appears correctly.
    </li>
  </ol>
</body>
</html>
