---
sidebar_position: 1
slug: /
---

# Canvas API Documentation

Welcome to the Canvas API documentation. This documentation provides detailed information about the Canvas video content management system's API endpoints.

## Available Endpoints

### AES (Advanced Encryption Standard) Operations

- [Create AES Lock](/api/aes-api#create-aes-lock)
  - Create new AES-encrypted video content with customizable locks
  
- [Modify AES Lock](/api/aes-api#modify-aes-lock)
  - Update existing video locks and their configurations
  
- [Delete AES Lock](/api/aes-api#delete-aes-lock)
  - Remove existing video locks

### Lock Management

- [Get Lock ID by Content ID](/api/aes-api#get-lock-id-by-content-id)
  - Retrieve lock information using content identifiers
  
- [Get Lock JSON Object](/api/aes-api#get-lock-json-object)
  - Get detailed lock configuration and settings
  
- [Get Lock ID by Input Video URL](/api/aes-api#get-lock-id-by-input-video-url)
  - Find lock information using video URLs

## Authentication

All API endpoints require AWS credentials for authentication. Ensure you have:

- AWS Access Key ID
- AWS Secret Access Key
- AWS Region
- AWS Bucket Name

## Storage Requirements

The API currently supports AWS S3 for video storage. Make sure you have:

- Proper IAM roles and permissions
- S3 bucket configured for video storage
- Appropriate CORS settings
