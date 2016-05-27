## NSDate

```swift
extension NSDate {
  //since I am going to be using these date components
  //to convert dates to and from strings, these vars 
  //will need to be utilized in multiple places within 
  //my NSDate extention. 
  private var calendar: NSCalendar { return NSCalendar.currentCalendar() }
  private var allComponents: NSCalendarUnit { return [.Year, .Month, .Day, .Hour, .Minute, .Second, .TimeZone] }
  private var dateFormatter: NSDateFormatter { 
    let formatter = NSDateFormatter
    formatter.dateFormat = "yyyy-MM-dd'T'HH:mm:SS'Z'" 
    return formatter
  }
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
  
  //REST query string representation of the date 
  func asPercentEncodedString() -> String {
    let stringDate = self.asString()
    return stringDate.stringByAddingPercentEncodingWithAllowedCharacters(NSCharacterSet.URLQueryAllowedCharacterSet())!
  }
  
  //the Google API requires a perticular format for the 
  //query string at the end of a HTTP request, this 
  //allows me to convert any NSDate object to the 
  //approprate string formatting for Google's API
  //other services may require other formatting so I 
  //have included the service name incase that is true
  func asGoogleString() -> String {
    return dateFormatter.stringFromDate(self)
  }
  
  private func stringFromTimeZone(timeZone: CFTimeZone) -> String {
      let seconds = timeZone.secondsFromGMT()
      let hours = seconds / (60 * 60)
      let minutes = seconds % (60 * 60)
      //since string(format:) doesn't show + sign for positive
      //integer, this is how I am adding the + to make it 
      //valid for the google API query
      if seconds > 0 {
          return String(format: "+%02d:%02d", hours, minutes)
      } else {
          return String(format: "%03d:%02d", hours, minutes)
      }
  }
}
```
