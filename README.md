# Hotel Booking Analysis (EDA)

An exploratory data analysis of hotel booking data, aimed at understanding why bookings get cancelled so the cancellation rate can be reduced.

## Business Objective

Reduce the hotel cancellation rate. Cancellations lead to empty rooms, lost revenue and unreliable forecasts, so the goal is to find which booking characteristics are associated with cancellation and what the business can do about them.

## Dataset

- **Source:** Hotel Bookings dataset ([add link, e.g. Kaggle "Hotel booking demand"])
- **Size:** 119,390 bookings and 32 columns
- **Hotels:** City Hotel (79,330 bookings) and Resort Hotel (40,060 bookings)
- **Target variable:** `is_canceled` (1 = cancelled, 0 = not cancelled)
- **Key columns:** `lead_time`, `hotel`, `deposit_type`, `market_segment`, `total_of_special_requests`, `previous_cancellations`, `stays_in_weekend_nights`, `stays_in_week_nights`, `adr`

## Tools Used

- Python (Google Colab)
- Pandas and NumPy for data manipulation and aggregation
- Matplotlib and Seaborn for visualization

## Project Structure

1. Know your data: shape, data types, duplicates and missing values
2. Understanding variables: column descriptions and unique values
3. Data wrangling: feature engineering and grouped summaries
4. Visualization (UBM approach): Univariate, Bivariate and Multivariate charts
5. Business recommendations and conclusion

## Data Preparation

- 129,425 missing values found, mostly in `company` and `agent`
- 31,994 duplicate rows found
- The full booking log was kept for the analysis so every rate can be traced back to the source data (duplicates, nulls and outliers would be handled before any predictive modelling)
- Engineered features: `total_stay` (weekend + week nights) and `total_guests` (adults + children + babies), plus grouped ranges for lead time, stay length and special requests

## Key Findings

- 44,224 of 119,390 bookings were cancelled, about **37%**
- **City Hotel** cancels at 41.73% versus 27.76% for **Resort Hotel**
- **Lead time** is the strongest numeric signal (correlation 0.293). Cancelled bookings average about 145 days of lead time versus about 80 for kept bookings
- Bookings with **no special requests** cancel at 47.72%, versus 10% for bookings with 4 or more requests
- By market segment, **Groups** cancel at 61.06%, Online TA at 36.72% and Offline TA/TO at 34.32%, while Direct bookings cancel at 15.34%
- **Non Refund** deposit bookings show a 99.36% cancellation rate, which needs careful interpretation and is not treated as proof of cause
- Some categories are small (Refundable deposits: 162 bookings, 15+ night stays: 439 bookings), so their percentages should be read with caution

## Business Recommendations

- Send reconfirmation reminders for long-lead-time bookings and review deposit policies for them
- Investigate why Non Refund bookings behave so differently
- Handle Group bookings with clearer contracts and deposits
- Manage agency channels (Online TA, Offline TA/TO) carefully
- Encourage customers to share special requests, since engaged guests cancel less
- Flag customers with previous cancellations
- Use hotel type, lead time and market segment together to forecast occupancy

These findings show associations, not proven causes.

## Future Improvements

- Clean duplicates, missing values and outliers
- Build a predictive model (logistic regression or random forest) to score each booking's cancellation risk
- Build an interactive dashboard in [Tableau / Power BI]

## How to Run

1. Open `[notebook file name].ipynb` in Google Colab (use the Open in Colab badge below)
2. Upload the dataset to your Google Drive and update the file path in the data loading cell (currently `/content/drive/MyDrive/Hotel Bookings.csv`)
3. Run all cells from top to bottom

[![Open In Colab]([colab link])](colab link)

## Project Video

[Add your video link here]

## Author

Taha
