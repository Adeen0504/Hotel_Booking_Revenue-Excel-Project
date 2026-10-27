# Hotel Booking & Revenue Dashboard (Excel)

An interactive Excel dashboard that analyses booking performance, revenue and cancellations across **4 hotel branches** and **5 booking channels**.

> **Note:** The dataset is synthetic (AI-generated) and was created for portfolio purposes. The insights demonstrate the analysis approach, not real business results.

![Hotel Booking & Revenue Dashboard](images/dashboard.png)

---

## Business Questions

1. How much of the booked revenue has actually been realised, and how much is still pending?
2. Which branches, room types and booking channels drive the most revenue?
3. How much revenue is lost to cancellations and no-shows?
4. When are the seasonal peaks and troughs?

## Dataset

| Detail | Value |
|---|---|
| Records | 7,000 bookings |
| Period | Check-ins across 2023 |
| Branches | 4 (Branch A to D) |
| Room types | Single, Double, Deluxe, Suite |
| Booking sources | Website, OTA, Phone, Walk-in, Travel Agent |
| Booking statuses | Confirmed, Checked-out, Cancelled, No-show |

**Columns:** booking_id, hotel_branch_city, check_in_date, check_out_date, booking_date, room_type, room_rate_per_night, num_adults, num_children, booking_source, payment_method, booking_status, special_requests, revenue_category

## What's Inside the Workbook

| Sheet | Purpose |
|---|---|
| `raw_data` | Original untouched dataset |
| `data` | Excel Table with calculated columns used for analysis |
| `KPI` | Headline metrics built with structured-reference formulas |
| `Pivot_Table` | 8 PivotTables that feed the dashboard |
| `Dashboard` | KPI cards, 6 charts and slicers for interactive filtering |

### Calculated columns

| Column | Logic |
|---|---|
| `Num_Nights` | Check-out date minus check-in date |
| `Total_Guests` | Adults + children |
| `Revenue_Amount` | Room rate × nights for *Confirmed* and *Checked-out* bookings; 0 otherwise |
| `Revenue_Type` | **Actual** (checked-out), **Expected** (confirmed, not yet completed) or **No Revenue** (cancelled / no-show) |
| `Revenue_Per_Nights` | Revenue amount ÷ number of nights |

## Key Findings

- **69% of booked revenue is still pending.** Only $1.83M of $5.85M is realised; $4.02M sits in confirmed stays, so converting these on time is the biggest lever.
- **Branch D leads, Branch C trails.** Branch D earns $1.80M (31% of revenue) at a $226 average room rate, while Branch C brings $1.23M (21%) at $162, a $64 gap per night.
- **Suites are 16% of bookings but 33% of revenue.** Suites bring $1.91M from 1,098 bookings, 1.7x what Singles earn from 2,430. Upselling to premium rooms beats chasing volume.
- **Website is the #1 channel.** 2,400 bookings and $2.02M (35% of revenue), ahead of OTA at $1.47M (25%). Travel agents add only 11%.
- **Revenue peaks in December and January.** Together they bring about 25% of annual revenue (Dec $748K, Jan $688K). March is the low at $364K; Q4 is the strongest quarter and Q3 the weakest.
- **1 in 5 bookings is lost.** 1,410 bookings (20.1%) were cancelled or no-shows, roughly $1.48M of room revenue. Branch A has the highest loss rate at 22.0%.

## Tools & Skills Demonstrated

- Microsoft Excel Tables and structured references
- Formulas: `IF`, `OR`, `COUNTIF`, `SUMIF`, `TEXT`, array formulas
- PivotTables and PivotCharts
- Slicers for interactive filtering
- Dashboard design and KPI storytelling
- Translating data into business recommendations

## How to Use

1. Download `Hotel_Booking_Revenue_Dashboard.xlsx`.
2. Open it in **desktop Excel** (slicers and PivotTables work best there).
3. Go to the `Dashboard` sheet and use the slicers to filter by branch, room type or booking channel.
4. Click **Data → Refresh All** if you change the underlying data.

## Repository Structure

```
hotel-booking-revenue-dashboard/
├── README.md
├── Hotel_Booking_Revenue_Dashboard.xlsx
├── hotel_bookings_raw.csv
└── images/
    └── dashboard.png
```

## Recommendations (from the analysis)

1. **Speed up conversion of pending stays** and send pre-arrival confirmations to protect the $4.02M in expected revenue.
2. **Push premium room upsells** at booking time, since Suites deliver outsized revenue per booking.
3. **Reduce cancellations**, starting with Branch A, using deposits or flexible-rebooking incentives.
4. **Run targeted promotions in low months** such as March to smooth out seasonality.
5. **Grow direct bookings** through the website to reduce reliance on OTA commissions.

## Author

**Adeen Ali**
[LinkedIn](https://www.linkedin.com/in/adeen-ali)

Feedback and suggestions are welcome.
