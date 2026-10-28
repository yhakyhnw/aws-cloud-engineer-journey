# Week 04 — Storage & Databases

S3, EBS, EFS, RDS, and DynamoDB all store data, which means the difference is the shape of the data and who needs to reach it. S3 holds files as objects. EBS is a disk for one instance. EFS is a filesystem several instances share. RDS is for rows, columns, and joins. DynamoDB is for looking one item up by a key.

| Service | Use this when |
|---|---|
| S3 | The data is a file, and older objects can move to a cheaper class such as Glacier with a lifecycle rule. |
| EBS | One EC2 instance needs its own disk, like the root volume of `property-api-01`. |
| EFS | More than one instance has to read and write the same files at the same time. |
| RDS | The data is a table with a fixed schema and the questions need filters, joins, or aggregates, like `rets_property` grouped by city. |
| DynamoDB | Each item is fetched by one key, such as `L_ListingID`, and the table should scale by request instead of by a server you manage. |
