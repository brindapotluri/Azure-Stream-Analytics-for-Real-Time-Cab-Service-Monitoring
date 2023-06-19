# Azure Stream Analytics for Real-Time Cab Service Monitoring

## Overview
This project focuses on the real-time monitoring of cab services like Uber, Ola, etc. The architecture diagram given is a replica of how these companies monitor their real-time booking service via the Power BI dashboard.

## Data Pipeline
A data pipeline is a method of moving information from one system to another. The information may or may not be updated, and it may be processed in real-time (or streaming) rather than in batches. The data pipeline includes everything from gathering data through multiple ways to storing raw data, cleaning, verifying, and transforming data into a query-able format, showing KPIs, and overseeing the entire process.

## Tech Stack
- Language: SQL
- Services: Azure VM, Docker, Azure Stream Analytics, Azure Event Hubs, Blob Storage, Cosmos DB, Power BI

## Approach
1. We use Event hubs as the ingestion point for cab booking/drop ride details. We simulate real-time data using Azure VM running a generator code.
2. We use stream analytics to join some reference data like customer details and cab owner details which are maintained in Blob storage. The joined data is used to derive multiple trends like average commission per km, routes with max bookings(to identify trends)
3. We will keep a copy of day by day in cosmos No-SQL DB, which will feed the power BI dashboards for business users' understanding.
4. Since we are using real-time streaming and analytics service., we might have to monitor it and trigger it in case of input overload via email service to service admin.

## Architecture Diagram

![Architecture Diagram](./images/architecture.png)