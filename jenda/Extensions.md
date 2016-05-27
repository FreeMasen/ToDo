## NSDate

```swift
extension NSDate {
    private var calendar: NSCalendar { return NSCalendar.currentCalendar() }
  private var allComponents: NSCalendarUnit { return [.Year, .Month, .Day, .Hour, .Minute, .Second, .TimeZone] }
  private var dateFormatter: NSDateFormatter { return NSDateFormatter() } 

  func atMidnight() -> NSDate {
    let components = calendar.components(allComponents, fromDate: self)!
    components.setValue(0, forComponent: .Hour)
    components.setValue(0, forComponent: .Minute)
    components.setValue(0, forComponent: .Second)
    return components.date!
  }
  
  func atEOD() -> NSDate {
    let components = calendar.components(allComponents, fromDate: self)!
    components.setValue(23, forComponent: .Hour)
    components.setValue(59, forComponent: .Minute)
    components.setValue(59, forComponent: .Second)
    return components.date!
  }
  
  func asPercentEncodedString() -> String {
    let stringDate = self.asDateTimeString()
    return stringDate.stringByAddingPercentEncodingWithAllowedCharacters(.URLHostAllowedCharacterSet())!
  }
  
  func asDateTimeString() -> String {
    dateformatter.dateFormat = "yyyy-MM-dd'T'HH:mm:SS'Z'"
    return dateFormatter.stringFromDate(self)
  }
  
  func asDateString() -> String {
    dateformatter.dateFormat = "yyyy-MM-dd"
    return dateFormatter.stringFromDate(self)
  }
}
```
