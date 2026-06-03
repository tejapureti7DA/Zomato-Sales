# Zomato-Sales
📊 Zomato Data Analysis Project
📝 Short Description
This data analytics project focuses on analyzing customer ordering behaviors, restaurant types, ratings, and spending patterns utilizing restaurant data. The analysis evaluates metrics such as dining preferences, vote distributions, approximate costs for couples, and how online vs. offline ordering structures impact average customer ratings.
🛠️ Tech Stack
Language: Python
Data Manipulation: Pandas, NumPy
Data Visualization: Matplotlib, Seaborn
Environment: Jupyter Notebook / Anaconda
🔬 Technical Deep-Dive & Execution Steps
Step 1: Environment & Dependency Management
The project initializes by checking and satisfying local system dependencies
Core installations include data processing engines (numpy, pandas) and structural plotting frameworks (matplotlib, seaborn) to prepare the notebook workspace.
Step 2: DataFrame Ingestion & Structural Inspection
The raw data is loaded into memory using pd.read_csv("zomato_data.csv")
Initial health checks are run using df.head(), df.columns.tolist(), and df.info(), which reveal a dataset containing 148 row entries and 7 working columns with zero null fields.
Step 3: Custom Data Preprocessing Pipeline (DAX/Python-Equivalent logic)
The raw rate column contains string object values formatted with text denominators (e.g., "4.1/5")
A custom python function handleRate(value) is declared to dynamically split the string at the / character, extract the leading index (value[0]), and cast it into a floating-point number (float64)
Step 4: Comprehensive Analytical Explorations & InsightsMarket Share Profiling: Using a Seaborn categorical count-plot, the project visually establishes that "Dining" is the most frequent restaurant classification in the market, while "Buffet" holds the lowest market share count. Customer Engagement Mapping: The script groups the data by category type using df.groupby('listed_in(type)')['votes'].sum(), showing that Dining dominates community engagement with a massive 20,363 aggregate votes, while Buffet ranks lowest at 3,028 votes.Consumer Pricing Index: A target analysis on approx_cost(for two people) reveals that a significant majority of dining couples select restaurants with an approximate cost of 300 Rupees, marking it as the ideal sweet spot for consumer market pricing.  Channel Efficiency via Distribution Outliers: A comparative boxplot contrasts consumer ratings across order methods. It shows that "Online Orders" earn higher median scores and tighter distribution boundaries, whereas "Offline Orders" suffer from wider variances and drop to the lowest rating outliers (down to a 2.6 rating minimum).B2B Strategic Heatmapping: A custom two-way contingency table (pivot_table) cross-references order methods against restaurant types. Annotated with Seaborn (sns.heatmap(pivot_table, annot=True, cmap='YlGnBu')), it exposes that Dining establishments running offline ordering have the heaviest market cluster (77 distinct locations), giving Zomato data-backed proof to target these specific businesses with specialized online onboarding campaigns 
