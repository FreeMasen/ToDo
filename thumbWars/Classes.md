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
