## NSDate

```swift
extension NSDate {
let calendar: NSCalendar {
  return NSCalendar.currentCalendar
}
  func atMidnightGMT() -> NSDate {
    let components = calendar.componentsFromDate(self)
    components.setValue(0,.Hour)
    components.setValue(0,.Minute)
    components.setValue(0,.Second)
    components.setValue(0,.Nanosecond)
    return components.date
  }
  
  func asPercentEncodedString() -> String {
    let string = self.asString()
    return stringDate.stringByAddingPercentEncodingWithAllowedCharacters(.URLQueryAllowedCharacterSet)
  }
  
  func asString() -> String {
    let components = calendar.componentsFromDate(self)
    return String(format: "%04d-%02d-%02dT%02d:%02d:%02d-%02d:%02d, 
                          components.Year, components.Month, components.Day,
                          components.Hour, components.Minute, components.Second
                          components.TimeZone)
  }
}

```
