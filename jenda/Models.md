## Appointment
```swift
struct Appointment {
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
    static let WunderList = CalendarsOptions(rawValue: 8)
    static let Evernote = CalendarsOptions(rawValue: 16)
}
```
## Reminder?

## Day
```swift
struct Day {
    let date: NSDate
    let dayOfTheWeek: String
    let appointments: [Appointment]
    
    init(date: NSDate) {
      self.date = date
      self.dayOfTheWeek = DaysOfTheWeek(date)
    }
}
```

## Page
```swift
enum Page {
    case Left(monday: Day, tuesday: Day, wednesday: Day)
    case Right(thursday: Day, friday: Day, saturday: Day, sunday: Day)
}
```

## Week
```swift
struct week {
  let leftPage: Page
  let rightPage: Page
  
  init(days: [Day]) {
    
  }
}
```
## Agenda
```swift 
class Agenda {

}
```
