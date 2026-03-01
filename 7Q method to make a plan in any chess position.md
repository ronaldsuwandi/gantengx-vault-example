Usually in the middle game we get stuck and don't know what to do next. This is where the framework comes to play. Follow and answer the 7 questions and it can guide you to make the right move

1. What problems does the opponent have?
2. What problems do I have?
3. Where am I strong?
4. Which of my pieces can be happier?
5. Which pieces do I want to trade?
6. What's the opponent's next move/plan?
7. How can I advance?

In a way it's similar to Jeremy Silman's [[Imbalances in chess|imbalance concept]]

## 1. What problems does the opponent have?
Possible answers: weak king, weak pawn/square, etc. Once you found out think about how can we target and exploit them

```chessboard
fen: 2r1nr2/2q3kp/1p1pbpp1/p7/2PpPQ2/1P1P2NP/P2B1RP1/4R2K w
annotations: Hf6/r Hg6/r Hd4/r
```

Black king is weakened because of f6 and g6 pawn. White played **h4** with idea of attacking it with h5

But if white stop and ask the question they would notice that **d4** is very weak and if white gets the pawn, the bishop will bombard the king across diagonal

```chessboard
fen: 2r1nr2/2q3kp/1p1pbpp1/p7/2PpPQ2/1P1P2NP/P2B1RP1/4R2K w
annotations: Hd4/r Ag3-e2/g Ad2-c1/g Ac1-b2/g Ac7-c5/r
```

## 2. What problems do I have?
Next is to check the opposite quesiton of question 1. We may have a weak king we want to defend, weak pawn to get rid of, etc

```chessboard
fen: 2b1rr1k/ppp1n1pp/3qp3/3p4/P2P3Q/2PN2N1/1P3PPP/R4RK1 b
annotations: He6/r He5/r Ac8-e6/r
orientation: black
```
 
At the position above, it was black's turn and we can see: 
- central e5 weak square
- bishop c8 is blocked and sad

```chessboard
fen: 2b1rr1k/ppp1n1pp/3qp3/3p4/P2P3Q/2PN2N1/1P3PPP/R4RK1 b
annotations: Ae7-g6/r Ae6-e5/r Ah4-g5/g
orientation: black
```

By moving black knight to g6 first, pawn push to e5 will be very strong since it's now protected by knight, rook and queen

## 3. Where am I strong?
Next is to check where am I strong
- Based on pawn structure, I may have a pawn majority on one side on the board want to push that
- Could be kingside, queenside, center
- Or maybe no pawn majority, but piece majority on one side of the board

```chessboard
fen: 1b2rrk1/pp1q1pp1/5n1p/2Pp4/3Pp3/PP4N1/5PPP/R2QRNK1 w
orientation: black
```

From the game above as black:
- we have pawn majority on the king side (4 pawns vs white's 3 pawns)
- our bishop also stares at white's king
- rook is ready if we push our pawn

```chessboard
fen: 1b2rrk1/pp1q1pp1/5n1p/2Pp4/3Pp3/PP4N1/5PPP/R2QRNK1 w
annotations: Af6-h7/r Af7-f5/r Ab3-b4/g
orientation: black
```

Given the position, moving the knight to h7 allow us to push f5 pawn

## 4. Which of my pieces can be happier?
This is very important question. The example below

```chessboard
fen: 4r1k1/pp1b1r1p/5qp1/2p2p2/2P1pP2/1P2P2P/P1Q3PB/3R1RK1 w
```

Talk to our pieces
- "queen, where would you be happier?"
	- "not sure yet"
- "rooks?"
	- "on d open file"
- "bishop?"
	- "of course on the long diagonal a1-h8. I can bombard the black's king"

```chessboard
fen: 4r1k1/pp1b1r1p/5qp1/2p2p2/2P1pP2/1P2P2P/P1Q3PB/3R1RK1 w
annotations: Ah2-g3/g Ag3-e1/g Ae1-c3/g
```

## 5. Which pieces do I want to trade?
Always try our worst piece and the opponent's best piece

```chessboard
fen: r2qr1k1/1p3pbp/6p1/p2p4/Pn1P4/1Q2PNP1/5PBP/1R1R2K1 w
annotations: Hb4/r Ab1-b7/g Ab4-d5/r
```

Black's knight on b4 is very good, it blocks queen and rook on b1 and also defend b7 and d5 pawns

```chessboard
fen: r3r1k1/1p1q1pbp/6p1/p2p4/Pn1P4/1Q2P1P1/5PBP/1R1RN1K1 w
annotations: Hf3/g Hd8/r Ae1-d3/g Ab4-d3/r Ad1-d3/g
```

And we will left with pawn b7 and d5 under threat

## 6. What's the opponent's next move/plan?
Prevent opponent's plan or next move

```chessboard
fen: 1r2r3/4qpkp/p3bbp1/1p6/4p3/1P2P3/P2B1PPP/1NR1QRK1 b
orientation: black
```

Black has a great position with bishop pair advantage and active pieces compared to white

What would be white's next move? White wants to play Bc3 to trade their bad bishop and remove the bishop pair advantage from black

How do we stop this? ..b4

```chessboard
fen: 1r2r3/4qpkp/p3bbp1/8/1p2p3/1P2P3/P2B1PPP/1NR1QRK1 b
annotations: Ab5-b4/g Hc3/r
orientation: black
```

This stopped white's Bc3 move and limited possible activity for white pieces.

Possible future plan for black now are
1. a5, a4 and create passed pawn on queen side
2. h5, h4 and attack white king with pawns
3. Rb5 and transfer to king side

## 7. How can I advance?
In most of situations once you ask the 6 questions, at least 1 of them will have a clear answer and you know what todo. But very rarely, there will be situations when none have an answer

```chessboard
fen: 4nrk1/pr1q1ppp/1pR1p3/3pQ3/3P1B2/1P4P1/P1R1PPKP/8 w
```

Let's go through the questions
1. What problems do opponent have? Their pieces are passive and white dominates c file
2. What problems do I have? None
3. Where am I strong? Queen side because of the open c file
4. Which of my pieces can be happier? All of them seem happy
5. Which pieces do I want to trade? None
6. What's the opponent's next move/plan? They can't do much, they can't do f6 because they'll lose e6 pawn

Now we have open c file but what do we do with it? We can't enter 7th rank because the knight defends c7 and if we do Rc8, we'll allow black f6 move

So how can I advance? Most of the time by pushing pawn (h4)

## Examples

### Example 1
```chessboard
fen: 3r2k1/pn2qpp1/1p2p2p/3pPb2/PP1P4/Q4N1P/3B1PP1/2R3K1 b
orientation: black
```

From the questions, we learn
1. White's only issue is the weak c4 square
2. Black has problem with c file, it belongs to white
3. Black's b7 knight is very unhappy

Here we can use pin on b4 pawn, by moving knight to a5 knight can then hop into c4 closing the c file. Pawn on b4 can't capture the knight because it's pinned to protect the queen

```chessboard
fen: 3r2k1/p3qpp1/1p2p2p/n2pPb2/PP1P4/Q4N1P/3B1PP1/2R3K1 b
annotations: Hb4/r Ab7-a5/g Ae7-a3/g Aa5-c4/g
orientation: black
```

### Example 2

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
```

Q1: What problems do the opponent have?
- Black king would love to have bishop on g7 to cover dark squares. Because of this black king's not very safe
- At the same time, it's not very weak because our pieces are very far from it
- Black has issue with backward d6 pawn. We can pressure it with our rooks

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
annotations: Ac1-d1/g Ae1-d1/g Ad1-d6/g
```

Q2: What problems do I have?
- Our king is fine, no weak pawn
- Weak central square on d4. If black knight comes to d4 we won't like it
- With black knight in d4 we can't pressure weak d6 pawn

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
annotations: Ae7-c6/r Ac6-d4/r
```

Q3: Where am I strong? No answer

Q4: Which of my pieces can be happier?
- We know rooks aren't doing much, they would love to be in the d file
- But light square bishop is the unhappiest, it's limited by both c4 and e4 pawn

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
annotations: Ad1-d6/r Ad3-c4/r Ad3-e4/r
```

Q5: Which pieces do I want to trade
- We have a bad bishop
- Black knight on e7 can become monster if it hops into d4
- In this case trading our bishop with the black knight will be reasonable

```chessboard
fen: r2qr1k1/p4p1p/3pp1p1/2p5/2P1P3/8/PP1Q1PPP/2R1R1K1 w
annotations: Ac1-c3/g Ac3-d3/g Ae1-d1/g Ad1-d6/g
```

Q6: What's the opponent's next move/plan?
- Black will play Nc6 and Nd4

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
annotations: Ae7-c6/r Ac6-d4/r
```

Q7: How can I advance?
We only need to ask this if all 6 questions have no clear answer. Since we know that
1. We want to play around black's d6 pawn
2. We have problem with d4 square and need to prevent black knight coming there
3. Our light square bishop is misplaced
4. We should trade it with opponent's knight

```chessboard
fen: r2qr1k1/p3np1p/3pp1p1/2p5/2P1P3/3B4/PP1Q1PPP/2R1R1K1 w
annotations: Ad3-c2/g Ac2-a4/g Ae7-c6/r
```

By pushing Bc2, white opens up d file for the rook which targets d6 pawn with the intention to trade with knight

```chessboard
fen: r2qr1k1/p4p1p/2npp1p1/2p5/B1P1P3/8/PP1Q1PPP/2R1R1K1 w
annotations: Hc6/g Ac1-d1/g Ad8-c7/r
```

With knight pinned white can then push rook to d1

Black answers with Red8 and then we can exchange bishop and knight

```chessboard
fen: r2r2k1/p1q2p1p/2npp1p1/2p5/B1P1P3/8/PP1Q1PPP/3RR1K1 w
annotations: Aa4-c6/g Ac7-c6/r
```

And we then achieve our dream, exchanged bad light square bishop with potential dangerous knight and we can now target d6 pawn

```chessboard
fen: r2r2k1/p4p1p/2qpp1p1/2p5/2P1P3/8/PP1Q1PPP/3RR1K1 w
annotations: Ae1-e3/g Ae3-d3/g
```

### Example 3

```chessboard
fen: r1b2rk1/pp3pp1/4p2p/2P5/3p2q1/PB1P4/1P1Q1PPP/R1R3K1
```

Q1: What problems do the opponent have?
No serious issue, king is safe, no weak pawn, they only behind development

Q2: What problems do I have?
No issues either. King is safe with no weak pawns or weak squares

Q3: Where am I strong?
- White is stronger on the queenside, with pawn majority 4 vs 3
- Black is stronger on the kingside with pawn majority

```chessboard
fen: r1b2rk1/pp3pp1/4p2p/2P5/3p2q1/PB1P4/1P1Q1PPP/R1R3K1
annotations: Ha3/g Hb2/g Hd3/g Hc5/g Ha7/r Hb7/r Hd4/r
```

Q4: Which of my pieces can be happier?
- White's bishop on b3 stays in the way of b pawn and stops us from pushing our pawns
- Ra1 is sad

Q5: Which pieces do I want to trade?
No answer, no specific can be gained by trading any of the pieces

Q6: What's the opponent's next move/plan?
Black is stronger on kingside, so they'll probably want to develop their bishop, bring it to c6 and try to push king side pawns

```chessboard
fen: r1b2rk1/pp3pp1/4p2p/2P5/3p2q1/PB1P4/1P1Q1PPP/R1R3K1
annotations: Ac8-d7/g Ad7-c6/g Ae6-e5/g Af7-f5/g
```

Q7: How do I advance?
Only ask this question if none of the first six had an answer

We learned
1. We should play on the queen side and push our pawns
2. Bishop on b3 is misplaced

```chessboard
fen: r1b2rk1/pp3pp1/4p2p/2P5/3p2q1/PB1P4/1P1Q1PPP/R1R3K1
annotations: Ab3-d1/g Ad1-f3/g Af3-a8/g Ag4-h4/r
```

We can then transfer bishop to f3 by doing Bd1 followed with Bf3. On f3 bishop is happier, it's close to the king and can support pawn storm on queen side. It also prevent's black's Bd7, Bc6. White next move is then to push b4, b5 pushing the pawn on queenside

Do note that c6 might make sense but white will ends up losing material (a big blunder), after c6, bxc6 and Rxc6 white is in trouble when black does Bb7

```chessboard
fen: r4rk1/pb3pp1/2R1p2p/8/3p2q1/PB1P4/1P1Q1PPP/R5K1
annotations: Hc8/r Ab7-g2/r Ag4-g2/r
```

This pinned the rook, if rook move then it's a mate

### Example 4

```chessboard
fen: 2r3k1/5n2/pBp2pqp/3p4/3P2pP/P3P3/1QP3PK/5R2 w
```

Q1: What problems do opponent have?
- Black has weakened king by pushing kingside pawns but king is ok because queen and knight provide defense
- White's queen and bishop are also far from black king
- Pawn structure, f6 is backward and a6 can be attacked

Q2: What problems do I have?
- Weak pawn on e3
- Weak central square on e4 where black knight can land

```chessboard
fen: 2r3k1/5n2/pBp2pqp/3p4/3P2pP/P3P3/1QP3PK/5R2 w
annotations: Af7-d6/g Ad6-e4/g
```

- King isn't very safe: black queen nearby, black pawn on g4 can cause trouble. If black knight joins in it could be even more dangerous

Q3: Where am I strong?
No answer

Q4: Which of my pieces can be happier?
- Rook on f1 is fine
- Quee nand bishop aren't doing much on the queen side

Q5: Which pieces do I want to trade?
- Exchanging useless bishop on b6 with black's potentially strong knight is not a bad idea
- May also trade queen to secure our king

Q6: What's the opponent's next move/plan
- If black plays ..g3 2.Kg1 Qe4 attacking the e3 and h4 pawn and mate from h2 we'll be in trouble

```chessboard
fen: 2r3k1/5n2/pBp2p1p/3p4/3Pq2P/P3P1p1/1QP3PK/5R2 w
annotations: Ae4-e3/g Ae4-h4/g Ah4-h2/g
```

- Black can also play Rb8 to create a pin on bishop
- Black has significant threat on ..Nd6 followed by Ne4

```chessboard
fen: 2r3k1/5n2/pBp2pqp/3p4/3P2pP/P3P3/1QP3PK/5R2 w
annotations: Af7-d6/g Ad6-e4/g
```

Q7: How can I advance?
Not needed as we have answer from the previous questions. We learned that

1. Our pieces on queenside are misplaced
2. Our king isn't safe
3. Black has dangerous threats

If we can get our bishop to f4 we can then push the queen into b7

```chessboard
fen: 2r3k1/5n2/p1p2pqp/3p4/3P1BpP/P3P3/1QP3PK/5R2 w
annotations: Af7-d6/r Ab2-b7/g Ac8-b8/r Ag4-g3/r
```

To achieve this, we'll go with Bc7

```chessboard
fen: 2r3k1/5n2/pBp2pqp/3p4/3P2pP/P3P3/1QP3PK/5R2 w
annotations: Ab6-c7/g Ac7-f4/g
```

After Bc7, black can't capture the bishop otherwise Qb8 will give black a check and lose rook

## See also
- [[Chess live notes]]
- [[Chess study plan for 1000-1500 rated players]]
- [[Chess weak squares]]
- [[Chess psychology]]

## References
- https://chessmood.com/blog/7q-method-chess-planning