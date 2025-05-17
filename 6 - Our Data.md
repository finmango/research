### More about our data

The **Google Health Trends API** provides access to anonymized, aggregated Google search activity data related to health topics. It is intended for non-commercial research by approved users and is especially useful for aligning real-world health phenomena with digital search behavior.

The API returns values based on the following formula:

Value[time, term] = P(term | time AND geography) × 10,000,000

Think of it like this:

> *If someone searched Google at a certain time and in a certain place, how likely is it that they were looking for the topic you're interested in?*

For example:
- For example, if 10 out of every 1 million short search sessions in New York during March were about "flu symptoms", the API would return a value of 100 (since the probability is scaled up by 10 million for readability).

So:
- The values **don’t represent search counts**.
- Instead, they indicate **how popular a topic was**, relative to total search activity at that time and place.

#### Granularity
- **Geographic Resolution**:
  - `country` (e.g., `"US"`)
  - `region` (e.g., `"US-NY"` for New York State)
  - `dma` (Designated Market Area, e.g., `"506"` for Boston)

- **Time Resolution**:
  - `day`, `week`, `month`, or `year` (default is weekly)

- **Date Range**:
  - Define using `startDate` and `endDate` in `YYYY-MM-DD` format

This granularity allows researchers to tailor queries to the **temporal and spatial scale** of their real-world research questions — from daily city-level analysis to national annual trends.


#### 🔗 Additional Notes

- Data is drawn from a **random sample** of Google searches, updated daily.
- Zeros may indicate **no activity** or **insufficient distinct queries** for privacy protection.
- Each request is limited to:
  - 2 queries per second (QPS)
  - 5,000 queries per day
  - 2,000 data points per query (terms × time × resolution)
