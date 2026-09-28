# US-203 Check in

As a **Member**, I want to **check in when I arrive** so that **the library knows the room is in use**.

## Acceptance criteria

1. From 10 minutes before the start time, **Booking Details** shows a **Check in** button.
2. Clicking **Check in** changes the status to Checked in.
3. After check-in, the member gets an email receipt within 5 minutes.
4. If the member has not checked in within **15 minutes** of the start time, the room is released back to Free.
5. A released booking shows "This booking was released" in **My Bookings**.

## Notes from the product owner

- Members under 16 can book, but a guardian must be listed on their account before they can check in.
- Accessible rooms (such as R-14) are held for members who need them until 1 hour before the start time. After that, any member can book them.
- Staff sometimes move a booking to another room. The member must see the new room before they check in.

## Test data

- Sam Lee (adult)
- Ava Cruz (age 14, guardian listed)
- Room R-14, tomorrow, 14:00 to 16:00
