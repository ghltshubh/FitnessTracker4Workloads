# fitbit4workloads

**Description:** Summit is an important tool for the scientific community. Whether it’s drug discovery for COVID-19 or material research for next generation aircraft it has increased the pace of research many folds because of its ability to crunch numbers at an exponential rate compared to any other machine in the world. Therefore like any other machine or tool  it is imperative to monitor its performance to know how optimally it is being utilized. In its case we can gather insights in terms of its workloads by mining and analyzing Darshan I/O activity logs and RATS-CRM that stores and organizes data pertaining to users, projects, allocations, etc. We propose a system which can continuously mine and analyze the utilization based on various parameters from the data combined from both sources and visualize them to present insights. The vision of the project is to build a Fitbit of sorts that gives near real time information for workloads on summit. The version 1.0 provides project wise I/O insights though it can be scaled up to gather any type of insights based on the type of data that is collected. Current beta version of the project is live.

**System Overview:** The system comprises of following components: 

1. Backend:
    1. Data collection: Data is collected from two sources: Darshan I/O logs and RATS-CRM. I/O data is collected by parsing Darshan logs using custom bash scripts that search for unique key works in job logs. Project details are collected using RATS-CRM API.
    2. Data collation: Both datasets are combined in a table using python scripts for the analysis. The data pipeline can be easily automated to make the process of data collection and collation seamless. 
    3. Analysis: Data is analyzed in python using standard libraries like numpy, pandas, matplotlib and bokeh.
2. Frontend:
    1. Data visualization: Interactive data visualizations are created using python bokeh library. Currently total read / write  (STDIO and POSIX) data for each project is being visualized.
    2. Serve Visualization: Bokeh library is used to host and serve these  visualizations as well.


