# personal-finance-app

Personal Finance Tracker
A simple web application for tracking personal finances built with Next.js, React, and MongoDB.

Features
Add/Edit/Delete Transactions: Manage your financial transactions with amount, date, and description
Transaction List View: View all your transactions in a clean, organized list
Monthly Expenses Chart: Visual representation of your monthly income, expenses, and net balance
Current Balance Display: Real-time calculation of your total balance
Form Validation: Comprehensive validation for all transaction inputs
Responsive Design: Works seamlessly on desktop and mobile devices
Error Handling: Graceful error handling with user-friendly messages
Tech Stack
Frontend: Next.js, React, Plain CSS
Backend: Next.js API Routes
Database: MongoDB Atlas
Charts: Recharts
Language: JavaScript (No TypeScript)
Project Structure
├── components/
│   ├── TransactionForm.js    # Form component for adding/editing transactions
│   ├── TransactionList.js    # List component for displaying transactions
│   └── ExpenseChart.js       # Chart component for monthly expense visualization
├── lib/
│   └── mongodb.js           # MongoDB connection configuration
├── pages/
│   ├── api/
│   │   └── transactions.js  # API routes for transaction CRUD operations
│   ├── _app.js             # Next.js app configuration
│   └── index.js            # Main page component
├── styles/
│   └── globals.css         # Global styles (Plain CSS, no Tailwind)
├── .env.example            # Environment variables example
├── next.config.js          # Next.js configuration
├── package.json            # Project dependencies
└── README.md              # Project documentation
Getting Started
Prerequisites
Node.js (version 14 or higher)
MongoDB Atlas account
npm or yarn
Installation
Clone the repository or create a new project with the provided files
Install dependencies:
bash
npm install
Set up environment variables:
bash
cp .env.example .env.local
Update the .env.local file with your MongoDB credentials:
MONGODB_URI=mongodb+srv://aasthaparihar:<your_password>@cluster0.lo4osnq.mongodb.net/financeDB?retryWrites=true&w=majority&appName=Cluster0
Replace <your_password> with your actual MongoDB password
Start the development server:
bash
npm run dev
Open http://localhost:3000 in your browser
Database Setup
The application uses MongoDB Atlas with the following configuration:

Database: financeDB
Collection: transactions
Connection string provided in the MongoDB configuration
The transactions collection will store documents with the following structure:

javascript
{
  _id: ObjectId,
  amount: Number,        // Positive for income, negative for expenses
  date: Date,
  description: String,
  createdAt: Date,
  updatedAt: Date        // Only present for updated transactions
}
API Endpoints
GET /api/transactions
Fetches all transactions sorted by date (newest first)
Returns: Array of transaction objects
POST /api/transactions
Creates a new transaction
Body: { amount, date, description }
Returns: Created transaction object
PUT /api/transactions
Updates an existing transaction
Body: { id, amount, date, description }
Returns: Updated transaction object
DELETE /api/transactions
Deletes a transaction
Body: { id }
Returns: Success message
Form Validation
The application includes comprehensive form validation:

Amount: Must be a valid number (cannot be zero)
Date: Must be a valid date
Description: Required, minimum 3 characters
Features in Detail
Transaction Management
Add new transactions with positive amounts for income and negative for expenses
Edit existing transactions with pre-populated form data
Delete transactions with confirmation dialog
Real-time balance calculation
Data Visualization
Monthly expense chart showing income, expenses, and net balance
Responsive chart that adapts to different screen sizes
Custom tooltip displaying formatted currency values
User Interface
Clean, modern design with intuitive navigation
Responsive layout that works on all devices
Loading states and error handling
Success messages for user feedback
Error Handling
The application includes robust error handling:

Client-side validation for form inputs
Server-side validation for API requests
Database connection error handling
User-friendly error messages
Loading states during API calls
Deployment
To deploy this application:

Build the project:
bash
npm run build
Start the production server:
bash
npm start
Deploy to your preferred hosting platform (Vercel, Netlify, etc.)
Contributing
Fork the repository
Create a feature branch
Make your changes
Test thoroughly
Submit a pull request
License
This project is open source and available under the MIT License.

