EasyLedger
EasyLedger is a lightweight, user-friendly web application designed for small business owners to track income and expenses with minimal tech experience. It supports voice commands, receipt scanning, offline functionality, and multilingual support, with visual summaries for financial insights.
Features

Voice Input: Record transactions using voice commands (e.g., "Record income 50 dollars for sales") via the Web Speech API.
Receipt Scanning: Upload receipt images to extract amount and date using Tesseract.js OCR.
Offline Functionality: Store transactions locally using localStorage, with periodic syncing to a mock backend.
Visual Summaries: View income, expenses, and profit/loss with bar charts powered by Chart.js.
Multilingual Support: Supports English, Spanish, and Swahili, configurable via i18next.
Payment Integration: Mock API for syncing transactions from mobile payment platforms (e.g., M-Pesa, PayPal).
Simple Interface: Intuitive design optimized for users with minimal tech experience.

Tech Stack

Frontend: React (via CDN), Tailwind CSS for styling.
Libraries:
Tesseract.js for OCR-based receipt scanning.
Chart.js for financial charts.
i18next for internationalization.
Web Speech API for voice input.


Storage: localStorage for offline data persistence.
Backend: Mock API for syncing and payment integration (extendable to real APIs).

Installation

Clone or Download:

Download the index.html file from the repository or copy the provided code.
Alternatively, clone the repository (if hosted):  git clone https://github.com/your-repo/easyledger.git




Serve the Application:

Place index.html in a directory.
Open it directly in a modern browser (Google Chrome recommended for Web Speech API support).
Optionally, serve it using a local server for better performance:npm install -g http-server
http-server .

Then navigate to http://localhost:8080 in your browser.


Dependencies:

No manual installation is required, as all dependencies (React, Tailwind CSS, Chart.js, Tesseract.js, i18next) are loaded via CDN.



Usage

Access the App:

Open index.html in a browser or access it via the local server.


Record Transactions:

Manual Entry: Enter the amount, description, and select income/expense, then click "Record Income" or "Record Expense."
Voice Input: Click "Record with Voice" and speak (e.g., "Record expense 20 dollars for supplies"). Supports English, Spanish, and Swahili.
Receipt Upload: Click "Upload Receipt" to upload an image; the app extracts amount and date automatically.
Payment Sync: Click "Sync Payments" to fetch mock transactions from payment platforms.


View Financial Summaries:

See total income, expenses, and profit/loss in the Summary section.
View a bar chart of monthly income and expenses.


Change Language:

Select English, Spanish, or Swahili from the language dropdown.


Sync Data:

Click "Sync Data" to simulate syncing transactions with a backend. Data is stored offline in localStorage when no internet is available.



Customization

Add Languages: Extend multilingual support by adding new translations to the i18next configuration in index.html. Example:
i18next.init({
  resources: {
    fr: {
      translation: {
        appTitle: "EasyLedger",
        recordIncome: "Enregistrer le revenu",
        // Add more translations
      },
    },
  },
});


Real Payment API: Replace the mockApi object with real API calls to platforms like M-Pesa or PayPal. Update the fetchPaymentTransactions function:
fetchPaymentTransactions: async () => {
  const response = await fetch("https://api.payment-platform.com/transactions");
  return response.json();
},


Improve OCR: Adjust Tesseract.js settings for better receipt scanning accuracy (e.g., specify languages or preprocess images).


Limitations

Voice Input: Requires an internet connection for Web Speech API in some browsers.
Receipt Scanning: Tesseract.js may struggle with low-quality images or complex receipt layouts.
Payment Integration: Currently uses a mock API; integration with real payment platforms requires additional setup.
Browser Compatibility: Best supported in Chrome due to Web Speech API limitations in other browsers.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/new-feature).
Commit changes (git commit -m 'Add new feature').
Push to the branch (git push origin feature/new-feature).
Open a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For support or inquiries, contact the project maintainer at [your-email@example.com] or open an issue on the repository.
