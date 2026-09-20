# Automate Financial Data Extraction from Banxico into Google Sheets

Real-time data streaming for your financial model — automate the retrieval of economic and financial time series from Banco de México (Banxico) directly into Google Sheets using Google Apps Script.

## 📄 About This Project

This repository contains the JavaScript code referenced in the Medium article:

**[Automate Financial Data Extraction from Banxico into Google Sheets](https://chomchom216.medium.com/automate-financial-data-extraction-from-banxico-into-google-sheets-d04a44e19eba)**

The article explains, step by step, how to connect to the Banxico SIE API (Sistema de Información Económica), retrieve financial time series, and automatically populate a Google Sheets spreadsheet. This repository provides ready-to-use scripts for over a dozen key financial indicators, so you can implement the solution immediately.

## 📁 Repository Contents

All scripts are located in the folder [`JavaScript code to fetch data`](https://github.com/robert0777/Automate-Financial-Data-Extraction-from-Banxico-into-Google-Sheets/tree/main/JavaScript%20code%20to%20fetch%20data).

Each `.txt` file contains a complete Google Apps Script function ready to be copied into your Apps Script project. The following data series are included:

| Script File | Data Series | Description |
|-------------|-------------|-------------|
| `Banxico API_Fetching CETES 28 Data.txt` | CETES 28-day | 28-day Mexican Treasury Certificates rate |
| `Banxico API_Fetching CETES 91 Data.txt` | CETES 91-day | 91-day Mexican Treasury Certificates rate |
| `Banxico API_Fetching CETES 182 Data.txt` | CETES 182-day | 182-day Mexican Treasury Certificates rate |
| `Banxico API_Fetching CETES 28 Weekly Auction Data.txt` | CETES 28 Weekly Auction | Weekly auction results for 28-day CETES |
| `Banxico API_Fetching TIIE 28 Data.txt` | TIIE 28-day | Equilibrium Interbank Interest Rate |
| `Banxico API_Fetching TIIP 28 Data.txt` | TIIP 28-day | Interbank Interest Rate for TIIP |
| `Banxico API_Fetching CPP Data.txt` | CPP | Average Percentage Cost Rate |
| `Banxico API_Fetching INPC Data.txt` | INPC | National Consumer Price Index |
| `Banxico API_Fetching Exchange Rate MXN_USD Daily FIX Data.txt` | MXN/USD Daily FIX | Daily exchange rate (FIX) |
| `Banxico API_Fetching Exchange Rate MXN_USD Monthly Average Data.txt` | MXN/USD Monthly Avg | Monthly average exchange rate |
| `Banxico API_Fetching UDIS Data.txt` | UDIS | Daily Investment Unit value |
| `Banxico API_Fetching UDIBONOS 3-Years Data.txt` | UDIBONOS 3-Year | 3-year UDIBONOS rate |
| `Banxico API_Fetching BONDES 3-Years Data.txt` | BONDES 3-Year | 3-year BONDES rate |
| `Banxico API_Fetching IPC BMV Data.txt` | IPC BMV | Mexican Stock Exchange index |
| `Banxico API_Fetching PIB Nominal Value Quarterly Data.txt` | PIB Nominal | Quarterly nominal GDP |
| `Banxico API_Fetching Salario Mínimo Daily MXN Data.txt` | Minimum Wage | Daily minimum wage in MXN |
| `Banxico API_Fetching PRLV Data.txt` | PRLV | PRLV series |
| `Banxico API_Fetching Tasa Crédito a los Hogares Data.txt` | Household Credit Rate | Interest rate for household credit |
| `Import All Data Banxico.txt` | **All series** | Master script that fetches all the above series in one execution |

## 🚀 Getting Started

### Prerequisites

1. A **Google Account** with access to Google Sheets.
2. A **Banxico SIE API token**. You can obtain one for free here: [Banxico API Token](https://www.banxico.org.mx/SieAPIRest/service/v1/token)
3. Basic familiarity with **Google Apps Script** (the article covers this).

### Installation & Usage

1. **Open your Google Sheets** spreadsheet.
2. Go to **Extensions → Apps Script**.
3. **Copy the content** of one of the `.txt` files from this repository into the Apps Script editor (or use `Import All Data Banxico.txt` for all series).
4. **Replace the token** in the script with your own Banxico API token (the scripts include a placeholder token that you must renew).
5. **Run the function** (e.g., `importCETES28Data`) from the Apps Script editor.
6. The script will create a new sheet in your spreadsheet with the downloaded data.

> **Note:** The API token in the scripts is a placeholder. You must replace it with your own token to avoid errors. Tokens may expire over time — renew as needed.

### Scheduling Automatic Refreshes

You can set a **time-driven trigger** in Apps Script to run the import function automatically (e.g., daily or weekly):

1. In the Apps Script editor, click the **Triggers** icon (clock icon) on the left panel.
2. Click **Add Trigger**.
3. Select your import function, choose **Time-driven**, and set the desired frequency.

### Custom Menu (Optional)

The scripts include an optional `onOpen()` function (commented out) that creates a custom menu in your Google Sheets. Uncomment it to add a "Banxico Data" menu with buttons to run the imports manually.

## 🔗 Related Article

This repository is the companion code for the Medium article:

**[Automate Financial Data Extraction from Banxico into Google Sheets](https://chomchom216.medium.com/automate-financial-data-extraction-from-banxico-into-google-sheets-d04a44e19eba)**

The article provides:
- A conceptual introduction to APIs and the Banxico SIE API.
- Step-by-step instructions to obtain an API token.
- Detailed explanation of the JavaScript code.
- Instructions for scheduling automatic refreshes and customizing the model.

## ⚠️ Important Notes

- **API Token:** Each script contains a hardcoded token placeholder. You must replace it with your own token. If the code fails, renew your token and try again.
- **Series IDs:** Each script uses a specific `Id Serie` (e.g., `SF282` for CETES 28-day). If you want to fetch a different series, look up its ID in the [Banxico SIE API Catalog](https://www.banxico.org.mx/SieAPIRest/service/v1/doc/catalogoSeries) and update the script accordingly.
- **Data Formatting:** The scripts convert values to decimals (dividing by 100) for percentage formatting. You may need to adjust this depending on the data series and your model's requirements.
- **Terms of Use:** Respect Banxico's terms of service and API usage limits.

## 👤 Author

**Dr. Robert Hernández Martínez**  
*Consultant in Actuarial Science, Finance, Risk Modeling, and Applied AI*

* 📝 [Articles on Medium](https://chomchom216.medium.com/)
* 🎓 [Academic Publications](https://unam1.academia.edu/Robert_Hernandez_Martinez)
* 🏆 [Credentials on Credly](https://www.credly.com/users/robert-hernandez.89bffe7b)
* 🐙 [GitHub Profile](https://github.com/robert0777)
* 📧 Email: [robert@actuariayfinanzas.net](mailto:robert@actuariayfinanzas.net)
