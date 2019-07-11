# Listings

## View all listings

> Request `GET /v1/listings`

> Response `200 OK`

```json
[
  {
    "features": {
      "bedrooms": 1,
      "bathrooms": 1
    },
    "rates": "5.00,365",
    "_id": "5d0bd329a790372f488fe7c3",
    "name": "Wyndham Waikiki Beach 1 Bedroom",
    "images": [
      {
        "index": 1,
        "createdOn": "2019-06-20T18:40:19.124Z",
        "_id": "5d0bd3e8a790372f488fe7c9",
        "url": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
        "thumbURL": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
        "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
      }
    ],
    "address": {
      "formattedAddress": "227 Lewers St, Honolulu, HI 96830, USA"
    }
  }
]
```

**Authentication:** Public

Requests all of the enabled listings. The information for each listing is limited to only what is necessary for a listing card. More information for a single listing can be requested from `/v1/listings/:id`

## View one listing

> Request `GET /v1/listings/:id`

> Response `200 OK`

```json
{
  "features": {
    "bedTypes": {
      "K": 1,
      "KB": 0,
      "QS": 1,
      "Q": 0,
      "QB": 0,
      "DS": 0,
      "QM": 0,
      "DB": 0,
      "SS": 0,
      "D": 0,
      "TB": 0,
      "SB": 0,
      "T": 0,
      "BB": 0,
      "VARIES": 0
    },
    "bedrooms": 1,
    "bathrooms": 1,
    "occupancy": 4,
    "kitchen": "full",
    "area": 590
  },
  "rules": {
    "resortFeeCollectedAtResort": {
      "enabled": false
    },
    "cancelAfterBook": {
      "enabled": false,
      "hours": 0,
      "refundPercent": 0
    },
    "cancelNearCheckin": {
      "enabled": false,
      "days": 0,
      "amount": 0
    },
    "cancelPercentageRefund": {
      "enabled": false,
      "minDays": 0,
      "maxDays": 0,
      "refundPercent": 0
    },
    "cancelPriorLimit": {
      "enabled": false,
      "days": 0,
      "refundPercent": 0
    },
    "unpaidPriorLimit": {
      "enabled": false,
      "days": 0
    },
    "earliestArrival": {
      "enabled": false,
      "days": 0
    },
    "paymentDueBefore": {
      "enabled": false,
      "days": 0
    },
    "downPayment": {
      "enabled": false,
      "amount": 0
    }
  },
  "availability": {
    "updatedOn": "2019-06-20T18:40:19.127Z",
    "checkInDays": 127,
    "minimumStay": 0,
    "maximumStay": 0,
    "blacklist": []
  },
  "enabled": true,
  "rates": "5.00,365",
  "createdOn": "2019-06-20T18:40:19.127Z",
  "updatedOn": "2019-06-20T18:43:52.195Z",
  "deletedOn": null,
  "_id": "5d0bd329a790372f488fe7c3",
  "name": "Wyndham Waikiki Beach 1 Bedroom",
  "amenities": [],
  "costs": [],
  "images": [
    {
      "index": 1,
      "createdOn": "2019-06-20T18:40:19.124Z",
      "_id": "5d0bd3e8a790372f488fe7c9",
      "url": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
      "thumbURL": "https://...f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg",
      "title": "f4ddd442-b34a-4593-9940-fbb0eca16d6d.jpeg"
    }
  ],
  "address": {
    "administrativeLevels": {
      "level2long": "Honolulu County",
      "level2short": "Honolulu County",
      "level1long": "Hawaii",
      "level1short": "HI"
    },
    "_id": "5d0bd329a790372f488fe7c5",
    "formattedAddress": "227 Lewers St, Honolulu, HI 96830, USA",
    "latitude": 21.2789295,
    "longitude": -157.8306647,
    "streetNumber": "227",
    "streetName": "Lewers Street",
    "city": "Honolulu",
    "country": "United States",
    "countryCode": "US",
    "zipcode": "96830",
    "provider": "google"
  },
  "__v": 1,
  "description": "...",
  "phone": "..."
}
```

**Authentication:** Public

Requests detailed information for a single listing.

## View listing availability

> Request `GET /v1/listings/:id/availability`

> Response `200 OK`

```json
{
  "updatedOn": "2019-06-20T18:40:19.127Z",
  "checkInDays": 127,
  "minimumStay": 0,
  "maximumStay": 0,
  "blacklist": []
}
```

**Authentication:** Public

Requests listing availability.
