# US-202 Cancel a booking

As a **Member**, I want to **cancel a room I booked** so that **someone else can use it if my plans change**.

## Acceptance criteria

1. On **My Bookings**, each Booked room shows a **Cancel** button.
2. Cancelling requires a reason: "Plans changed", "Found another room", or "Other".
3. "Other" requires a short note of up to 200 characters.
4. After confirming, the room returns to Free and shows on **Find a Room**.
5. Cancelling is allowed only if the start time is **more than 2 hours** away.
6. At 2 hours or less, **Cancel** is disabled and shows "Please call the front desk to cancel."

## Test data

- Sam Lee
- Room R-12, booked for 3 days from now, 10:00 to 12:00
- Room R-14, booked for today, starting in 90 minutes
