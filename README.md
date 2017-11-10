# 7up-7down
Seven Up Seven Down Game
Ansh (2016CS10367) and Pradyumna (2016CS10375)
1. Detailed description of overall design
First we take input from user using switches and three pushbuttons one
each for initial amount of both players and one for bet amount. Then
random number is generated using RNG. After that we provide
information about which player is betting on which side of seven. Then
decider comes into play using comparator , bet_on and comparator. Then
subtractor starts to work and the cash amount of each player changes in
their respective buffers. We also have a GameOver which tells whether
either of the player has zero balance or not. One point to be noted is that
we can’t have same set of bets again i.e. say P1 puts a bet on greater than
7 and P2 on less than 7 then on next bet one of the player must change
his bet. The next challenge was to implement the display part sequentially
as we needed the code to remember the history. So we designed a finite
state machine to implement this.This FSM takes care of everything that
will be displayed in the code.
Description of FSM =>
-> Random Number Generator(RNG) : Generates a random number
between 2 and 12.
-> Bet_On : Outputs two bits indicating whether the bet is valid or not
and other indicates which player betted on greater than seven.
-> Comparator: Outputs 0/1 denoting whether the input bit vector(output
of RNG) is greater than 0111 or not.
-> Decider: Outputs 0/1 using output of comparator and Bet_On. It also
outputs two bits one indicating who won the bet and other indicating that
whether the bet placed was valid or not.
-> Seven segment display : Same as used in Lab-4.
-> Feed_Amount : Register used to store input for amount of player1 and
player2.
-> Bet_Register : Register used to store input for bet amount.2. Mappings
##LEDs =>
-> over : This indicates whether the game is over or not.
-> P1won : This indicates that currently player one is winning.
-> P2won : This indicates that currently player two is winning.
-> invbet : This will tell us whether the bet amount inserted is greater
than either of the player’s current amount.
-> invald : This will tell us whether the bet is invalid or not. It works on
the condition that both the players bet on different sides of seven.
##Switches=>
-> P1 : This indicates that whether player one is betting on greater than 7
or not.
-> P2 : This indicates that whether player two is betting on greater than 7
or not.
-> Extra : This is used for transition between random state to the winning
player’s state.
-> lifesaver : Helps in taking input so that we don’t end up storing
undefined in registers.
-> amounts(11 downto 0) : used for taking input.
##Push Buttons=>
-> pb1 : Used to input player one’s initial amount.
-> pb2 : Used to input player two’s initial amount.
-> pb13: Used to input bet amount.
-> pb4 : Used to reset the random number.
-> pb5 : Used to get random number.
3.How to use??
1. Feed initial amount for each player and also the bet amount (using three
pushbuttons and switches).
2. Press pb4 to send RNG to a start state and generation of random
number will happen by subsequent pressing of pb5.
3. Now using P1 and P2 decide the bet. This will be the very first bet.
4. Now to change bet amount start following steps from third part offirst step.
5. Have fun untill the game is over!!!!!!!!
