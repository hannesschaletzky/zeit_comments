# Project Specification

## Goal

Build a public, mobile-first website that presents a curated collection of interesting ZEIT Online comments.

Visitors can discover one comment at a time. The next comment is selected randomly from comments the visitor has not yet seen.

The UI language is German.

I am the only person who adds comments.

## Scope

- One Node.js + TypeScript application
- PostgreSQL database
- Fewer than ~1,000 comments
- No user accounts
- No cross-device seen-state synchronization
- No automatic data extraction from ZEIT Online

## Public Website

- Display only the comment text.
- Comment text is displayed as plain text with paragraph breaks preserved.
- No HTML from comments is stored or rendered.
- Each comment has its own shareable permalink.
- Show how many comments the visitor has not yet seen.
- Provide a "next" action to discover another comment.
- Provide a "start over" action once all comments have been seen.

## Seen Tracking

- Seen state is stored in the visitor's browser.
- A comment becomes seen when the visitor clicks "next".
- Refreshing a comment does not mark it as seen.
- Seen state persists across browser sessions.
- Seen state can be reset with "start over".
- Comments added later are unseen for all visitors.

## Private Submission

The private submission route is protected with Basic Auth.

The form contains exactly two fields:

1. Comment text (required)
2. Comment URL (optional)

Submitting the form validates the fields and publishes the comment immediately.

A submission is rejected as a duplicate if its normalized text (trimmed, with whitespace and line breaks collapsed) or its URL (if given) matches an existing comment.

The comment URL, if given, is stored in the database but is never displayed on the public website.

## Database

PostgreSQL

## Requirements

- TypeScript
- Node.js
- Input validation
- Automated tests

## Non-functional Requirements

- Type-safe
- Simple architecture
- No unnecessary abstractions
- Consistent error handling
- Mobile-first UI
