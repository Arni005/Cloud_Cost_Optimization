# ☁️ AWS Cloud Cost Optimization – EBS Snapshot Cleaner
📌 Overview

This project is a serverless cloud cost optimization solution built using AWS.
It automatically identifies and deletes unused or stale Amazon EBS snapshots to reduce unnecessary storage costs.
The solution ensures safe cleanup by applying retention policies and validating snapshot relevance before deletion.

## 🎯 Problem Statement

In large cloud environments, unused EBS snapshots accumulate over time, leading to:

-Increased storage costs

-Difficult lifecycle management

-Manual cleanup overhead

-Risk of forgotten backup artifacts

## 🚀 Solution

A serverless automation system that:

-Scans all EBS snapshots in the AWS account

-Identifies snapshots older than 30 days

-Validates whether snapshots are still linked to active EC2 infrastructure

-Deletes only safe-to-remove snapshots

## 🏗️ Architecture

Services Used:

AWS Lambda – Executes cleanup logic

Amazon EC2 – Provides instance state data

Amazon EBS – Snapshot lifecycle management

AWS IAM – Permissions for secure access

## 🚀 Setup & Deployment

1. Create IAM Role

Attach permissions:
AmazonEC2ReadOnlyAccess
AmazonEC2FullAccess (or restricted custom policy for delete_snapshot due to zero trust architecture, i would suggest inline policy)

2. Deploy Lambda
   
Runtime: Python 3.x
Paste lambda_function.py
Set timeout: 10 sec

## Key Features

✅ Serverless automation (no servers to manage)

✅ Cost optimization through lifecycle cleanup

✅ Safety checks before deletion

✅ Retention policy (30 days)
