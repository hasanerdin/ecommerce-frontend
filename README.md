📊 E-Commerce Price Tracker – Frontend

This repository contains the frontend dashboard of the E-Commerce Price & Discount Tracker project.
The application is built with Streamlit and visualizes historical product prices, discount periods, and event impacts by consuming a REST API.

The frontend is fully decoupled from the backend and communicates only via HTTP requests.

🎯 Purpose

The goal of this frontend is to provide:

- Clear and interactive visualizations of product price history
- Easy comparison of prices across time ranges
- Visibility into discount events and their impact on prices

This dashboard helps users understand pricing behavior over time rather than just seeing raw numbers.

🧩 Features

📦 Product Overview
- List all available products
- Display base price and summary statistics (min / max / avg)

📈 Price History
- Interactive time-series chart
- Hoverable price points
- Highlighted discount and campaign periods

🎯 Event Impact
- Analyze how events affect prices
- Compare pre-event, event, and post-event price levels

🏗️ Architecture
```
FastAPI Backend (Railway)
        ↓ REST API
Streamlit Frontend (Streamlit Cloud)
```

- The frontend does not connect directly to the database
- All data is fetched from the backend API
- This separation improves scalability, security, and maintainability

🗂️ Project Structure
```
frontend/
├── app.py                  # Main Streamlit entry point
├── pages/
│   ├── 1_Product_Overview.py
│   ├── 2_Price_History.py
│   └── 3_Event_Impact.py
├── services/
│   └── api_client.py       # Backend API communication
├── __init__.py
├── pyproject.toml
└── README.md
```

⚙️ Configuration

The frontend requires the backend API URL.

Environment Variable
```
API_BASE_URL=https://your-backend.up.railway.app
```

Local Development (optional)

If the variable is not set, the app defaults to:
```
http://localhost:8000
```

▶️ Running Locally
```
bash scripts/setup.sh
streamlit run frontend/app.py
```

Make sure the backend API is running before starting the frontend.

☁️ Deployment (Streamlit Cloud)

1. Push this repository to GitHub
2. Create a new app on Streamlit Cloud
3. Select frontend/app.py as the entry point
4. Add the following secret:
```
API_BASE_URL = https://your-backend.up.railway.app
```
5. Deploy 🚀

🛠️ Technologies Used
- Python 3.10+
- Streamlit
- Plotly
- Pandas
- Requests
- REST APIs

🚀 Future Improvements
- Price comparison between multiple products
- Downloadable CSV exports
- Event-based filtering on charts
- User-defined alerts for price drops

👤 Author

Hasan Erdin

GitHub: https://github.com/hasanerdin

LinkedIn: https://www.linkedin.com/in/hasanerdin