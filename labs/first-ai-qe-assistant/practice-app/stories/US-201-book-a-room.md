# US-201 Book a room

As a **Member**, I want to **book a free study room** so that **I have a quiet place to work**.

## Acceptance criteria

1. On **Find a Room**, each Free room shows a **Book** button.
2. Clicking **Book** opens a pop-up with the room, date, start time, and end time.
3. Clicking **Confirm** changes the room status to Booked.
4. After booking, the room leaves **Find a Room** for that slot and appears in **My Bookings**.
5. If another member booked the room first, show "Sorry, this room was just booked."
6. If the membership is suspended, **Book** is disabled and shows "Please visit the front desk to book rooms."

## Test data

- Sam Lee (membership active)
- Jo Park (membership suspended)
- Room R-12, tomorrow, 10:00 to 12:00
