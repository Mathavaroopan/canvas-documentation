---
sidebar_position: 2
---

# Database API Documentation

This document provides detailed information about the database-related API endpoints for managing platform, user, and lock data.

## Table of Contents
- [Get Lock ID by Content ID](#get-lock-id-by-content-id)
- [Get Lock JSON Object](#get-lock-json-object)
- [Get Lock ID by Input Video URL](#get-lock-id-by-input-video-url)

## Get Lock ID by Content ID

Retrieves the lock ID associated with a content ID.

### Endpoint
```
GET /get-lockId-by-contentId/:contentId
```

### Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| contentId | string | Yes | Content ID to look up |

### Response
```json
{
  "lock_id": "string"
}
```

### Status Codes
- 200: Lock ID found
- 404: Lock not found
- 500: Server error

## Get Lock JSON Object

Retrieves the complete lock object by its ID.

### Endpoint
```
GET /get-lockjsonobject/:lockId
```

### Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| lockId | string | Yes | ID of the lock to retrieve |

### Response
```json
{
  "PlatformID": "string",
  "UserID": "string",
  "OriginalContentUrl": "string",
  "LockedContentUrl": "string",
  "contentId": "string",
  "storageType": "string",
  "locks": [
    {
      "lock_type": "string",
      "starttime": "number",
      "endtime": "number",
      "customJson": "object",
      "replacement_video_url": "string"
    }
  ]
}
```

### Status Codes
- 200: Lock object found
- 404: Lock not found
- 500: Server error

## Get Lock ID by Input Video URL

Retrieves the lock ID associated with an input video URL.

### Endpoint
```
GET /get-lockId-by-inputVideoUrl
```

### Query Parameters
| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| inputVideoUrl | string | Yes | URL of the input video |

### Response
```json
{
  "lock_id": "string"
}
```

### Status Codes
- 200: Lock ID found
- 404: Lock not found
- 500: Server error 