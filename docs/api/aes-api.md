---
sidebar_position: 1
---

# AES API Documentation

This document provides detailed information about the AES (Advanced Encryption Standard) API endpoints for managing video content locks.

## Table of Contents
- [Create AES Lock](#create-aes-lock)
- [Modify AES Lock](#modify-aes-lock)
- [Delete AES Lock](#delete-aes-lock)

## Create AES Lock

Creates a new AES lock for video content.

### Endpoint
```
POST /create-AES
```

### Request Body
```json
{
  "storageType": "AWS",
  "storageMetaData": {
    "awsAccessKeyId": "string",
    "awsSecretAccessKey": "string",
    "awsRegion": "string",
    "awsBucketName": "string"
  },
  "inputVideoUrl": "string",
  "lockedVideoUrl": "string",
  "platformName": "string",
  "userName": "string",
  "contentId": "string",
  "locks": [
    {
      "lock_type": "blackout-lock",
      "startTime": "number",
      "endTime": "number"
    },
    {
      "lock_type": "form-lock",
      "startTime": "number",
      "endTime": "number",
      "customJson": "object"
    },
    {
      "lock_type": "replacement-video-lock",
      "startTime": "number",
      "endTime": "number",
      "replacement_video_url": "string"
    }
  ]
}
```

### Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| storageType | string | Yes | Storage type (currently only supports "AWS") |
| storageMetaData | object | Yes | AWS credentials and configuration |
| inputVideoUrl | string | Yes | URL of the original video content |
| lockedVideoUrl | string | Yes | URL where the locked video will be stored |
| platformName | string | Yes | Name of the platform |
| userName | string | Yes | Name of the user |
| contentId | string | Yes | Unique identifier for the content |
| locks | array | No | Array of lock objects defining the restrictions |

### Response
```json
{
  "message": "Lock created successfully",
  "lock_id": "string"
}
```

### Status Codes
- 201: Lock created successfully
- 400: Bad request (missing or invalid parameters)
- 500: Server error

## Modify AES Lock

Modifies an existing AES lock.

### Endpoint
```
POST /modify-AES
```

### Request Body
```json
{
  "storageType": "AWS",
  "storageMetaData": {
    "awsAccessKeyId": "string",
    "awsSecretAccessKey": "string",
    "awsRegion": "string",
    "awsBucketName": "string"
  },
  "lockId": "string",
  "newLocks": [
    {
      "lock_type": "blackout-lock",
      "startTime": "number",
      "endTime": "number"
    }
  ]
}
```

### Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| storageType | string | Yes | Storage type (currently only supports "AWS") |
| storageMetaData | object | Yes | AWS credentials and configuration |
| lockId | string | Yes | ID of the lock to modify |
| newLocks | array | Yes | Array of new lock objects |

### Response
```json
{
  "message": "Lock modified successfully",
  "lock_id": "string"
}
```

### Status Codes
- 200: Lock modified successfully
- 400: Bad request (missing or invalid parameters)
- 404: Lock not found
- 500: Server error

## Delete AES Lock

Deletes an existing AES lock.

### Endpoint
```
POST /delete-AES
```

### Request Body
```json
{
  "storageType": "AWS",
  "storageMetaData": {
    "awsAccessKeyId": "string",
    "awsSecretAccessKey": "string",
    "awsRegion": "string",
    "awsBucketName": "string"
  },
  "lockId": "string"
}
```

### Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| storageType | string | Yes | Storage type (currently only supports "AWS") |
| storageMetaData | object | Yes | AWS credentials and configuration |
| lockId | string | Yes | ID of the lock to delete |

### Response
```json
{
  "message": "Lock deleted successfully"
}
```

### Status Codes
- 200: Lock deleted successfully
- 400: Bad request (missing or invalid parameters)
- 404: Lock not found
- 500: Server error 