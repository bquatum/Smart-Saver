System Architecture.md – The technical blueprint for your product.

---------------------------------Overview-------------------------------------------------------

Smart Saver connects prepaid electricity meters to a mobile app, allowing users to track usage, predict consumption, and recharge automatically.

It works as a bridge between three main systems:
The user app (mobile frontend).
The application server (backend).
The meter data and payment systems (external APIs).

This structure makes the solution reliable, scalable and easy to integrate with electricity providers.

https://drive.google.com/file/d/1H_foDABJ4GWgVZeVQaqtbsy21KnCYU6s/view?usp=sharing



 ------------------------------------System Components------------------------------

 Frontend:  (User Interface)
Technology: Flutter
Purpose: Cross platform mobile app for Android and iOS.
Responsibilities:
	•	Displays power usage, balance and spending trends.
	•	Provides notifications and alerts.
	•	Lets users top up units directly through the app.
	•	Syncs user data with backend APIs.

Modules:
	•	Dashboard Screen – Real time power usage visualization.
	•	Top Up Screen – Recharge options via wallet, mobile bank app, card, or USSD.
	•	Budget Planner – Set and track energy goals.
	•	Alert Manager – Push notifications for low balance or spikes.

Backend: (Application Server)
Technology: Node.js + Express.js
Purpose: This is the main hub that connects the app, database and external systems.
Responsibilities:
	•	Handle API requests from the app.
	•	Communicate securely with prepaid meter APIs.
	•	Manage user authentication and session tokens.
	•	Trigger notifications and auto top up workflows.
	•	Process and log all transactions.

--------------------------Database Layer------------------------------------

Technology : Firebase (Cloud Firestore) or MongoDB Atlas
Data Stored:
	•	User Profiles: ID, phone, meter number, payment details.
	•	Meter Data: Usage logs, current balance, timestamps.
	•	Transactions: Recharge history and top up receipts.
	•	Notifications: Scheduled alerts and reminders.


------------------------------------Integration Points------------------------------------

Meter Data API: This is our connection to smart prepaid meters and vendor systems, like the IkEDC APIs. It helps us grab live readings from the meters and send updates back to our backend, ensuring everything stays in sync.

Payment Gateway: Integrated with Paystack or Flutterwave to enable secure, seamless top ups and wallet transactions.

Notification Service: Our notification service keeps you in the loop with push alerts through Firebase Cloud Messaging (FCM) or OneSignal. You’ll get real time warnings, like low Power Unit.

------------------------------Technical Feasibility------------------------------------

Smart Saver is technically possible because it relies on existing, proven technologies already common in Nigeria and similar markets:

	•	Prepaid meter APIs for real time data.
	•	Mobile banking and fintech APIs for payments.
	•	Flutter and Node.js ecosystem for scalable apps and backend.

Each layer works independently, making the product easy to maintain and upgrade over time.
It’s modular, cloud-hosted and secure and perfectly suited for continuous improvement.






