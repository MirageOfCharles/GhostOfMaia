<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

<h1>GhostOfMaia</h1>

<p>
GhostOfMaia is a hybrid chess engine that combines Maia 1800 human-like intuition with a Stockfish tactical safety net, making a centaur system that plays around 2000 Elo strength.
</p>

<hr>

<h2>Introduction</h2>

<p>
A big problem in chess engine design is balancing human-like intuition with accurate calculation. Maia neural networks are good at copying human play, but they often miss tactics and immediate threats.
</p>

<p>
GhostOfMaia was made to fix this. It wraps Maia 1800 weights with a tactical safety layer powered by Stockfish at Skill Level 6. The goal is to keep human-style play while avoiding simple blunders.
</p>

<hr>

<h2>Methodology</h2>

<p>
We ran a 140 game round robin tournament to test GhostOfMaia against different engines. The pool included Monarch, Rybka, Fruit, Garbochess, and Maia models from 1500 to 1900.
</p>

<p>
The setup uses Maia 1800 as the main move generator, checked with a 2.5 pawn blunder threshold.
</p>

<p>
The average Elo of the pool was about 1788. Engine Elo is usually lower than human online ratings. A performance rating of 1850 in this pool likely translates to around 2000–2100 on Lichess or Chess.com.
</p>

<hr>

<h2>Results: Safety Net Effect</h2>

<img width="979" height="553" src="https://github.com/user-attachments/assets/8830957a-e9c1-42b5-b825-17f54ace34ac">

<img width="531" height="338" src="https://github.com/user-attachments/assets/202358fc-9d33-44cb-9318-604dd67497c0">

<img width="361" height="357" src="https://github.com/user-attachments/assets/6b585ac5-b460-4ef5-993f-28956408519b">

<p>
GhostOfMaia scored 58.9% with 57 wins, 51 draws, and 32 losses, giving a tournament performance rating of 1850.
</p>

<p>
One key result is the draw-to-loss ratio. Fruit 2.3.1 had 41 losses, while GhostOfMaia had 32. It also had 51 draws, the highest in its group.
</p>

<p>
This shows the safety net is working. The engine avoids collapsing under tactical pressure, even when Maia suggests weaker moves.
</p>

<hr>

<h2>The Maia Paradox</h2>

<p>
The results show a problem with standalone Maia networks.
</p>

<p>
Maia 1900 scored 20.7%, Maia 1800 scored 28.2%, and Maia 1600 scored 40.7%.
</p>

<p><strong>The paradox:</strong></p>

<ul>
  <li><strong>Human-style play:</strong> Maia 1900 plays aggressive and complex positions like a strong human.</li>
  <li><strong>Tactical weakness:</strong> It does not calculate deeply, so it often misses tactics.</li>
  <li><strong>Exploitation:</strong> Classical engines like Rybka and Fruit punish these mistakes.</li>
  <li><strong>Result:</strong> Maia 1600 does better because it plays more safely.</li>
</ul>

<hr>

<h2>Discussion: GhostOfMaia as the Fix</h2>

<p>
GhostOfMaia fixes this issue.
</p>

<p>
Even though it uses the same Maia 1800 model (which scored 28.2%), the hybrid version reached 58.9%.
</p>

<p>
A 2.5 pawn safety buffer lets the engine follow Maia’s plan until it becomes clearly bad. At that point, Stockfish steps in.
</p>

<p>
This helps the engine keep its human style without falling apart tactically.
</p>

<p>
The 1850 rating is from this specific tournament, but it behaves like a strong 1800 human player with better tactical safety.
</p>

<hr>

<h2>Conclusion</h2>

<p>
GhostOfMaia shows that combining a human-style model with a tactical engine works better than using either alone.
</p>

<p>
It is not just another Maia network. It is a safer version that avoids blunders.
</p>

<p>
In this test pool, it performs like a ~2000 human-level opponent.
</p>

<p>
The main idea is simple: human-style chess needs a calculator to stay stable.
</p>

<p>
GhostOfMaia is a proof of concept for a “human-style but safe” chess engine.
</p>

<hr>


<hr>

<h2 id="weaknesses">Project Limitations & Future Research</h2>

<p>
While GhostOfMaia successfully demonstrates the potential of the Centaur Hybrid architecture, the current results represent a foundational stage of development. To move beyond a proof of concept toward a more complete chess benchmark, several improvements are acknowledged:
</p>

<ul>
  <li>
    <strong>Sample Size & Statistical Significance:</strong>
    A 140-game round-robin gives an initial idea of performance, but it still has a lot of variance. Running 1,000+ games would make the results more stable and reliable.
  </li>

  <li>
    <strong>Competitive Diversity:</strong>
    The current test pool is useful for baseline comparison, but future testing should include more modern and varied engines to better understand real-world strength.
  </li>

  <li>
    <strong>Metric Analysis:</strong>
    The current results are based mainly on win/draw/loss percentages. Adding deeper metrics like confidence ranges or Elo error margins would make the analysis stronger and more precise.
  </li>

  <li>
    <strong>Data Transparency & Reproducibility:</strong>
    Future versions should include full PGN logs and full configuration details so others can reproduce the results exactly and verify the findings.
  </li>

  <li>
    <strong>Human Elo Correlation:</strong>
    Converting engine performance into human Elo is only an estimate. More direct testing against real human players is needed to confirm if the “2000+ human level” claim is accurate.
  </li>

  <li>
    <strong>Parameter Optimization:</strong>
    The current 2.5-pawn threshold and Stockfish level were chosen manually. A proper test across different values would show which settings actually give the best balance.
  </li>

  <li>
    <strong>Human-Like Behavior Testing:</strong>
    More testing is needed to see if the engine truly feels human-like in play, or if the Stockfish corrections make its style noticeable or inconsistent.
  </li>
</ul>

<p>
Overall, the results show that the GhostOfMaia system is a strong improvement over standalone models. With more testing, better data collection, and full reproducibility, it could become a more solid benchmark for hybrid chess engines.
</p>

<h2>How To Download</h2>

<p>
Download the GhostOfMaia RAR file from the Google Drive link. Extract it into a folder on your desktop.
</p>

<p>
Make sure <code>lc0.exe</code>, <code>stockfish.exe</code>, and the Maia weights file are in the same folder as GhostOfMaia.exe.
</p>

<p>
Open Lucas Chess, go to Options → Engines → External engines. Click Add and select GhostOfMaia.exe.
</p>

<p>
Lucas Chess will test it. Once it appears in the list, click Accept.
</p>

<p>
You can now use it during games.
</p>

<p>
Google Drive Link:
<a href="https://drive.google.com/file/d/144h7EmpGrszqUM7iZCYj1DMihmqiVCHV/view?usp=sharing">
Download GhostOfMaia
</a>
</p>

</body>
</html>
