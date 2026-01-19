PROJECT: Do "Infrastructure" positions provide better risk-adjusted returns than "Skill" positions in the NFL Draft?
NAME: Tom Horwood
DATE: January 19, 2026
MODULE: M3. Business Intelligence & Storytelling in Sports

1. PROJECT OVERVIEW
-------------------
For this assignment, I wanted to test whether NFL teams are overvaluing "Skill" positions (QB, WR, RB) compared to "Infrastructure" positions (OL, TE) in the early rounds of the draft. 

My hypothesis is that Infrastructure players act as stable assets; they might not have the natural appeal of a QB, for example, but they offer similar long-term value with significantly less risk of busting.

I built a Python dashboard ("Draft OS") to visualize this volatility gap using data from the 2011-2021 draft classes.

2. WHAT IS IN THIS FOLDER?
-------------------
- M3.TaskTomHwAV.pdf: The final executive summary and my strategic recommendations.
- M3TomHDashOSFinal.py: The Python script that runs the dashboard.
- requirements.txt: The list of libraries you need to install.
- processed_nfl_draft_data.csv: A backup copy of the data (just in case the live download fails).
- exported_charts [Folder]: Static images of all the charts from the dashboard.

3. HOW TO SET UP
-------------------
To run this, you need Python installed on your machine. I built and tested this using Python 3.12

Recommended Tools:
- If you use an IDE like PyCharm or VS Code then just open this folder as a project, open the terminal inside the IDE, and you are good to go.
- If you are using a standard Terminal/Command Prompt: Navigate to this folder using the 'cd' command.

Installation:

Copy and paste this specific command to install the libraries directly:
   pip install pandas plotly dash dash-bootstrap-components nfl_data_py kaleido

4. HOW TO RUN THE DASHBOARD
-------------------
Once the libraries are installed:

1. Run the script by typing:
   python M3TomHDashOSFinal.py

2. Wait a few seconds. You should see a message saying "Dash is running on http://127.0.0.1:8050/"
3. Copy and paste that link into your web browser (Chrome works best).

5. DASHBOARD GUIDE
-------------------
The app has three tabs that follow the narrative of my PDF report:

- Tab 1 (Market Inefficiency): Shows how teams currently spend draft capital and highlights the massive volatility difference between Skill players and Linemen.
- Tab 2 (The Risk Reality): Digs into the Floor of these players. Look for the Sankey diagram; it shows how many Skill players drop out of the league compared to Infrastructure players.
- Tab 3 (The Arbitrage Fix): Recommendations. It includes an Asset Explorer where you can hover over individual players to see who hit and who busted historically.

6. TROUBLESHOOTING
-------------------
I tested this code to run locally, but sometimes firewalls or library versions can cause issues. 

- If the API fails to download data: The code is set up to automatically look for the "processed_nfl_draft_data.csv" file included in this folder as a backup.
- If the app won't launch: I have exported all the visualizations as high-res images in the "exported_charts" folder so you can still see the analysis results without running the code.

7. DATA & METRICS
-------------------
Data Source: Pro-Football-Reference (accessed via the nfl_data_py library).

Key Metric: wAV (Weighted Career Approximate Value). 
- Overview: Unlike standard "Career AV" which simply adds up every season equally, wAV puts a heavy weight on a player's peak performance (100% of their best season, 95% of their second best, etc.).
- Why I used it: This distinguishes true impact players from compilers (players who remain on rosters for a long time without being great). It gives us a better measure of who actually impacted winning during their prime.
