# ASSIGNMENT FOR SESSION 2

## 1- Add a description field to Flag

Added an optional `description` field to Flag.

### Files Touched

- `FlagController.java`
- `CreateFlagRequest.java`
- `Flag.java`
- `FlagService.java`

Now a flag can be created with or without a description.

---

## 2- Add DELETE /api/v1/flags/{flagId}

Added a DELETE API to delete a flag.

- Existing flag → `204 No Content`
- Non-existing flag → `404 Not Found`

### Files Touched

- `FlagController.java`
- `FlagService.java`
- `FlagRepository.java`
- `InMemoryFlagRepository.java`

---

## 3- Think, don't code

Currently, one flag has only one `enabled` value.

To have the flag ON in `test` but OFF in `production`, we would need to store the flag state separately for each environment.

Example:

- `test` → ON
- `production` → OFF
