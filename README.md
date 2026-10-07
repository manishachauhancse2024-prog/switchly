# Switchly

## ASSIGNMENT FOR SESSION 2

## 1- Add a description field to Flag

Added an optional `description` field to Flag.

### Files Touched

#### 1. `FlagController.java`

Passed the description from the request to the service.

#### 2. `CreateFlagRequest.java`

Added the optional `description` field.

#### 3. `Flag.java`

Added the `description` field, constructor parameter and getter.

#### 4. `FlagService.java`

Updated the create method to accept the description.

### Result

A flag can now be created with or without a description.

With description:

{
    "key": "new-feature",
    "name": "New Feature",
    "description": "Testing the new feature"
}

Without description:

{
    "key": "new-feature",
    "name": "New Feature"
}

---

## 2- Add DELETE /api/v1/flags/{flagId}

Added DELETE API for deleting a flag.

### Files Touched

#### 1. `FlagController.java`

Added the DELETE endpoint.

#### 2. `FlagService.java`

Added the delete logic and checks whether the flag exists.

#### 3. `FlagRepository.java`

Added the delete method.

#### 4. `InMemoryFlagRepository.java`

Implemented the delete operation.

### Result

Existing flag → `204 No Content`

Non-existing flag → `404 Not Found`

---

## 3. Think, don't code

Currently, each flag has only one `enabled` value.

So if `new-checkout` is ON, it is ON for everyone.

To make it ON in the test environment but OFF in production, the flag state would need to be stored separately for each environment.

Example:

- test → ON
- production → OFF

The Flag model, repository, service and API would need to support environment-specific flag states.
