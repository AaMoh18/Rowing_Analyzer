# Rowing Performance Analyzer Dashboard

Visualize rowing performance trends, analyze splits, and track personal records.

A powerful, single-file web application designed specifically for rowing athletes. Say goodbye to manual spreadsheet calculations! This tool instantly takes your raw training log (CSV) and transforms it into actionable analytics and interactive charts right in your browser.

[Link to Live Demo](https://rowing-analyse.netlify.app/)

## Core Features

* Instant Analysis: Upload your CSV file and see all your stats update immediately, with no server-side processing required.

* Automatic Data Sourcing: The app is designed to load your default rowing_log.csv file automatically when deployed (e.g., on Netlify), offering a seamless experience without needing a manual upload on every visit.

* Smart Athlete Grouping: Analyze your data regardless of naming consistency. The tool intelligently groups variations like "Peter" and "Peter Parker" for a single, consolidated performance view.

* Performance Insights:

* **Personal Records (PRs):** Instantly highlights your fastest 500m split and best total times for 1000m and 2000m.

* **Performance Change (%):** Displays the percentage change in your 500m split from your very first session to your most recent one—a true measure of long-term progress.

## Interactive Visualizations (Powered by Chart.js)

* Intra-day Session Trend: Tracks how your 500m pace degrades (or holds up!) across multiple sets within a single day. Each line is a separate training date.

* Daily Improvement Trend: View your long-term consistency by plotting the overall daily average 500m pace over months. Faster times appear higher on the chart.

* Volume Bar Chart: A clean bar chart showing the total distance (training volume) you covered on each date.

## Setup and Deployment Guide

The entire application is contained within the index.html file.

### 1. Data Requirements

Your data file must contain the following column headers. The parser will automatically handle common separators (comma, tab, semicolon).

Column Name	Format	Example
Name	Text	Peter Parker
Date	YYYY-MM-DD	2025-08-04
Distance	Integer (meters)	500
Time	MM:SS 	1:46 or 01:46
Time in 500m(500*(distance/time)	MM:SS	1:46 or 01:46


<img width="646" height="175" alt="image" src="https://github.com/user-attachments/assets/5e180b31-a571-4c28-b37b-490f3ce61f10" />


### 2. Netlify Deployment (Live Site)

For an out-of-the-box experience, follow these steps:

GitHub Setup: Create a new repository and commit your index.html file.

Default Data: Commit your training log file, named rowing_log.csv, to the root of the repository.

Deploy: Link your repository to Netlify. Netlify will serve the files, and the dashboard will load the data automatically on launch.

### 3. Local Testing (For Developers)

Since web browsers block the automatic loading of local files (due to the file:// security protocol), you must use a simple server for local testing:

Open your terminal and navigate to the folder containing index.html and rowing_log.csv.

Run the Python simple server:

python -m http.server 8000

View your project at: http://localhost:8000/.
