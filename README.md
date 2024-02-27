# Security Sniffer Backend

## Endpoints

### 1. Create Security Card

- **Endpoint:** `/api/cards`
- **Method:** POST
- **Parameters:**
  - `id` (in the request body): The unique identifier of the security card.
  - `name` (in the request body): The user-defined name for the security card.
  - `description` (in the request body): A brief description or purpose of the security card.
  - `includedPatterns` (in the request body): A string of patterns specifying conditions for displaying certain data.
  - `excludedPatterns` (in the request body): A string of patterns specifying conditions for hiding certain data.
  - `sensitivity` (in the request body): A measure of the sensitivity level associated with the security card.
- **Example Request Body:**

  ```json
  {
    "id": "789012",
    "name": "Finance Rules",
    "description": "Rules for managing financial data",
    "includedPatterns": "Credit Card string",
    "excludedPatterns": "Social Security string",
    "sensitivity": "High"
  }
  ```

- **Example Response:**

```json
{
  "id": "789012",
  "name": "Finance Rules",
  "description": "Rules for managing financial data",
  "includedPatterns": "Credit Card string",
  "excludedPatterns": "Social Security string",
  "sensitivity": "High"
}
```

### 2. Get All Security Cards

- **Endpoint:** `/api/cards`
- **Method:** GET
- **Parameters:**
  - None

```json
[
  {
  "id": "789012",
  "name": "Finance Rules",
  "description": "Rules for managing financial data",
  "includedPatterns": "Credit Card string",
  "excludedPatterns": "Social Security string",
  "sensitivity": "High"
  },
  {
    "id": "345678",
    "name": "Health Records",
    "description": "Rules for managing health records",
    "includedPatterns": "Medical Tests string",
    "excludedPatterns": "Prescription Details string",
    "sensitivity": "Medium"
  }
]
```

### Delete Security Card

- **Endpoint:** `/api/cards/:id`
- **Method:** DELETE
- **Parameters:**
  - `id` (in the URL path): The unique identifier of the security card to be deleted.
- **Example Response:**

```json
{ 
    message: "Security Card with ID ${id} deleted successfully" 
}
```