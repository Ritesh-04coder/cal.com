
🔧 Fix: Incorrect German Translation for "Date and Time"
📝 Summary
This change fixes an incorrect translation in the German locale file for Cal.com. The string for "bookingDateTime" was either missing or incorrectly translated. It has now been properly added to reflect "Datum und Uhrzeit" in the de/common.json file.

Additionally, the end-to-end test file locale.e2e.ts has been updated to verify this translation is correctly displayed on the /event-types page.

🛠️ Changes Made
✅ Updated German locale file:
apps/web/public/static/locales/de/common.json

json
Copy
Edit
{
  ...
  "bookingDateTime": "Datum und Uhrzeit"
}
✅ Modified locale test:
apps/web/tests/e2e/locale.e2e.ts

ts
Copy
Edit
await test.step("should navigate to /event-types and show Uhr translations", async () => {
  await page.goto("/event-types");
  // other assertions to verify translation presence
});
✅ Testing the Fix
Verified the translation is rendered correctly on the UI.

Ran locale.e2e.ts to ensure automated tests pass for the German locale.

🧪 How to Test It Locally
Make sure dependencies are installed:

bash
Copy
Edit
npm install
Fix dependency issues (TypeScript and Turbo):

bash
Copy
Edit
npm install typescript@^5.1.0 --save-dev
npm install turbo --save-dev
Run the development server:

bash
Copy
Edit
npm run dev
Visit http://localhost:3000/event-types and ensure the translated text "Datum und Uhrzeit" appears as expected.
