---
title: Adding mentors
description: We added a way for schools to add their mentors to the service
date: 2024-02-09
tags:
  - mentors
related:
  items:
    - text: Adding mentors in Manage school placements
      href: /manage-school-placements/adding-mentors/
    - text: Adding mentors in Support
      href: /claim-funding-for-mentors/adding-mentors-in-support/
screenshots:
  items:
    - text: Mentors list
      src: mentors--list.png
    - text: Mentors list - empty
      src: mentors--list-empty.png
    - text: Add mentor - finding a teacher using DQT/Teacher Record
      src: mentors--add-mentor.png
    - text: Add mentor - error message - enter a TRN
      src: mentors--add-mentor-error-message-no-trn.png
    - text: Add mentor - error message - enter a valid TRN
      src: mentors--add-mentor-error-message-invalid-trn.png
    - text: Add mentor - error message - mentor already added
      src: mentors--add-mentor-error-message-duplicate.png
    - text: Add mentor - no results found
      src: mentors--add-mentor-no-results-found.png
    - text: Add mentor - check your answers
      src: mentors--add-mentor-check-your-answers.png
    - text: Mentor added success message
      src: mentors--add-mentor-success.png
    - text: Mentor details
      src: mentors--mentor-details.png
    - text: Remove mentor
      src: mentors--remove-mentor.png
    - text: Mentor removed success message
      src: mentors--remove-mentor-success.png
eleventyComputed:
  eleventyNavigation:
    key: claim-mentor-funding-adding-mentors
---

We added a way for schools to add their mentors to Claim funding for mentors.

We collect a list of a school’s mentors essential to creating a claim.

## How it works

### Mentor list

On the mentor list page, we show:

- an ‘Add mentor’ button
- a list of mentors in alphabetical order - ordered by their first name, then last name

For each mentor in the list, we show:

- full name - including a link to the mentor details page
- teacher reference number (TRN)

We paginate the list if the mentor list contains more than 25 mentors.

We show a success message above the page heading when a mentor is added or removed.

### Mentor details

On the mentor details page, we show a summary list of the mentor’s details, including:

- first name
- last name
- teacher reference number (TRN)

This page also includes a ‘Remove mentor’ link, which allows mentors to remove the mentor.

Users cannot change the mentor’s first name, last name and TRN.

### Adding a mentor

![Add mentor flow](add-mentor--flow.png)

Selecting ‘Add mentor’ starts the add mentor flow.

The ‘Add mentor’ flow has two steps:

1. Find a teacher by TRN
2. Check your answers

#### Find a teacher by TRN

The first step in the ‘Add mentor’ flow is to enter the mentor’s teacher reference number (TRN).

Users can find a lost TRN or apply for a TRN by reading the [Teacher reference number (TRN) guidance](https://www.gov.uk/guidance/teacher-reference-number-trn).

##### Validation rules

If the user does not enter anything, we show an error message:

> Enter a teacher reference number (TRN)

If the user does not enter a valid TRN, we show an error message:

> Enter a valid teacher reference number (TRN)

A valid TRN is seven digits.

#### No results found

If the user enters a valid TRN but it does not return a result, we show a page with the heading:

> No results found for ‘{trn}’

Users can change their search. We pre-populate the previously entered TRN for them to change.

#### Check your answers

The final step is to check your answers.

We use Database of Qualified Teachers (DQT) data and display it in a summary list.

We show:

- first name
- last name
- teacher reference number (TRN)

When a user adds a mentor to Claims, and they or another user adds the same mentor to Manage school placements (Placements), we match the records so that there is only one instance of a mentor in our provider. This allows us to share information between services more accurately.

### Removing a mentor

Users must confirm the mentor’s removal when they select ‘Remove mentor’.

When users remove a mentor from the organisation, we retain their data. We must keep a historical record of mentors allocated to claims.

## Further considerations

We considered some changes that we did not implement. These included:

- finding the mentor by National Insurance number
- adding a mentor manually
- showing mentor’s provider training details
- constraints on removing a mentor

### Finding the mentor by National Insurance number

If the user does not know the mentor’s TRN, we can identify a mentor using their National Insurance number (NINO) and date of birth.

We considered giving users the option to add a mentor using NINO. However, mentors can use the [Find a lost teacher reference number (TRN)](https://find-a-lost-trn.education.gov.uk/start) service, so there is no need for us to build it into the service.

### Adding a mentor manually

We considered allowing users to enter mentors manually, not via a DQT lookup. However, we need assurance that a mentor is a teacher as the information is shared with Claim funding for mentors. This means we will not allow users to add mentors manually to the service.

### Showing mentor’s provider training details

We could give users a way to manage mentor’s training outside the claim process or show that they’ve received training based on the information given in the claim.

The information about completed training could become important when verifying the relationship between a school and an accredited provider.

### Constraints on removing a mentor

We allow users to remove mentors from the service without constraint. However, when a school adds a mentor to a claim, we may need to reconsider this since we must know who was on a claim and how many hours of training were claimed for.

*[DQT]: Database of Qualified Teachers
*[TRN]: Teacher Reference Number
