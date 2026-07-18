# awesome-o1

This is a bibliography of papers that are presumed to be related to
OpenAI’s [o1](https://openai.com/index/learning-to-reason-with-llms/).


## Video

https://youtu.be/6PEJ96k1kiw

<a href="https://youtu.be/6PEJ96k1kiw"> <img src="https://github.com/user-attachments/assets/6c890bdf-8006-4d90-b822-84b413b0f248" /> </a>

[o1 Tutorial Slides](https://srush.github.io/awesome-o1/o1-tutorial.pdf)




------------------------------------------------------------------------

> Our large-scale reinforcement learning algorithm teaches the model how
> to think productively using its chain of thought in a highly
> data-efficient training process. We have found that the performance of
> o1 consistently improves with more reinforcement learning (train-time
> compute) and with more time spent thinking (test-time compute). The
> constraints on scaling this approach differ substantially from those
> of LLM pretraining, and we are continuing to investigate them. …
> Similar to how a human may think for a long time before responding to
> a difficult question, o1 uses a chain of thought when attempting to
> solve a problem. Through reinforcement learning, o1 learns to hone its
> chain of thought and refine the strategies it uses. It learns to
> recognize and correct its mistakes. It learns to break down tricky
> steps into simpler ones. It learns to try a different approach when
> the current one isn’t working. This process dramatically improves the
> model’s ability to reason. To illustrate this leap forward, we
> showcase the chain of thought from o1-preview on several difficult
> problems below.

------------------------------------------------------------------------

## What we would like to actually work?

-   **Self-Consistency** ([X. Wang et al. 2022](#ref-Wang2022-px))
    Majority voting of LLM output improves a bit.
-   **Scratchpad** ([Nye et al. 2021](#ref-Nye2021-bx)) /
    **Chain-of-Thought** ([Wei et al. 2022](#ref-Wei2022-uj)) Wouldn’t
    it be cool if an LLM could talk to itself and get better?
-   **Tree-of-Thought** ([Yao et al. 2023](#ref-Yao2023-nw)) Wouldn’t it
    be cool if you could scale this as a tree?

## Why might this be possible?

-   **AlphaGo** ([Silver et al. 2016](#ref-Silver2016-ag)) Quantifies
    value of self-play training vs. test search
-   **AlphaZero** ([Silver et al. 2017](#ref-Silver2017-bn)) Shows
    training on guided self-trajectory can be generalized / scaled
-   **Libratus** ([N. Brown and Sandholm 2017](#ref-Brown2017-of)) Poker
    bot built by scaling search
-   **Scaling Laws for Board Games** ([Jones 2021](#ref-Jones2021-di))
    Clean experiments that compare train / test FLOPs in a controlled
    setting
-   **Noam Lecture** ([Paul G. Allen School
    2024](#ref-Paul-G-Allen-School2024-da)) Talk from Noam Brown about
    the power of search

## Can reasoning be a verifiable game?

-   **WebGPT** ([Nakano et al. 2021](#ref-Nakano2021-iz)) Shows that
    test time rejection sampling against a reward model is a very strong
    model.
-   **GSM8K** ([Cobbe et al. 2021](#ref-Cobbe2021-gt)) Considers why
    math reasoning is challenging and introduces ORM models for
    verification
-   **Process Reward** ([Uesato et al. 2022](#ref-Uesato2022-aw))
    Introduces distinction of a process reward / outcome reward model,
    and uses expert iteration RL.
-   **Let’s Verify** ([Lightman et al. 2023](#ref-Lightman2023-cr))
    Demonstrates that PRMs can be quite effective in efficacy of
    rejection sampling
-   **Math-Shepard** ([P. Wang et al. 2023](#ref-Wang2023-ur))
    Experiments with automatic value function learning with roll outs

## Can a verifier make a better LLM?

-   **Expert Iteration** ([Anthony, Tian, and Barber
    2017](#ref-Anthony2017-dm)) Search, collect, train. Method for
    self-improvement in RL.
-   **Self-Training** ([Yarowsky 1995](#ref-Yarowsky1995-tm)) Classic
    unsupervised method: generate, prune, retrain
-   **STaR** ([Zelikman et al. 2022](#ref-Zelikman2022-id)) Formulates
    LLM improvement as retraining on rationales that lead to correct
    answers. Justified as approximate policy gradient.
-   **ReST** ([Gulcehre et al. 2023](#ref-Gulcehre2023-vk)) Models
    improvement as offline-RL. Samples trajectories, grow corpus,
    retrain.
-   **ReST-EM** ([Singh et al. 2023](#ref-Singh2023-eb)) Formalizes
    similar methods as EM for RL. Applies to reasoning.

## Can LLMs learn to plan?

(This part is the most speculative)

-   **Stream of Search** ([Gandhi et al. 2024](#ref-Gandhi2024-vs))
    Training on linearized, non-optimal search trajectories induces
    better search.
-   **DualFormer** ([Su et al. 2024](#ref-Su2024-us)) Training on
    optimal reasoning traces with masked steps improves reasoning
    ability.
-   **AlphaZero-like** ([Feng et al. 2023](#ref-Feng2023-sz)) /
    **MCTS-DPO** ([Xie et al. 2024](#ref-Xie2024-lp)) / **Agent Q**
    ([Putta et al. 2024](#ref-Putta2024-yy)) Sketches out MCTS-style
    expert iteration for LLM planning.
-   **PAVs** ([Setlur et al. 2024](#ref-Setlur2024-ax)) Argues for
    advantage (PAV) function over value (PRM) for learning to search.
    Shows increase in search efficacy.
-   **SCoRE (Self-Correct)** ([Kumar et al. 2024](#ref-Kumar2024-fj))

## Does this lead to test time scaling?

-   **Optimal test scaling** ([Snell et al. 2024](#ref-Snell2024-dx))
-   **Large Language Monkeys** ([B. Brown et al.
    2024](#ref-Brown2024-bs))
-   **Inference Scaling** ([Y. Wu et al. 2024](#ref-Wu2024-mt))
-   **FoT Scaling** ([Z. Bi et al. 2024](https://arxiv.org/abs/2412.09078))

------------------------------------------------------------------------

## Full Bibliography.

Anthony, Thomas, Zheng Tian, and David Barber. 2017. “Thinking Fast and
Slow with Deep Learning and Tree Search.” *arXiv \[Cs.AI\]*.
<http://arxiv.org/abs/1705.08439>.

Brown, Bradley, Jordan Juravsky, Ryan Ehrlich, Ronald Clark, Quoc V Le,
Christopher Ré, and Azalia Mirhoseini. 2024. “Large Language Monkeys:
Scaling Inference Compute with Repeated Sampling.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2407.21787>.

Brown, Noam, and Tuomas Sandholm. 2017. “Libratus: The Superhuman AI for
No-Limit Poker.” In *Proceedings of the Twenty-Sixth International Joint
Conference on Artificial Intelligence*. California: International Joint
Conferences on Artificial Intelligence Organization.
<https://www.onlinecasinoground.nl/wp-content/uploads/2018/10/Libratus-super-human-no-limit-poker-Sandholm-Brown.pdf>.

Chen, Ziru, Michael White, Raymond Mooney, Ali Payani, Yu Su, and Huan
Sun. 2024. “When Is Tree Search Useful for LLM Planning? It Depends on
the Discriminator.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2402.10890>.

Cobbe, Karl, Vineet Kosaraju, Mohammad Bavarian, Mark Chen, Heewoo Jun,
Lukasz Kaiser, Matthias Plappert, et al. 2021. “Training Verifiers to
Solve Math Word Problems.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2110.14168>.

Feng, Xidong, Ziyu Wan, Muning Wen, Stephen Marcus McAleer, Ying Wen,
Weinan Zhang, and Jun Wang. 2023. “Alphazero-Like Tree-Search Can Guide
Large Language Model Decoding and Training.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2309.17179>.

Gandhi, Kanishk, Denise Lee, Gabriel Grand, Muxin Liu, Winson Cheng,
Archit Sharma, and Noah D Goodman. 2024. “Stream of Search (SoS):
Learning to Search in Language.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2404.03683>.

Gulcehre, Caglar, Tom Le Paine, Srivatsan Srinivasan, Ksenia
Konyushkova, Lotte Weerts, Abhishek Sharma, Aditya Siddhant, et al.
2023. “Reinforced Self-Training (ReST) for Language Modeling.” *arXiv
\[Cs.CL\]*.
<https://scholar.google.com/citations?view_op=view_citation&hl=en&citation_for_view=7hwJ2ckAAAAJ:evX43VCCuoAC>.

Jones, Andy L. 2021. “Scaling Scaling Laws with Board Games.” *arXiv
\[Cs.LG\]*. <http://arxiv.org/abs/2104.03113>.

Kazemnejad, Amirhossein, Milad Aghajohari, Eva Portelance, Alessandro
Sordoni, Siva Reddy, Aaron Courville, and Nicolas Le Roux. 2024.
“VinePPO: Unlocking RL Potential for LLM Reasoning Through Refined
Credit Assignment.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2410.01679>.

Kirchner, Jan Hendrik, Yining Chen, Harri Edwards, Jan Leike, Nat
McAleese, and Yuri Burda. 2024. “Prover-Verifier Games Improve
Legibility of LLM Outputs.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2407.13692>.

Kumar, Aviral, Vincent Zhuang, Rishabh Agarwal, Yi Su, John D Co-Reyes,
Avi Singh, Kate Baumli, et al. 2024. “Training Language Models to
Self-Correct via Reinforcement Learning.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2409.12917>.

Lightman, Hunter, Vineet Kosaraju, Yura Burda, Harri Edwards, Bowen
Baker, Teddy Lee, Jan Leike, John Schulman, Ilya Sutskever, and Karl
Cobbe. 2023. “Let’s Verify Step by Step.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2305.20050>.

Nakano, Reiichiro, Jacob Hilton, Suchir Balaji, Jeff Wu, Long Ouyang,
Christina Kim, Christopher Hesse, et al. 2021. “WebGPT: Browser-Assisted
Question-Answering with Human Feedback.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2112.09332>.

Nye, Maxwell, Anders Johan Andreassen, Guy Gur-Ari, Henryk Michalewski,
Jacob Austin, David Bieber, David Dohan, et al. 2021. “Show Your Work:
Scratchpads for Intermediate Computation with Language Models.” *arXiv
\[Cs.LG\]*. <http://arxiv.org/abs/2112.00114>.

Paul G. Allen School. 2024. “Parables on the Power of Planning in AI:
From Poker to Diplomacy: Noam Brown (OpenAI).” Youtube.
<https://www.youtube.com/watch?v=eaAonE58sLU>.

Putta, Pranav, Edmund Mills, Naman Garg, Sumeet Motwani, Chelsea Finn,
Divyansh Garg, and Rafael Rafailov. 2024. “Agent Q: Advanced Reasoning
and Learning for Autonomous AI Agents.” *arXiv \[Cs.AI\]*.
<http://arxiv.org/abs/2408.07199>.

Setlur, Amrith, Chirag Nagpal, Adam Fisch, Xinyang Geng, Jacob
Eisenstein, Rishabh Agarwal, Alekh Agarwal, Jonathan Berant, and Aviral
Kumar. 2024. “Rewarding Progress: Scaling Automated Process Verifiers
for LLM Reasoning.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2410.08146>.

Silver, David, Aja Huang, Chris J Maddison, Arthur Guez, Laurent Sifre,
George van den Driessche, Julian Schrittwieser, et al. 2016. “Mastering
the Game of Go with Deep Neural Networks and Tree Search.” *Nature* 529
(7587): 484–89. <https://www.nature.com/articles/nature16961>.

Silver, David, Thomas Hubert, Julian Schrittwieser, Ioannis Antonoglou,
Matthew Lai, Arthur Guez, Marc Lanctot, et al. 2017. “Mastering Chess
and Shogi by Self-Play with a General Reinforcement Learning Algorithm.”
*arXiv \[Cs.AI\]*. <http://arxiv.org/abs/1712.01815>.

Singh, Avi, John D Co-Reyes, Rishabh Agarwal, Ankesh Anand, Piyush
Patil, Xavier Garcia, Peter J Liu, et al. 2023. “Beyond Human Data:
Scaling Self-Training for Problem-Solving with Language Models.” *arXiv
\[Cs.LG\]*. <http://arxiv.org/abs/2312.06585>.

Snell, Charlie, Jaehoon Lee, Kelvin Xu, and Aviral Kumar. 2024. “Scaling
LLM Test-Time Compute Optimally Can Be More Effective Than Scaling Model
Parameters.” *arXiv \[Cs.LG\]*. <http://arxiv.org/abs/2408.03314>.

Su, Dijia, Sainbayar Sukhbaatar, Michael Rabbat, Yuandong Tian, and
Qinqing Zheng. 2024. “Dualformer: Controllable Fast and Slow Thinking by
Learning with Randomized Reasoning Traces.” *arXiv \[Cs.AI\]*.
<http://arxiv.org/abs/2410.09918>.

Uesato, Jonathan, Nate Kushman, Ramana Kumar, Francis Song, Noah Siegel,
Lisa Wang, Antonia Creswell, Geoffrey Irving, and Irina Higgins. 2022.
“Solving Math Word Problems with Process- and Outcome-Based Feedback.”
*arXiv \[Cs.LG\]*. <http://arxiv.org/abs/2211.14275>.

Wang, Junlin, Jue Wang, Ben Athiwaratkun, Ce Zhang, and James Zou. 2024.
“Mixture-of-Agents Enhances Large Language Model Capabilities.” *arXiv
\[Cs.CL\]*. <http://arxiv.org/abs/2406.04692>.

Wang, Peiyi, Lei Li, Zhihong Shao, R X Xu, Damai Dai, Yifei Li, Deli
Chen, Y Wu, and Zhifang Sui. 2023. “Math-Shepherd: Verify and Reinforce
LLMs Step-by-Step Without Human Annotations.” *arXiv \[Cs.AI\]*.
<http://arxiv.org/abs/2312.08935>.

Wang, Xuezhi, Jason Wei, Dale Schuurmans, Quoc Le, Ed Chi, Sharan
Narang, Aakanksha Chowdhery, and Denny Zhou. 2022. “Self-Consistency
Improves Chain of Thought Reasoning in Language Models.” *arXiv
\[Cs.CL\]*. <http://arxiv.org/abs/2203.11171>.

Wei, Jason, Xuezhi Wang, Dale Schuurmans, Maarten Bosma, Brian Ichter,
Fei Xia, Ed Chi, Quoc Le, and Denny Zhou. 2022. “Chain-of-Thought
Prompting Elicits Reasoning in Large Language Models.” Edited by S
Koyejo, S Mohamed, A Agarwal, D Belgrave, K Cho, and A Oh. *arXiv
\[Cs.CL\]*, 24824–37.
<https://proceedings.neurips.cc/paper_files/paper/2022/file/9d5609613524ecf4f15af0f7b31abca4-Paper-Conference.pdf>.

Welleck, Sean, Amanda Bertsch, Matthew Finlayson, Hailey Schoelkopf,
Alex Xie, Graham Neubig, Ilia Kulikov, and Zaid Harchaoui. 2024. “From
Decoding to Meta-Generation: Inference-Time Algorithms for Large
Language Models.” *arXiv \[Cs.CL\]*. <http://arxiv.org/abs/2406.16838>.

Wu, Tianhao, Janice Lan, Weizhe Yuan, Jiantao Jiao, Jason Weston, and
Sainbayar Sukhbaatar. 2024. “Thinking LLMs: General Instruction
Following with Thought Generation.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2410.10630>.

Wu, Yangzhen, Zhiqing Sun, Shanda Li, Sean Welleck, and Yiming Yang.
2024. “Inference Scaling Laws: An Empirical Analysis of Compute-Optimal
Inference for Problem-Solving with Language Models.” *arXiv \[Cs.AI\]*.
<http://arxiv.org/abs/2408.00724>.

Xie, Yuxi, Anirudh Goyal, Wenyue Zheng, Min-Yen Kan, Timothy P
Lillicrap, Kenji Kawaguchi, and Michael Shieh. 2024. “Monte Carlo Tree
Search Boosts Reasoning via Iterative Preference Learning.” *arXiv
\[Cs.AI\]*. <http://arxiv.org/abs/2405.00451>.

Xie, Yuxi, Kenji Kawaguchi, Yiran Zhao, Xu Zhao, Min-Yen Kan, Junxian
He, and Qizhe Xie. 2023. “Self-Evaluation Guided Beam Search for
Reasoning.” *arXiv \[Cs.CL\]*. <http://arxiv.org/abs/2305.00633>.

Yao, Shunyu, Dian Yu, Jeffrey Zhao, Izhak Shafran, Thomas L Griffiths,
Yuan Cao, and Karthik Narasimhan. 2023. “Tree of Thoughts: Deliberate
Problem Solving with Large Language Models.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2305.10601>.

Yarowsky, David. 1995. “Unsupervised Word Sense Disambiguation Rivaling
Supervised Methods.” In *Proceedings of the 33rd Annual Meeting on
Association for Computational Linguistics -*. Morristown, NJ, USA:
Association for Computational Linguistics.
<https://dl.acm.org/doi/10.3115/981658.981684>.

Yoshida, Davis, Kartik Goyal, and Kevin Gimpel. 2024.
“<span class="nocase">MAP’s</span> Not Dead yet: Uncovering True
Language Model Modes by Conditioning Away Degeneracy.” In *Proceedings
of the 62nd Annual Meeting of the Association for Computational
Linguistics (Volume 1: Long Papers)*, 16164–215. Stroudsburg, PA, USA:
Association for Computational Linguistics.
<https://aclanthology.org/2024.acl-long.855.pdf>.

Zelikman, Eric, Georges Harik, Yijia Shao, Varuna Jayasiri, Nick Haber,
and Noah D Goodman. 2024. “Quiet-STaR: Language Models Can Teach
Themselves to Think Before Speaking.” *arXiv \[Cs.CL\]*.
<http://arxiv.org/abs/2403.09629>.

Zelikman, Eric, Yuhuai Wu, Jesse Mu, and Noah D Goodman. 2022. “STaR:
Bootstrapping Reasoning with Reasoning.” *arXiv \[Cs.LG\]*.
<http://arxiv.org/abs/2203.14465>.

Zhao, Stephen, Rob Brekelmans, Alireza Makhzani, and Roger Grosse. 2024.
“Probabilistic Inference in Language Models via Twisted Sequential Monte
Carlo.” *arXiv \[Cs.LG\]*. <http://arxiv.org/abs/2404.17546>.

Zhenni Bi, Kai Han, Chuanjian Liu, Yehui Tang, and Yunhe Wang. 2024.
“Forest-of-Thought: Scaling Test-Time Compute for Enhancing LLM 
Reasoning.” *arXiv \[Cs.CL\]*. <https://arxiv.org/abs/2412.09078>.
