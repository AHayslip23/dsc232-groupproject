# DSC 232 Group Project

My contributions to a UC San Diego DSC 232 (Big Data Analytics) group project. The project uses PySpark on a large Spotify charts dataset, about 1.05 million rows of chart entries with song audio features.

## Repository Contents

| File | Description |
|---|---|
| `Alex Hayslip Spotify Data Preprocessing.ipynb` | Data loading, cleaning and exploration in PySpark |
| `Alex Hayslip Spotify Data Preprocessing Milestone 3 Code.ipynb` | Milestone 3: feature engineering, normalization, random forest classifiers and clustering |
| `Alex Hayslip Data Preprocessing Milestone 4.ipynb` | Milestone 4: refined exploration and final k-means clustering |

## Commit History

### `fad8770`: Upload of all three project notebooks (2025-09-05)

**Data preprocessing notebook**
- **Loading and cleaning:**
  - loaded 1,048,575 chart records into Spark
  - dropped rows with nulls, leaving 881,194
  - checked for duplicates
  - cast `streams`, `popularity` and `duration_ms` to integers
- **Exploration:**
  - descriptive statistics for streams, popularity, duration and audio features
  - record counts by region, artist, trend, time signature, explicit content and mode
  - songs with above-average streams, popularity and duration
- **North America focus (USA, Canada, Mexico):** top artists, songs and albums, including drill-downs on Drake and Post Malone.

**Milestone 3 notebook**
- **New true/false features:** `contains_cussing` (explicit), `popularity_increased`, `popularity_decreased`, `popularity_same` and `new_entry`.
- **Normalization:** checked whether audio features follow a normal distribution, then min-max normalized acousticness and loudness.
- **Random forest classifiers:**

  | Target | Accuracy |
  |---|---|
  | Contains explicit content | 83.0% |
  | Popularity increased | 61.5% |
  | Popularity decreased | 55.9% |
  | Popularity stayed the same | 88.5% |
  | New chart entry | 94.0% |

- **K-means clustering on audio features:** silhouette scores of about 0.43–0.55.

**Milestone 4 notebook**
- **Refined exploration:** top artists, songs and albums by country.
- **Final clustering:** tested different numbers of clusters by silhouette score. The final model, on danceability, energy, normalized loudness and acousticness, reached a silhouette score of **0.57**.
- **Cluster profiles:** described each cluster by its audio-feature ranges, e.g. high danceability with high loudness.

## Tools
PySpark (Spark 2.3), pandas, matplotlib, Jupyter Notebook
