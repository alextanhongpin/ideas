## Location-based feature

Add a location based-feature to suggest something to a user. Use the haversine formula to compute the difference in the last location (can be cached offline at client-side, and can be confirmed with the user by showing a message "you are at xxx, change location if not"). If the user fulfil the condition, perform the necessary check.

## Timing of prompt

Most of the time the code (whether it's js or other languages) executes immediately to perform a specific business logic. Example, triggering the popup advertisements in an app whenever a user open the application. Instead of directly showing the notification (which can be annoying for users), set an `initialDelaySeconds`, which indicates the initial time that needs to be fulfilled before executing the logic. To add randomness, set a certain random number to the initial delay, after estimating the duration to perform other business logic (checking if the user should receive the notification after saying no to the previous one).


## Coupons and discounts alternative

Rather than giving out coupons and discounts, we should provide users sample products. Like a 10% chance to win something etc.

## Client as Workers

Create a system that lets users do simple work and earn points. By leveraging collective intelligence, we can make clients perform work rather than the server.
