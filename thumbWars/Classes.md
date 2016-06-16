# Classes
### Thumb
``` swift
class Thumb {
  var level: Int
  var health: Int
  var attackPower: Dice
  var attacksLeft: Int
  
  func attack() -> (attackRoll: Int, healthToRemove: Int) {
    return (0,0)
  }
  
}
```
``` swift
struct Attack {
  var attackRoll: Int
  var damage: Int
}
```
``` swift
enum Dice: int {
  case d2 = 2
  case d4 = 4
  case d6 = 6
  case d8 = 8
  case d10 = 10
  case d12 = 12
  case d20 = 20
  
  func roll() -> Int {
    let unsignedMax = UInt(self.rawValue)
    let unsignedRandom = arc4random_uniform(unsignedMax)
    return Int(unsignedRandom)
  }
  
  func roll(numberOfDice: Int) -> Int {
    var total: int = 0
    for i in 1...numberOfDice {
      total += self.roll()
    }
    return total
  }
