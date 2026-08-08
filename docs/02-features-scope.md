# 2. Features & Scope

## Feature List (Master)

**1. Equipment Availability Module**
Equipment owners post equipment they have available: tractors, harvesters, tillers, sprayers, seeders.

**2. Equipment Requirement Module**
Farmers post equipment needs: requirement, date, budget, duration.

**3. Labor Availability Module**
Laborers post their availability: labor type, availability, wage.

**4. Labor Requirement Module**
Farmers post labor needs: number of laborers required, work type, budget.

**5. AI Recommendation System**
Reads the listing, finds similar listings, calculates similarity scores, and displays the three best matches.

**6. Administrator Dashboard**
Administrators manage users, manage listings, resolve requests, and remove fraudulent listings.

**7. Manual Search**
Users can accept AI suggestions or search manually.

## Feature-to-Module Mapping

| Feature | Primary Users | Data Captured | Related System |
|---|---|---|---|
| Equipment Availability Module | Equipment owners | Equipment type (tractor, harvester, tiller, sprayer, seeder) | Listings collection (category: equipment, type: available) |
| Equipment Requirement Module | Farmers | Requirement, date, budget, duration | Listings collection (category: equipment, type: required) |
| Labor Availability Module | Laborers | Labor type, availability, wage | Listings collection (category: labor, type: available) |
| Labor Requirement Module | Farmers | Number of laborers, work type, budget | Listings collection (category: labor, type: required) |
| AI Recommendation System | All users | Listing data (all four modules above) | Matches collection (similarity scoring) |
| Administrator Dashboard | Administrators | Users, listings, matches | Administrators collection + oversight |
| Manual Search | All users | Existing listings | Listings collection (direct query) |

---
⬅️ [Previous: Problem & Vision](./01-problem-vision.md) | 🏠 [Documentation Home](./README.md) | ➡️ [Next: Workflow](./03-workflow.md)