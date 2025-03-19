A TLQ (Transform, Load, Query) pipeline was built to process sales data. The process started with a CSV file containing 1.5 million rows of data, stored in AWS S3. Three Lambda functions were developed: Service1, Service2, and Service3.

    Service1 (Transform): This function processed the raw data by adding new columns like Order Processing Time and Gross Margin while modifying existing fields,   
    such as converting Order Priority into a more human-readable format. The transformed data was saved back into S3 as a new CSV file.
    Service2 (Load): This function loaded the transformed data from S3 into an SQLite database, which was then re-uploaded to S3 for storage.
    Service3 (Query): This function allowed users to run SQL queries on the database, enabling operations like filtering, grouping, and aggregating the data.

To automate the workflow, AWS CLI scripts were used, and two different approaches were experimented with:

    Switchboard approach: A single Lambda function handled the entire process, with AWS CLI scripts automatically triggering each phase in sequence.
    Non-switchboard approach: Each step (Service1, Service2, and Service3) was executed as an independent Lambda function,   
    requiring manual execution via AWS CLI after the previous step was completed.

This project provided hands-on experience with AWS Lambda, S3, EC2, and SQLite, while exploring different automation strategies using AWS services and enhancing knowledge of cloud computing and data processing.
