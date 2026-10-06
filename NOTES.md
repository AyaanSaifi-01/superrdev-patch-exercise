# Patch Exercise Notes

## Summary

I ran and reviewed the React + Spring Boot task tracker and fixed the highest-value issues found during testing.

### Fixes made

* Fixed the SQL search query so `archived`, search term, and `status` filters are correctly combined using parentheses.
* Fixed the frontend loading state so it stops when an API request fails.
* Reset pagination to page 1 when the search query or status filter changes.
* Added validation for invalid `status`, `page`, and `pageSize` API parameters.
* Removed an artificial `Thread.sleep()` that unnecessarily delayed API requests.

## What I Did Not Change

I did not rewrite the application architecture or change the database schema because these were not necessary for the identified issues. I also kept the existing API structure and startup commands unchanged.

## Biggest Remaining Risk

The application performs pagination after retrieving all matching tasks into memory. This may become inefficient as the number of tasks grows significantly. Database-level pagination would be a better long-term solution.

## AI / Tools Used

I used ChatGPT to help review the code, identify potential bugs, understand their root causes, and validate possible fixes. I manually applied, tested, and verified the changes. IntelliJ IDEA, Git, Spring Boot, React, and the browser were used for development and testing.
