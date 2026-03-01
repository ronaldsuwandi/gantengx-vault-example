Position played by Fischer - Gadia, white to move
```chessboard
fen: 2r3k1/5ppp/pqrp1b2/1p2pP2/4P3/2NQ4/PPP3PP/3R1R1K w - - 0 1
annotations: Af8-c8/r
```

Black is lost because of the **weakness on d5**

```chessboard
fen: 2r3k1/5ppp/pqrp1b2/1p1NpP2/4P3/3Q4/PPP3PP/3R1R1K w - - 0 1
annotations: Ac3-d5/g
```

After Nd5 black resigned after 5 moves

Weak square = square that can't be controlled by pawns. In the example below the highlighted part shows the weak square where the black pawn has no control over

```chessboard
fen: 7k/8/3p4/2pNp3/8/8/8/7K
annotations: Hd5/g
```

```chessboard
fen: 7k/8/4p3/3pB3/3P4/8/8/7K
annotations: He5/g
```

## Why it's important
```chessboard
fen: 8/8/1pk1p3/p2p1p1p/P2P3P/1P2PPK1/8/8
annotations: He5/g Hf4/g Hg5/g
```
In this example above, we can see that black has weak squares marked with green. White king can get into those squares and take advantage

```chessboard
fen: 8/8/1pk1pp2/3p3p/pP1P3P/P3PPK1/8/8
annotations: Hb5/g Hc4/g Hb3/g He5/r Hg5/r
annotations: Ac6-b5/b Ab5-c4/b Ac4-b3/b
```

The difference is black pawn on f6 instead of f5.This allow black to control important squares on g5 and e5 (red highlight) whereas white pawn structure on the queen side is weak and black can get into the position

## How to identify weak squares
Look for the squares the opponent is not controlling or can't control with the pawns

```chessboard
fen: 4r1k1/6pp/2pnp3/pp1p4/3P4/1PPN1P2/P5PP/4R1K1
annotations: Hc5/g He5/g Ad3-c5/b Ad3-e5/b
```

In this example, black has c5 and e5 weak squares whereas white has no weak squares. White knight can take good central outposts on c5 or e5

## How to use weak squares

```chessboard
fen: 8/3kb3/1p1p4/p3p1p1/P3P1Pp/2P4P/1P1NK3/8
annotations: Hb5/g Hd5/g Hf5/g
annotations: Ae2-d3/g Ad3-c4/g
```

From the position above, white has solid support on black's weak squares (light squares). Knight can hope to b5 or the king can quickly advance to c4. Using the light squares white king can invade black's camp

```chessboard
fen: r1rb2k1/5ppp/1p1p4/pP1Pp3/P3P3/4BP2/6PP/R1R2K2
annotations: Hc6/g Ac1-c6/b
```

Above position both players fighting over c-file. Pawns on dark squares limit black's bishop and white's bishop can target the pawns. However one of the weakest square is c6, by moving rook to c6 the rook can target both pawns

When exploiting weak squares, we must ensure we have the **right piece** to do so

```chessboard
fen: r4nk1/pp2bp1p/2pq1p2/3p4/3P4/P1NBPQ2/1P3PPP/2R3K1
annotations: Hf5/g
```

In the above position, the black king side structure is weak. The question is should you use white queen or bishop to occupy that weak square? Either is fine **but** knight is protecting h7 spot so you can't do a mate

Instead, imagine another option if white knight goes via e2-g3-f5
```chessboard
fen: r4nk1/pp2bp1p/2pq1p2/3p1N2/3P4/P2BPQ2/1P3PPP/2R3K1
annotations: Ac3-e2/g Ae2-g3/g Ag3-f5/g Hg7/g Hh6/g
```

With this option, the knight attacks weakened square g7 and h6 which can create dangerous threat for black king

You can also use this for defense in the example below
```chessboard
fen: 5rk1/ppp3pp/2bb4/4p3/7q/2NPP3/PPQN1PPP/2R3K1
annotations: Hf2/r Hh2/r
annotations: Ae5-e4/r
```

f2 is very weak targetted by both queen and rook. Black can also play e4 push to open up the bishop and also aiming for h2. This is when you can use black's weak square to defend
```chessboard
fen: 5rk1/ppp3pp/2bb4/4p3/4N2q/2NPP3/PPQ2PPP/2R3K1
annotations: Hf2/g !e4
```

Nde4 prevents e5 push and also defend f2 pawn. It also further protect f2 by opening white queen to protect the pawn

## 5 ways to create weak squares in opponent's position
### Destroy the structure
```chessboard
fen: r2r2k1/1p3ppp/1q1p1n2/2b1p1B1/p1PpP3/3P3P/PP2NPP1/1R1Q1RK1
annotations: Hd2/g Hg5/g
annotations: Ah7-h6/r, Ag5-f6/g
```

Black f6 can't be defended, if black goes h6 then the knight can hop into f5 while leaving g file open

```chessboard
fen: r2r2k1/1p3p1p/1q1p1p2/2b1p3/p1PpP3/3P3P/PP2NPP1/1R1Q1RK1
annotations: Ag7-f6/r Ae2-g3/g Ag3-f5/g
```

### Weaken the structure
The current setup black has no weak square but we can try to create them

```chessboard
fen: 8/1b5p/pp1kppp1/8/PP1K1PPP/3NP3/8/8
annotations: Ag4-g5/g Af6-f5/r
```
After black push to f5 then e5 is no longer defended by pawn thus a weak square

```chessboard
fen: 2b5/7p/p2kp1p1/PpN2pP1/1P1K1P1P/4P3/8/8
annotations: Hb7/r Hc8/r
annotations: Aa4-a5/g Ab6-b5/r Ad3-c5/g
```

After the white knight goes to c5 and black bishop goes to Bc8, black bishop is paralysed because a6 is hanging if it moves

```chessboard
fen: 2b5/7p/p2kp1p1/PpN2pP1/1P1KPP1P/8/8/8
annotations: Ae3-e4/g !e4 Af5-e4/r Ad4-e4/g

```

Despite black didn't have weak squares, the position was destroyed after white weakened the structure

### Provocation
Another way to entice opponent to create weak squares. In the example below, we provoke black by attacking on h7

```chessboard
fen: r1b2rk1/ppn2ppp/1q2p3/2p1P3/2P1Q3/8/PPB2PPP/R1B1R1K1
annotations: He3/g He4/g
```

This forces black to play g6 thus creating weak squares

```chessboard
fen: r1b2rk1/ppn2p1p/1q2p1p1/2p1P3/2P1Q3/8/PPB2PPP/R1B1R1K1
annotations: Hf6/r Hg7/r Hh6/r
annotations: Ac1-h6/g Ae4-h4/b Ah4-f6/b
```

If black doesn't want to play g6 but f5 or f6 we can still capture using exf6 (en passant or normal capture)

```chessboard
fen: r1b2rk1/ppn3pp/1q2pP2/2p5/2P1Q3/8/PPB2PPP/R1B1R1K1
annotations: He5/g Hf6/g Af8-f6/r Ae4-h7/g
```

### Fixing the weak square
We can advance our pawn to gain space and create weakness

```chessboard
fen: 5rk1/pp1b2pp/4p3/3p4/3P4/2P5/PP1N1PP1/R5K1
annotations: Hd3/g Hd4/g
```

Advancing d4 preventing black to do e5 and we can follow up with Nf3 or Re1 to further secure e5 square

If we don't do d4 but do Nb3 instead

```chessboard
fen: 5rk1/pp1b2pp/4p3/3p4/8/1NPP4/PP3PP1/R5K1
annotations: Hd2/g Hb3/g Ae6-e5/r
```

Then black can play e5 and no more weak square opportunity

### Sacrifice to create a weak square
In the move below, white choose to sacrifice the rook to get a weak square

```chessboard
fen: r4rk1/1ppq1ppp/p2p1n2/4p3/4P3/3PP1NP/PPP3P1/R2Q1RK1
annotations: Af1-f6/g Ag7-f6/r
```

```chessboard
fen: r4rk1/1ppq1p1p/p2p1p2/4p2Q/4P3/3PP1NP/PPP3P1/R5K1
annotations: Hd1/g Hh5/g Ag8-h8/r Ah5-h6/g Af8-g8/r
```

```chessboard
fen: r6k/1ppq1prp/p2p1Q2/4p3/4P3/3PP1NP/PPP3P1/R5K1
annotations: Hh6/g Hf6/g Hg8/r Hg7/r Ag3-f5/g
```

Doing this white destroy black's pawn structure and gets winning position

## What to do when you have weak squares

When you have weak squares you have 3 options
1. Get rid of the weak square
2. Defend them
3. Make them useless

```chessboard
fen: 2n2rk1/1pp3pp/p4p2/3p4/3P4/P3P2P/1PP1N1P1/5RK1
annotations: He4/g Ae2-c3/g
```

White has weak square on e4, simply moving Nc3 will provide suport for e4 and then white can push e4 as it will be supported by the knight

Sometimes exchanging pawns in charge controlling weak square can be a great defensive technique

### Useless weak squares
Weak squares is only useful if you have the right piece to use it

```chessboard
fen: 2r5/pp6/3pkp2/2p1p1p1/2P3Pp/3PPP1P/PP2K3/2R5
annotations: Hd5/r He4/r Hf5/r
```

In this example, black has d5, e4 and f5 weak square but white has no pieces that can utilise them, no piece that can go to that weak square to be useful

## References
- https://chessmood.com/blog/weak-squares-in-chess