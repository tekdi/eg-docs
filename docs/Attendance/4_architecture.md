---
sidebar_position: 4
---

# Architecture

#### User Initiates Attendance

The user accesses the Attendance Service and selects the option to mark attendance.
Photo Capture and Face Recognition

The service prompts the user to take a photo.
The captured photo is sent to AWS Face Recognition to match it with the user's profile photo stored in the system.

#### Location Detection

The service automatically detects the user’s current location using GPS.
The detected location is compared with the user's registered work location.

#### Attendance Recording

If the face recognition and location verification are successful, the attendance is marked and recorded in the system.
If the user is marking attendance for others, the process follows the same steps, with permissions checked before proceeding.

#### Event Integration

During events, the service works in conjunction with the Event Service to record attendance for all participants.
The same steps of face recognition and location verification are applied to ensure accurate attendance records.

#### Access Control
##### Self-Attendance:
All users can mark their own attendance.
##### Others’ Attendance:
Only users with specific permissions can mark attendance for others. These permissions are managed through the platform’s access control system.

#### Error Handling
##### Face Recognition Failure:
If the face recognition process fails, the service will prompt the user to retry or will flag the attendance for manual review.
##### Location Mismatch:
If the detected location does not match the registered work location, the service will flag the attendance and notify the relevant authorities for further action.
Dependencies
##### AWS Face Recognition:
For verifying the identity of the user by matching the captured photo with the profile photo.
GPS Location Services: For detecting the user’s current location during the attendance marking process.