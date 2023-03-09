# Scramble Squares Puzzle Solver
## What is Scramble Squares?

It is a puzzle game that you try to arrange nine illustrated square pieces into a square so that the images on the pieces' edges match perfectly to form a completed design in every direction.

<p align="center">
<img src="https://www.scramblesquares.com/wp-content/uploads/fish-anim.gif">
</p>
There are **95,126,814,720** possible combinations! And, only **1** of them is the solution.

## How to execute the code?

First, you have to do couple of things.
1. Give numbers to each of your cards.

2. Change the values of card arrays in the code, according to your cards. Values of your array should start from the bottom corner and has to go clockwise. For example:

<p align="center">

<img src="https://imgur.com/OopMgX0.png"  width="50%" height="30%">

</p>


```python
card2 = np.array([green_window, blue_window, yellow_window, red_door])       
```
 
3. Execute the code
  
4. Profit?

### Output

The output tells you how to arrange the cards to fit the corners.
```python
        Ninth card number is 3 , turn clockwise 3 times,
        Eighth card number is 1 , turn clockwise 3 times,
        Seventh card number is 8 , turn clockwise 2 times,
        Sixth card number is 4 , turn clockwise 3 times,
        Fifth card number is 2 , turn clockwise 1 times,
        Fourth card number is 7 , turn clockwise 1 times,
        Third card number is 9 , turn clockwise 0 times,
        Second card number is 5 , turn clockwise 1 times,
        First card number is 6,
        Number of compared cards:  5950
```
You should put those cards in this order, starting from the middle:
<p align="center">
<img src="https://imgur.com/yJgAY1b.png"  width="60%" height="30%">
</p>

Here is a solved solution:
<p align="center">
<img src="https://imgur.com/pj4JyN8.png"  width="60%" height="30%">
</p>

## Algorithm

The algorithm solves the problem with numbering the edges according to their color and shape. I gave different number values for different colors, and if the shape is house's door, it is a positive number, if it is house's window, it is a negative number.
<p align="center">
```python
red_door = 1
red_window = -1
green_door = 2
green_window = -2
blue_door = 3
blue_window = -3
yellow_door = 4
yellow_window = -4
```
</p>
Here is an example in real life:

<p align="center">
<img src="https://imgur.com/OopMgX0.png"  width="50%" height="30%">
</p>

 So, if you put two card together and the sum of their corners values equal to 0, it means that these cards are matched.

My algorithm starts with giving a number for each cards and giving 4 values for their each edges. Then, it draws the first card from the deck and puts it in the center. After that, it puts the next card to the right of the first card, and sums their corners. If the sum is 0, it means they are matching and it draws the next card and checks if it matches with the second card. If it does, it moves to the fourth card, if it does not, it withdraws the third card and continues trying other cards. This algorithm starts from the center and adds cards counterclockwise as I already showed you:
<p align="center">
<img src="https://imgur.com/yJgAY1b.png"  width="60%" height="30%">
</p>

The algorithm does this until it finds the perfect solution that matches all cards and prints which order you should put your cards and how many times you should turn them clockwise.




