# AWS Cloud Cost Optimization Automation

## Overview

This project automates the identification and deletion of unused AWS resources, such as abandoned snapshots, to optimize cloud costs. By leveraging various AWS services like Lambda, CloudWatch, SQS, and the Python Boto3 module, it provides a scalable, serverless solution for reducing cloud infrastructure expenses.

## Features

- **Automated Resource Monitoring:** Uses AWS CloudWatch to monitor AWS resources, such as instances, volumes, and snapshots.
- **Serverless Architecture:** AWS Lambda triggers automated tasks without requiring dedicated infrastructure.
- **Efficient Cleanup:** Filters out unused (abandoned) snapshots that are not attached to any active instance.
- **Notification System:** Uses AWS Simple Queue Service (SQS) to notify peers of unused resources before they are deleted.
- **Cost Savings:** Helps prevent unnecessary expenses by cleaning up abandoned resources.

## Technologies Used

- **AWS CloudWatch:** For resource monitoring and event triggering.
- **AWS Lambda:** For running automated serverless functions.
- **AWS Simple Queue Service (SQS):** For notifying peers about unused resources.
- **Boto3 (Python Module):** To interact with AWS APIs, retrieve resource details, and perform actions like snapshot deletion.

## How It Works

1. **Monitor Resources:** AWS CloudWatch tracks cloud resource usage and triggers Lambda functions based on predefined criteria.
2. **Identify Unused Snapshots:** The Boto3 module interacts with AWS APIs to retrieve lists of snapshots, instances, and volumes, filtering out unused ones.
3. **Peer Notification:** Notifications are sent to peers via SQS about abandoned snapshots to provide visibility into resource wastage.
4. **Automated Cleanup:** After notifications, unused snapshots are deleted automatically to reduce ongoing costs.

## Setup Instructions

To use this automation in your AWS environment:

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/hhsakaa/cloud-cost-optimization.git
