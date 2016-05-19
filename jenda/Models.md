## Appointment
```swift
class Appointment {
  var id: String?
  var title: String
  var start: NSDate
  var end: NSDate?
  var location: String?
  var description: String?
  var link: String?
  var status: Status
  var created: NSDate
  var updated: NSDate?
  var creator: User
  var organizer: User
  var attendees: [User: Status]
  var reminders: [Reminder]
}
```
## enum Status

## User

## Reminder?

## class Day

## class Page

## class Week

## Calendar
