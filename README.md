# Giving people api

**Search errands**
----
  Returns json data about a list of errands.

* **URL**

  /errands/query

* **Method:**

  `POST`
  
*  **URL Params**
None
* **Data Params**
`{ query:’String’, city:’string’ } as ErrandQuery`

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `
    [{
    "id":               35436,
    "url":              "https://company.zendesk.com/api/v2/tickets/35436.json",
    "created_at":       "2009-07-20T22:55:29Z",
    "updated_at":       "2011-05-05T10:38:52Z",
    "type":             "incident",
    "subject":          "Help, my printer is on fire!",
    "description":      "The fire is very colorful.",
    "priority":         "high",
    "status":           "open",
    "recipient":        "support@company.com"
    }]`

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`


**Get errand by id**
----
  Returns json data about a single errand.

* **URL**

  /errands/:id

* **Method:**

  `GET`
  
*  **URL Params**

   **Required:**
 
   `id=[integer]` errand id

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:** `
    {
    "id":               35436,
    "url":              "https://company.zendesk.com/api/v2/tickets/35436.json",
    "created_at":       "2009-07-20T22:55:29Z",
    "updated_at":       "2011-05-05T10:38:52Z",
    "type":             "incident",
    "subject":          "Help, my printer is on fire!",
    "description":      "The fire is very colorful.",
    "priority":         "high",
    "status":           "open",
    "recipient":        "support@company.com"
    }`

* **Error Response:**

  * **Code:** 404 NOT FOUND <br />
    **Content:** `{ error : "Errand doesn't exist" }`

  * **Code:** 401 UNAUTHORIZED <br />
    **Content:** `{ error : "You are unauthorized to make this request." }`
