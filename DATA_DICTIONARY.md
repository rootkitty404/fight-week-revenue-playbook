# Fight Week Revenue Playbook: Data Dictionary

**All data is synthetic (fake) and made for a portfolio project. Fighters, promoters, venues, hotels and sponsors are fictional. DAZN rights fees and all costs are assumptions, not real deal terms.**

The data covers 51 DAZN-televised fight cards from 2024 to 2026 in 6 markets:
- **Big cards** (star or world-title main event, 15,000+ seat arenas): Atlanta, New York, Las Vegas
- **Mid-sized cards** (contender or regional title main event, mostly 4,000-7,500 seat rooms): the DMV, Philadelphia, Texas (Houston and San Antonio)

Every card has 10 bouts. It is messy on purpose.

| File | One row = | Rows (raw) | What's messy |
|---|---|---|---|
| events_raw.csv | one fight card | 53 | 2 duplicate rows, 4 date styles, city nicknames (ATL, Philly, HTX, DC), DAZN fees written as $1.26M, $1070K or 1,350,000 |
| ticket_orders_raw.csv | one ticket order (a 10% sample, so multiply money by 10) | 24,445 | Duplicate orders, 4 date styles, seat and channel spellings, "COMP" for free tickets, blank prices |
| buyers_raw.csv | one ticket buyer | 10,742 | Duplicates, city nicknames, blank home cities, age groups written different ways |
| bouts_raw.csv | one bout (10 per card) | 516 | 6 duplicate bouts, purses written as $250K or 250,000, rounds written "10 rds", Yes/Y/TRUE/1 |
| staff_raw.csv | one person working one card (promoter staff or production company crew) | 2,198 | Staff type spellings (Production Co., Prod Company), arrival day written Tue/TUES/Tues., fees written $3.5K or 3,500, and "Included in flat fee" or blank for production crew |
| expense_lines_raw.csv | one cost invoice (venue rent, venue settlement, production company flat fee, commission, officials, medicals) | 314 | 8 invoices entered twice, many spellings of 6 categories, mixed money formats |
| fight_week_activities_raw.csv | one fight-week event | 257 | Day names, activity names, "Free" in the price column, blank attendance |
| hospitality_sales_raw.csv | one hospitality package for one card | 139 | Package spellings, money formats |
| hotel_blocks_raw.csv | one fan hotel room block | 106 | Commission written as "10%", "0.1" or "10" |
| sponsor_deals_raw.csv | one sponsor deal | 196 | Fee formats, placement spellings |
| marketing_channels_raw.csv | one marketing channel for one card | 357 | Market nicknames, spend with commas, 9 blank ticket counts |

## The fight-week travel rules built into the costs

- Main event and co-main fighters bring **3** corner people and arrive **Tuesday** for the press conference and media workout (5 hotel nights).
- All other fighters bring **2** corner people and arrive **Thursday** for the weigh-in (3 hotel nights).
- About **10 promoter staff** arrive Tuesday (the night before the press conference). The rest of the promoter staff arrive Thursday (the night before the weigh-in).
- Promoter staff are paid **$2,500-$5,000** per card and get a round-trip flight (assumed $450).
- The **production company** is paid a flat fee (**$40K** for big cards, **$20K** for mid-sized cards) and pays its own crew (about 40 people on big cards, about 20 on mid-sized). The promoter still covers the crew's **hotels and per diems**. The crew arrives Thursday.
- Everyone gets **$50 a day** per diem. Fighters and corners share rooms 2 to a room; staff and crew get their own room. Local fighters and staff need no flight or hotel.

## Other assumptions

- Commission / gate tax: 8% of ticket sales in Nevada, 5% everywhere else.
- Sanctioning fees come out of the fighters' purses, so they are not a promoter cost here.
- DAZN rights fees: about $0.9M-$2.2M for big cards, about $250K-$450K for mid-sized cards.
