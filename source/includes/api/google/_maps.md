# Google Maps

## Geolocation

> Request `GET /v1/maps/locate`

```json
{
  "address": "227 Lewers St, Honolulu, HI 96830, USA"
}
```

> Response `200 OK`

```json
{
  "formattedAddress": "227 Lewers St, Honolulu, HI 96830, USA",
  "latitude": 21.2789295,
  "longitude": -157.8306647,
  "extra": {
    "googlePlaceId": "ChIJzQyzc3VyAHwRcJyW0H6NNIw",
    "confidence": 1,
    "premise": null,
    "subpremise": null,
    "neighborhood": "Waikiki",
    "establishment": null
  },
  "administrativeLevels": {
    "level2long": "Honolulu County",
    "level2short": "Honolulu County",
    "level1long": "Hawaii",
    "level1short": "HI"
  },
  "streetNumber": "227",
  "streetName": "Lewers Street",
  "city": "Honolulu",
  "country": "United States",
  "countryCode": "US",
  "zipcode": "96830",
  "provider": "google"
}
```

**Authentication:** Basic

Allows geolocation of addresses through the Google Maps Geolocation API.

### Request Parameters

| Field   | Required | Type   |
| ------- | -------- | ------ |
| address | yes      | string |
