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
## Status
```swift
enum Status {
  case Confirmed
  case Tentative
  case Cancelled
}
```

## User
``` swift
class User {
  var name: String
  var emailAddress: String
  var calendars: CalendarsOptions
}
```
## CalendarOptions
While this may not be included in itial release
this would be good for future expansion
```swift
struct CalendarsOptions {
    var rawValue: Int
    init(rawValue: Int) {
      self.rawValue = rawValue
    }
    
    var relevantURL = NSURL?
    
    static let Google = CalendarsOptions(rawValue: 1)
    static let Outlook = CalendarsOptions(rawValue: 2)
    static let Facebook = CalendarsOptions(rawValue: 4)
    static let WunderList = CalendarsIotions(rawValue: 8)
}
```
## Reminder?

## Day
```swift
class Day {
    
}
```

## Page
```swift
enum Page {
    case Left(Day, Day, Day)
    case Right(Day, Day, Day, Day)
}
```

## Week
```swift
class week {

}
```
## Calendar
```swift 
class Calendar {

}
```
