# GhostOfMaia

GhostOfMaia is a hybrid chess engine that combines Maia 1800 human like intuition with a Stockfish powered tactical safety net resulting in a centaur system that plays around 2000 Elo strength.

---

## Performance Analysis of GhostOfMaia Bridging the Tactical Gap

---

### Introduction

A central challenge in chess engine development is balancing human like intuition with machine level precision. Standalone neural networks specifically the Maia series excel at mimicking human playstyles but suffer from tactical myopia an inability to calculate immediate threats.

GhostOfMaia was developed as a Centaur Hybrid to solve this. By wrapping the Maia 1800 weights in a tactical safety layer powered by Stockfish at Skill Level 6 we aimed to create an engine that maintains a human style while refusing to commit basic blunders that affect standalone models.

---

### Methodology

We conducted a 140 game round robin tournament to test the GhostOfMaia architecture against a diverse field. The pool included classical engines Monarch Rybka Fruit and Garbochess and the full suite of Maia models from 1500 to 1900.

The Hybrid Configuration uses Maia 1800 as the primary move generator filtered through a 2.5 pawn blunder threshold.

The Pool Dynamics show that the average Elo of the reference pool was approximately 1788. Engine pool Elo is typically deflated compared to human online ratings. A performance rating of 1850 in this pool suggests a functional strength significantly higher in human centric environments estimated around 2000 to 2100 on Lichess or Chess.com.

---

### Results The Success of the Safety Net

<img width="979" height="553" alt="image" src="https://github.com/user-attachments/assets/8830957a-e9c1-42b5-b825-17f54ace34ac" />

<img width="531" height="338" alt="image" src="https://github.com/user-attachments/assets/202358fc-9d33-44cb-9318-604dd67497c0" />

<img width="361" height="357" alt="image" src="https://github.com/user-attachments/assets/6b585ac5-b460-4ef5-993f-28956408519b" />

GhostOfMaia achieved a 58.9 percent score with 57 wins 51 draws and 32 losses yielding a Tournament Performance Rating of 1850.

The most significant data point is the draw to loss ratio. While similarly rated classical engines like Fruit 2.3.1 suffered 41 losses GhostOfMaia suffered only 32. Furthermore GhostOfMaia secured 51 draws the highest in the middle tier of the tournament.

This Iron Defense is the clear fingerprint of the Stockfish safety net. The engine refuses to collapse under tactical pressure even when the underlying Maia 1800 brain suggests a sub optimal move.

---

### The Maia Paradox Why Labels Fail

The tournament data exposed a critical failure in standalone neural networks.

Maia 1900 scored 20.7 percent and Maia 1800 scored 28.2 percent while Maia 1600 scored 40.7 percent.

This creates the Maia Paradox

Human Ambition  
Maia 1900 successfully mimics the sharp aggressive and tactically complex style of a 1900 rated human

Tactical Blindness  
Because standalone Maia does not calculate it runs at 1 node it enters these high level tactical complications without the ability to navigate them

Exploitation  
Classical engines Rybka Fruit easily exploit these aggressive setups

Maia 1600 performs better because it mimics lower level more cautious human play thereby avoiding sharp tactical lines

---

### Discussion GhostOfMaia as the Solution

GhostOfMaia serves as the corrective for the Maia Paradox.

Although it uses the same Maia 1800 brain as the standalone system which scored 28.2 percent GhostOfMaia hybrid architecture doubled its performance to 58.9 percent.

By providing a 2.5 pawn buffer we allowed the engine to follow Maia human plans until the point of tactical failure. At that threshold the safety net intervened.

This effectively unlocked the potential of the Maia 1800 weights allowing it to play its intended human style without constant risk of collapse.

While the 1850 TPR is the mathematical result of this specific tournament it represents an Unbreakable Amateur.

It is an engine that possesses the strategic strength of an 1800 human but with the tactical oversight of a stronger engine.

---

### Conclusion

GhostOfMaia successfully demonstrates that a Centaur architecture is superior to standalone human prediction models.

The data confirms that GhostOfMaia is not merely another Maia net but a tactically hardened system.

With a performance rating of 1850 in a deflated engine pool it functions as a solid 2000 plus human equivalent opponent.

The broader implication is that for a human style engine to be viable it must be supported by a calculator.

GhostOfMaia stands as a proof of concept for a new category of engine the human style tactician that refuses to blunder.

---

### How To Download?

Download the GhostOfMaia RAR file from the provided Google Drive link. Once the download is complete, locate the file in your downloads folder and extract its contents into a new folder on your desktop. Ensure that lc0.exe, stockfish.exe, and the maia weights file are all kept in the same folder as the GhostOfMaia executable.

Open Lucas Chess and navigate to the Options menu. Select Engines and then click on External engines. Click the Add button and browse to the folder where you extracted the files. Select GhostOfMaia.exe and click Open. Lucas Chess will run a brief test to verify the UCI connection. Once the name GhostOfMaia appears in your engine list, click Accept to finalize the installation. You can now select the engine from the move menu during any game.

Google Drive Link: https://drive.google.com/file/d/144h7EmpGrszqUM7iZCYj1DMihmqiVCHV/view?usp=sharing


