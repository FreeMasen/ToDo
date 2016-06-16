# Classes
### Thumb
``` swift
class Thumb {
  var level: Int
  var health: Int
  var attackPower: Dice
  var attacksLeft: Int
  var defence: Int
  var attackBonus: Int
  
  func attack() -> Attack {
    let attackRoll = Dice.d20.roll() + self.attackBonus
    let dmg = self.attackPower.roll() + self.attackBonus
    return Attack(attackRoll: attackRoll, damage: dmg)
  }
  
  func levelUp() {
    self.level += 1
    switch self.level {
      case 1...5: 
        self.attackPower = .d2
        self.health = 25
        self.attacksLeft = 5
        self.defence = 10
        self.attackBonus = 1
      case 6...10:
        self.attackPower = .d4
        self.health = 30
        self.attacksLeft = 10
        self.defence = 12
        self.attackBonus = 3
      case 11...15:
        self.attackPower = .d6
        self.health = 40
        self.attacksLeft = 15
        self.defence = 15
        self.attackBonus = 5
      case 16...20:
        self.attackPower = .d8
        self.health = 50
        self.attacksLeft = 20
        self.defence = 18
        self.attackBonus = 8
      case 21...25:
        self.attackPower = .d12
        self.health = 60
        self.attacksLeft = 25
        self.defence = 20
        self.attackBonus = 10
    }
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
