
# API Documentation

This API documentation provides an overview of the endpoints and data models used for managing patients and forms. 

## Schemes
- **Base URL**: `https://api.example.com`

---

## Endpoints

### Forms

#### `GET /forms`
Fetch a list of forms.

- **Query Parameters:**
  - `patientId` *(string, optional)*: Filter forms by a specific patient ID.

- **Response:**
```json
[
  {
    "name": "string",
    "patientId": "string",
    "weight": "string",
    "createdAt": "date"
  }
]
```

#### `POST /forms`
Create a new form.

- **Request Body:**
```json
{
  "name": "string",
  "patientId": "string",
  "weight": "string"
}
```

- **Response:**
```json
{
  "name": "string",
  "patientId": "string",
  "weight": "string",
  "createdAt": "date"
}
```

#### `GET /forms/{id}`
Fetch a form by its ID.

- **Path Parameters:**
  - `id` *(string, required)*: The ID of the form to fetch.

- **Response:**
```json
{
  "name": "string",
  "patientId": "string",
  "weight": "string",
  "createdAt": "date"
}
```

---

### Patients

#### `GET /patients`
Fetch a list of patients.

- **Response:**
```json
[
  {
    "name": "string",
    "patientId": "string",
    "createdAt": "date"
  }
]
```

#### `POST /patients`
Create a new patient.

- **Request Body:**
```json
{
  "name": "string",
  "patientId": "string"
}
```

- **Response:**
```json
{
  "name": "string",
  "patientId": "string",
  "createdAt": "date"
}
```

#### `GET /patients/{id}`
Fetch a patient by their ID.

- **Path Parameters:**
  - `id` *(string, required)*: The ID of the patient to fetch.

- **Response:**
```json
{
  "name": "string",
  "patientId": "string",
  "createdAt": "date"
}
```

---

## Data Models

### Form
| Field       | Type   | Description                  |
|-------------|--------|------------------------------|
| `name`      | string | Name of the form.            |
| `patientId` | string | Associated patient ID.       |
| `weight`    | string | Weight value.                |
| `createdAt` | date   | Creation timestamp.          |

### Patient
| Field       | Type   | Description                  |
|-------------|--------|------------------------------|
| `name`      | string | Name of the patient.         |
| `patientId` | string | Unique identifier for the patient. |
| `createdAt` | date   | Creation timestamp.          |
