SELECT issue_key, name FROM task_info 
JOIN (
  SELECT issue_key FROM task_status 
  WHERE (DATE(start_time) BETWEEN '2021-04-01' AND '2021-04-30') AND status = "in progress"
) ON task_info.issue_key = task_status.issue_key
WHERE type = "Bug"
