## Pig
This is Pig dice game where three players compete to reach 100 points. Player roll two dice at the same time, and the sum of two dice is added to their score. Players can choose to roll again or holds their points.
 
## How to play
1. Firstly, you need to click the roll button, and the dice will decide how much number you will get.
2. In addition, if you roll out a number one, you will lose the number that you roll, and the second player will get the chance to roll the dice
3. Furthermore, when you get a number, you can try to hold or you can try to get a larger number.
4. Lastly, if you achieve to a certain number like a 50 or a hundred, you will win the game.

## What I added
1. Firstly, I add a sign that if you achieve a hundred points, it will say player1/2 wins the game
2. In addition, I add one more dice to the game, and the player could roll two dice at the same time, and the number that the player will get is the sum of two numbers that the two dice get.
3. Lastly, I add theb third player, and it's could let 3 player to player at the same time.'

## How it works
** Dice two.** You can roll two dice in the same time, and the number of two dice will add up, then you can choose hold or not.
The idea uses a @State var, an if else statement, Int, and turnTotal,message that remember the two dice could add up to get a final score

```swift
       @State var dieSymbolTwo: String = "questionmark.square.fill"
       This part is just to set a die symbol's picture, and tell that it's has a diesymbol two, for example, it's use " string" to tell that it's has question mark in the die symbol'
       ```

```swift
    func rollDie() {
        let rollOne: Int = Int.random(in: 1...6)
        let rollTwo: Int = Int.random(in: 1...6)

        dieSymbol = "die.face.\(rollOne).fill"
        dieSymbolTwo = "die.face.\(rollTwo).fill"

        if rollOne == 1 || rollTwo == 1 {
            message = "Oh no, a 1! Player \(currentPlayer) loses \(turnTotal) points."
            turnTotal = 0
            switchPlayer()
        } else {
            let diceTotal: Int = rollOne + rollTwo
            turnTotal += diceTotal
            message = "You rolled a \(rollOne) and a \(rollTwo) (\(diceTotal) points). Roll again, or hold?"
        }
    }
    This functions is just tell how the two dice system work, for example, it's says let diceTotal: Int = rollOne + rollTwo, and it's shows the player will get the number by add the two dice's value, and the symbol is +=.
    ```       
       

## Testing 
Test 1 : 
if the player 1 roll the number 1, player 2 can start to roll the dice
Input:
let roll One: Int=1
Should happen:
player 2 could start roll the dice, and try to roll or holds 
Did happen:
yes


Test 2 :
If player roll to 94, the game will continune
Input:
    @State var playerOneScore: Int = 94
    Should happen:
The game will continune, and playerOne could still roll and hold
Did happen:
Yes


Test 3 :
If player 1 roll to 100, and holds, and there should be a sentence that says player 1 win the game 
Input:
    @State var playerOneScore: Int = 100
    Should happen:
player 1 should win the game, and there's will be a word that says player 1 wins the game
Did happen:
yes

Test 4:
When the player roll two dice together, the number will add up, and the player could choose to hold the number that add up or not
Input:
        let rollOne: Int = 3
        let rollTwo: Int = 4
                    let diceTotal: Int = rollOne + rollTwo
Should happen:
the player should get the number that add up by two dice, and they should have the choice to roll and hold
Did happen:
Yes
Test 5:
There's should be a player3 on the pig games page
Input:
                VStack {
                    Text("Player 3")
                        .font(.headline)
                    Text("\(playerThreeScore)")
                        .font(.system(size: 48, weight: .bold))
                        .monospacedDigit()
Should happen:
There should be a player 3 on the game's page'
Did happen:
Yes
## Credits
 
- The starting game was written by Mr. Gordon.
