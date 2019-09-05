# Scanning

Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/SQLtoNoSQL.ReadData.Scan.html

## Notes
Scans should be used sparingly because they can consume large amounts of system resources.
Sometimes a scan is appropriate (such as scanning a small table) or unavoidable (such as performing a bulk export of data). 
However, as a general rule, you should design your applications to avoid performing scans.

## Cost
You are still charged for the entire Scan, even if only a few matching items are returned.
