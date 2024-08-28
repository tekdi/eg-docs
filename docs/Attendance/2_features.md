---
sidebar_position: 2
---

# Features


#### Self-Attendance Marking

Users can mark their own attendance using this service.
When marking attendance, the service prompts the user to take a photo, which is then matched against the user’s profile photo using AWS Face Recognition.

#### Attendance Marking for Others

Users with the necessary permissions can mark attendance on behalf of others.
Similar to self-attendance, face recognition is employed to verify the identity of the individual whose attendance is being marked.

#### Face Recognition

The service uses AWS Face Recognition to match the photo taken during attendance marking with the user's profile photo.
This ensures that the person marking attendance is the same as the one in the profile, thereby preventing fraudulent attendance marking.

#### Location Verification

The service automatically detects the user's location at the time of attendance marking.
It compares the detected location with the registered work location of the user to verify that the attendance is being marked from the correct location.
Any discrepancies between the detected and registered locations are flagged for further review.

#### Integration with Event Service

The Attendance Service is integrated with the Event Service to manage and record attendance for event participants.
This functionality allows for seamless attendance tracking during events, ensuring that all participants are accurately recorded.