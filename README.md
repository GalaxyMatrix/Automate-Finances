# Automate-Finances

A Streamlit-based personal finance management application that helps you categorize and analyze your bank transactions automatically.

## Features

🏦 **CSV Bank Statement Upload** - Import your bank statements in CSV format  
📊 **Automatic Transaction Categorization** - Smart categorization based on merchant names  
✏️ **Manual Category Assignment** - Interactive data editor for manual categorization  
💾 **Persistent Category Storage** - Categories and keywords saved in JSON format  
📈 **Expense Analysis** - Separate tabs for expenses (debits) and income (credits)  
🔄 **Real-time Updates** - Changes are saved automatically to your category database  

## Installation

1. Clone this repository:
```bash
git clone https://github.com/GalaxyMatrix/Automate-Finances.git
cd Automate-Finances
```

2. Install required dependencies:
```bash
pip install streamlit pandas plotly
```

## Usage

1. Start the Streamlit application:
```bash
streamlit run main.py
```

2. Open your browser and navigate to `http://localhost:8501`

3. Upload your bank statement CSV file with the following columns:
   - `Date` - Transaction date
   - `Details` - Transaction description/merchant name
   - `Amount` - Transaction amount
   - `Currency` - Currency code (e.g., ZAR, USD)
   - `Debit/Credit` - Transaction type
   - `Status` - Transaction status

## CSV Format Example

```csv
Date,Details,Amount,Currency,Debit/Credit,Status
28 Feb 2025,LULU HYPERMARKET,455.00,ZAR,Debit,SETTLED
28 Feb 2025,Card Payment Received,18551.62,ZAR,Credit,SETTLED
15 Feb 2025,NETFLIX.COM,57.55,ZAR,Debit,SETTLED
```

## How It Works

### Automatic Categorization
The app automatically categorizes transactions based on merchant names stored in `categories.json`. When you manually assign a category to a transaction, the merchant name is automatically added to that category's keyword list for future automatic categorization.

### Category Management
- **Add New Categories**: Use the text input to create new expense categories
- **Manual Assignment**: Use the data editor to manually assign categories to transactions
- **Automatic Learning**: The app learns from your manual assignments and improves automatic categorization

### Data Persistence
- Categories and their associated keywords are stored in `categories.json`
- The system remembers your preferences across sessions
- No data is sent to external servers - everything runs locally

## File Structure

```
Automate-Finances/
│
├── main.py                 # Main Streamlit application
├── categories.json         # Category storage (auto-generated)
├── sample_bank_statement.csv # Sample data for testing
└── README.md              # This documentation
```

## Features in Detail

### Expenses Tab (Debits)
- View all outgoing transactions
- Categorize expenses manually or automatically
- Add new expense categories on-the-fly
- Real-time category assignment with keyword learning

### Income Tab (Credits)
- View all incoming transactions
- Track income sources and payments received

### Smart Categorization Engine
The app uses a keyword-based matching system:
1. Transaction details are matched against stored keywords
2. Manual categorization adds new keywords automatically
3. Case-insensitive matching for reliability
4. Continuous learning from user input

## Supported Banks

The app works with any bank that exports CSV files with the standard format. Tested with:
- ADCB (Abu Dhabi Commercial Bank)
- Standard Bank South Africa
- Most major banks with CSV export functionality

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-feature`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature/new-feature`)
5. Create a Pull Request



## Support

If you encounter any issues or have suggestions for improvements, please open an issue on GitHub.

## Future Enhancements

- 📊 Advanced analytics and spending trends
- 📱 Mobile-responsive design
- 🔐 Encrypted data storage
- 📤 Export categorized data
- 🎯 Budget tracking and alerts
- 📈 Financial goal setting
