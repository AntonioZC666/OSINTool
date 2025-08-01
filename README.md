# 🔬 OSIN

📘 This README is available in [English](README.md) | [中文](README.zh-CN.md)

## 📖 Project Overview

**OSINTool** is an automated web crawling client designed for efficient data collection and management in Open Source Intelligence (OSINT) tasks. The system adopts a clean separation between frontend and backend, built using **Electron** for the desktop client and **Flask** for the backend server.

This architecture allows users to interact with a user-friendly, cross-platform desktop interface while leveraging the power of Python-based asynchronous scraping and scheduling on the backend. OSINTool is capable of managing multiple crawling tasks, parsing various formats (HTML, CSV, TXT), scheduling periodic scraping jobs, and storing results locally using a lightweight database.

Whether you're performing data aggregation, content monitoring, or open-source investigations, OSINTool provides a modular, extensible foundation for automating repetitive web data collection workflows.

## 🚀 Quick Start

### Install Dependencies

Install **frontend dependencies** in the `frontend` directory:

```bash
npm install
```

Install **backend dependencies** in the project root directory:

```bash
pip install flask flask-cors flask[async] tinydb shortuuid requests lxml pandas aiofiles aiohttp apscheduler playwright
playwright install
```

### Launch Backend and Frontend

Start the **Flask backend** in the project **root directory**:

```bash
python app.py
```

Start the **Electron client** in the `frontend` directory:


```bash
npm start
```

> Please ensure that the browsers and drivers required by Playwright are installed. Use the command `playwright install` if needed.



## 🧱 Tech Stack

Built on a **frontend-backend separated** architecture using **Electron** for a native desktop client.

### Frontend

- Page development: HTML / CSS / JavaScript
- Desktop application: Electron
- UI library: ElementUI

### Backend

- Local server: Flask
- Web scraping: Playwright, Requests
- Scheduled tasks: APScheduler
- Database: TinyDB



## 📁 Project Structure

```
├── frontend
│   ├── edit.html 	 		# Edit page
│   ├── index.html  	    # List page
│   ├── main.js 			# Electron main process
│   ├── package.json
│   ├── preload.js  		# Preload script (includes API)
├── utils
│   ├── parsers  			# Parsers
│   │   ├── base.py
│   │   ├── csv_parser.py
│   │   ├── html_parser.py
│   │   └── txt_parser.py
│   ├── common.py  			# common functions
│   ├── logger.py  			# log module
│   ├── parser_factory.py  	# Parsers Factory
├── app.py  				# Flask application entry point
├── db.json  				# TinyDB database
```



## 📊 Parser Flowcharts

### TXTParser

![TXTParser](.\img\TXTParser.png)

### CSVParser

![CSVParser](.\img\CSVParser.png)

### HTMLParser

![HTMLParser](.\img\HTMLParser.png)

## 🖼️ UI Previews

### Task List Page （index.html）

![Index](.\img\Index.png)

### Task Edit Page（edit.html）

![Edit](.\img\Edit.png)



## ✅ Todo

- Support for CSV output
- Handle OCR / slider CAPTCHAs and other human-verification mechanisms
- CI/CD pipeline integration
- Support for web-based deployment



## 🧠 SWOT Analysis

- **Strengths**：Supports multiple data formats, highly customizable (e.g., login, pagination), and features flexible task scheduling.
- **Weaknesses**：Steep learning curve; requires knowledge of web structure and regular expressions. Limited visual interface; currently lacks support for anti-bot challenges like CAPTCHAs.
- **Opportunities**：Potential to integrate AI for intelligent crawling and support export to analysis tools like Excel.
- **Threats**：Existing competitors like Octoparse and EasySpider offer mature visual interfaces. Web anti-crawling technologies evolve quickly, requiring ongoing maintenance.



## 🔗 References

- [Octoparse](https://www.bazhuayu.com/)
- [EasySpider](https://www.easyspider.net/)