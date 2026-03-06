# 🧾 Pro Invoice Generator

A lightweight, professional, and serverless Automated Invoice Generator built with React, Tailwind CSS, and Firebase.

This application runs entirely in the browser using CDN links, meaning no build tools or npm install are required. It utilizes advanced CSS @media print rules to generate crisp, text-searchable PDFs directly from the DOM, avoiding the blurry text often caused by third-party PDF canvas libraries.

✨ Features

Real-time Live Preview: See exactly what your PDF will look like as you type.

Native PDF Generation: Uses the browser's native print engine for perfect, high-resolution PDFs.

Cloud Sync & History: Save, update, and manage your past invoices using Firebase Firestore.

Custom Branding: Upload your company logo (saved as base64) and pick a custom accent color.

Multi-Currency Support: Instantly switch between USD, EUR, GBP, PHP, JPY, and AUD.

Smart Calculations: Automatically calculates line-item totals, subtotals, percentage-based discounts, and taxes.

Fully Responsive: A modern dashboard UI that works beautifully on desktop and mobile.

🛠️ Tech Stack

Frontend Framework: React 18 (via CDN)

Styling: Tailwind CSS (via CDN)

Database & Auth: Firebase Firestore & Firebase Anonymous Authentication

PDF Engine: Native Browser Print (window.print() + Print Stylesheets)

🚀 Getting Started

Because this project uses CDNs, getting it running locally is incredibly simple.

1. Clone the repository

git clone [https://github.com/yourusername/automated-invoice-generator.git](https://github.com/yourusername/automated-invoice-generator.git)
cd automated-invoice-generator


2. Open the app

Simply double-click the index.html file to open it in your web browser. The app will work perfectly for creating and printing PDFs right out of the box!

3. Enable Cloud Saving (Firebase Setup)

To enable the "Save to Cloud" and "History" features, you need to connect the app to your own free Firebase project:

Go to the Firebase Console and create a new project.

Add a Web App to your project to get your configuration keys.

Enable Firestore Database (Start in Test Mode).

Enable Anonymous Authentication (Under Build > Authentication > Sign-in method).

Open index.html in your code editor and locate the localFirebaseConfig object (around line 58).

Replace the placeholder strings with your actual Firebase keys:

const localFirebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.appspot.com",
    messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
    appId: "YOUR_APP_ID"
};


Save the file and refresh your browser. Your cloud saving is now fully operational!

💡 How the PDF Generation Works

Instead of relying on heavy server-side rendering or canvas-to-image libraries, this app uses CSS @media print. When the user clicks "Export PDF", it triggers window.print(). The CSS intercepts this, hides the editor controls (display: none), and stretches the live preview to take up exactly one US Letter / A4 page size without margins.

📝 License

This project is open-source and available under the MIT License.
