Zeru Finance Credit Scoring Model

Overview
This project builds a machine learning model that assigns a credit score between 0 and 100 to each wallet using transaction data from the Compound V2 protocol. The credit score reflects the behavioral quality of a wallet interacting with DeFi protocols.

Dataset
- Data Source: Compound V2 transaction logs
- Files Used: The 3 largest JSON files
- Processed file: compound_combined.csv (stored in data folder)

Steps Followed

1. Data Preprocessing
Loaded and flattened raw JSON files, normalized nested structures, handled missing values, and converted amounts to float. Combined and cleaned data to prepare for feature extraction.saved the same file as final_wallet_features.csv.

2. Feature Engineering
Extracted the following simplified wallet-level features:
- total_amount_eth_deposits
- total_amount_eth_borrows
- total_amount_eth_repays
- tx_total
- repay_to_borrow_ratio

3. Scoring Logic
Used clustering to generate synthetic behavior labels, trained a Random Forest classifier on simplified features, and converted predictions into a credit score between 0 and 100.

Scoring Logic Justification

Since the dataset did not contain predefined credit labels, we used an unsupervised learning approach to generate synthetic labels based on wallet behavior. We applied KMeans clustering to group wallets into behavior-based segments.

We extracted five key features that reflect usage quality:
1. total_amount_eth_deposits – indicates how much the user is supplying to the protocol.
2. total_amount_eth_borrows – reflects risk-taking behavior.
3. total_amount_eth_repays – shows responsibility in settling borrowed funds.
4. tx_total – represents activity level and engagement.
5. repay_to_borrow_ratio – measures repayment discipline.

Wallets that showed high deposit amounts, consistent repayments, and lower or balanced borrow-to-repay ratios were considered more trustworthy. These clusters were labeled as higher credit quality.

Using the clusters as pseudo-labels, we trained a Random Forest classifier to learn scoring patterns. Final predictions were normalized to a 0–100 scale to represent credit scores, where higher scores indicate more reliable and protocol-supportive behavior.

This approach allows credit scores to reflect behavioral patterns without requiring external supervision or pre-existing score systems.



4. Output Files
- model.ipynb: Complete notebook for scoring
- top_1000_ml_wallet_scores.csv: Highest 1000 scoring wallets
- wallet_analysis.md: Behavior summary for top and bottom wallets

Future Implementations
- Save the trained machine learning model using pickle for reusability
- Build a simple web interface or API using Flask or FastAPI for real-time scoring
- Automate wallet behavior monitoring with scheduled model predictions
- Extend the model to include time-based features or advanced behavior patterns
- Integrate into decentralized platforms for real-time credit scoring

