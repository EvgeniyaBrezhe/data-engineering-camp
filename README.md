# data-engineering-camp

Kestra homework - 

1. Used backfill, went to Buckets -> evgeniia-brezhe-kestra/yellow_tripdata_2020-12.csv -> Overview -> Size
2. As long as file: "{{inputs.taxi}}_tripdata_{{trigger.date | date('yyyy-MM')}}.csv", then it will be green_tripdata_2020-04.csv
3. Backfilled whole year, went to Buckets -> Run query: 

SELECT count(*) AS total
FROM (
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_01`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_02`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_03`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_04`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_05`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_06`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_07`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_08`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_09`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_10`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_11`
  UNION ALL
  SELECT total_amount FROM `project-231c402f-f9ad-427f-b80.zoomcamp.yellow_tripdata_2020_12`
)

4. Same as in 4, but for Greens.
5. Backfilled the yellow for March 2021, went to Buckets -> Tables -> Number of rows