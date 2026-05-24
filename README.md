# Bellabeat Customer Trends




## 🏢 Client Background
Bellabeat is a high-tech manufacturer of health-focused smart products for women, founded by Urška Sršen (artist & CCO) and Sando Mur (mathematician & co-founder). Sršen's design background drives the company's philosophy: build beautifully designed technology that informs and inspires women through data on activity, sleep, stress, and reproductive health.
Since 2013, Bellabeat has grown rapidly into a tech-driven wellness brand with a global office presence and a product suite that includes the Bellabeat App, Leaf wellness tracker, Time smartwatch, and a membership program — all designed to empower women with knowledge about their own health and habits.
The company runs an active multi-channel marketing presence across Google Search, Instagram, Facebook, YouTube, and traditional media.

The Challenge: Bellabeat's executives want to become a major player in the global smart device market. To do that, they need to understand how consumers are actually using smart devices — and turn those insights into smarter marketing decisions.

Insights and recommendations are provided on the following key areas:

- **Category 1:** 
- **Category 2:** 
- **Category 3:** 
- **Category 4:** 

The SQL queries used to inspect and clean the data for this analysis can be found here [link].

Targed SQL queries regarding various business questions can be found here [link].





## 🗃️ Data Structure & Initial Checks

The dataset consists of 18 CSV files imported into BigQuery as structured tables. The core tables used in this analysis are 5 tables with a combined scope of 33 users tracked over 31 days. A description of each table is as follows:
- **daily_activity: Daily summaries per user including total steps, distance travelled, and calories burned. Primary table used for overall activity trends and user segmentation.**
- **sleep_day: Logs of total minutes asleep and total time spent in bed per user per night. Used to calculate the "awake-in-bed" metric and analyze sleep quality.**
- **intensity_hourly: Hour-by-hour intensity levels across the day. Used to identify peak activity windows and the mid-morning low-activity pattern.**
- **steps_daily: Daily step counts per user. Used to compute averages and classify users into activity segments (Sedentary, Lightly Active, Fairly Active, Very Active).**
- **weight_fat_log_info: User-logged weight entries. Inspected for weight tracking trends — notably, only 8 out of 33 users participated in this table.**
[Entity Relationship Diagram here]



## 📌 Executive Summary
### Overview of Findings
Analysis of 33 Fitbit users over 31 days reveals three critical behavioral gaps that Bellabeat can directly address through smarter marketing. First, users are more stable acitve during the weekdays and it flactuates and raise up on weekends(Saturday), enabling Bellabear to align marketing accordingly. Second, users are largely inactive during the morning window (6–10 AM) and struggle with pre-sleep wakefulness - averaging 38 minutes awake in bed - pointing to unmet demand for guided wellness routines. Third, 24.2% of users are sedentary, yet the "Fairly Active" segment shows the strongest growth potential, needing only small behavioral nudges to level up. Forth, manual data entry is a major friction point - only 8 of 33 users logged weight - suggesting Bellabeat should lead with automation and push proactive, personalized insights rather than passive tracking.

An interactive Tableau dashboard used to report and explore sales trends can be found here [https://public.tableau.com/authoring/Bellabeat_17787334776370/Dashboard1#1].


## 🔎 Insights Deep Dive
### Activity Patterns

* **1. The Mid-Day Peak.** Physical intensity and step counts surge consistently between 12:00 PM and 7:00 PM across the entire user base, making the afternoon the dominant active window of the day. In contrast, the morning window (6:00–10:00 AM) registers the lowest activity levels - a significant and consistent gap that represents a daily missed opportunity for engagement.
![image alt](https://github.com/SayedAliShahin/Bellabeat_Customer_Trends/blob/main/Viz/Peak_Huors.PNG)

(* **2. The Burnout Drop-Off.** Device engagement and data logging show a noticeable decline toward the final week of the tracked month (late April – May 12, 2016). This pattern suggests users experience a "burnout" or "forgetfulness" phase in long-term device usage — a retention risk that directly impacts the quality and consistency of health data collected.
Weekday vs. Weekend Variance. Activity levels are measurably more consistent across Monday–Friday, while Saturday and Sunday show high behavioral variance — users are either significantly more active or considerably more sedentary. This unpredictability on weekends signals an opportunity for targeted weekend wellness prompts.

![image alt](https://github.com/SayedAliShahin/Bellabeat_Customer_Trends/blob/main/Viz/Peak_Days.PNG))


### Sleep Quality

* **1. The Awake-in-Bed Gap.** Across 24 users who logged sleep data, the average time spent awake in bed before falling asleep was 38 minutes — calculated as the difference between TotalTimeInBed and TotalMinutesAsleep. This is a strong signal of difficulty winding down, and represents a direct, addressable pain point for Bellabeat's app and membership features.

* **2. Activity Does Not Guarantee Sleep.** A JOIN analysis between daily_activity and sleep_day tables revealed only a weak positive correlation between daily calorie expenditure and total sleep duration. Users who burned more calories did not consistently sleep longer — meaning physical effort alone is not solving users' sleep quality issues, and a dedicated sleep-support feature would add real value.
[Visualization specific to category 2]


### User Segmentation

* **1. The Sedentary Segment.** Approximately 24.2% of users average fewer than 5,000 steps per day, classifying them as sedentary. This group is the hardest to move but represents a significant share of the user base — and highlights a gap between owning a wellness device and actually using it toward health goals.

* **2. The Fairly Active Opportunity.** Users averaging between 7,500–10,000 steps/day (the "Fairly Active" segment) represent the single largest growth opportunity. These users are already engaged, already tracking data, and are the closest to reaching higher health benchmarks — making them the ideal audience for behavioral nudge campaigns and premium membership upsells.
  
[Visualization specific to category 3]

### Weight Logging Friction

* **1. Low Participation Rate.** Only 8 out of 33 users (24%) actively logged weight data in the weight_fat_log_info table — the lowest participation rate across all tracked metrics. Steps and sleep were logged automatically, while weight required manual input, making the drop-off a direct consequence of friction rather than disinterest.

* **2. Manual Entry as a Barrier.** The stark contrast between automated metric participation (~100% for steps) and manual metric participation (24% for weight) clearly demonstrates that users disengage when data entry requires effort. This finding directly supports the case for promoting Bellabeat's automated and connected product ecosystem over manual logging.

[Visualization specific to category 4]




## 💡 Recommendations
Based on the insights uncovered, the following four strategic recommendations are proposed for Bellabeat's marketing team:

### 🌅 1. Launch a "Morning Momentum" Campaign
- Insight addressed: Low activity during 6–10 AM across all users
Bellabeat should introduce a morning engagement feature within the app — such as guided breathing, a light movement prompt, or a personalized daily wellness goal — triggered automatically between 6:00–10:00 AM. Marketing should position the Leaf tracker and Time watch as a morning ritual companion, not just a passive tracker. Campaign messaging: "Start your day with intention."

Who acts: Marketing team + Product team
When: Prioritize for next campaign cycle


### 🌙 2. Build a "Wind Down" Sleep Program
- Insight addressed: Users spend an average of 38 minutes awake in bed before sleeping
The Bellabeat membership tier is the perfect vehicle to deliver a structured pre-sleep routine — guided meditations, breathing exercises, and stress-reduction content — activated automatically when the app detects the user is in bed but not yet asleep. This directly monetizes the sleep gap identified in the data and strengthens the case for membership upgrades.

Who acts: Content team + App development team
When: Position as flagship membership feature in next product update


### 🎯 3. Gamify the "Fairly Active" Segment
- Insight addressed: 7,500–10,000 step users are the highest-potential growth group
Introduce milestone-based challenges and streak rewards specifically targeting users in the Fairly Active segment. Push notifications, weekly progress summaries, and community leaderboards can nudge this group toward the 10,000-step threshold — increasing engagement, retention, and likelihood of converting to a paid membership. These users are already invested; they just need a reason to push further.

 Who acts: Marketing team + UX team
When: A/B test with Fairly Active segment in Q3


### 📲 4. Eliminate Weight-Tracking Friction
- Insight addressed: Only 8 of 33 users (24%) logged weight — the lowest participation of any metric
Promote the Spring smart bottle and connected scale integrations as the solution to manual logging fatigue. Marketing messaging should highlight effortless tracking — emphasizing that Bellabeat captures health data automatically, so users never have to think about it. Reducing this friction will increase data completeness, improve personalization, and drive product bundle sales.

Who acts: Marketing team + E-commerce team
When: Feature in next product bundle promotion

  


## ⚠️ Assumptions and Caveats
Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

- The dataset contains no gender or age information. It was assumed that the behavioral trends observed from the 33 Fitbit users are applicable to Bellabeat's target female audience, as the business task specifically required applying these insights to a women's wellness product.

- Only 24 out of 33 users logged sleep data, leaving 9 users unaccounted for in sleep analysis. It was assumed that missing sleep records indicate the device was not worn overnight, rather than a data collection error, and these users were excluded from sleep-related calculations.

- Records with 0 total steps and 0 total calories were present in the daily_activity table. It was assumed these entries represent days when the device was not worn and were filtered out to prevent artificially skewing daily averages downward.

- The dataset is from April–May 2016, making it approximately 10 years old at the time of this analysis. It was assumed that the core behavioral patterns around activity, sleep, and manual logging friction remain broadly relevant today, despite advancements in smart device features since 2016.

- Only 8 out of 33 users logged weight data. It was assumed that low participation reflects friction from manual entry rather than user disinterest in weight tracking, and this assumption directly informed the recommendation around automated tracking.
  
* Assumption 1 (ex: because 3% of the refund date column contained non-sensical dates, these were excluded from the analysis)
