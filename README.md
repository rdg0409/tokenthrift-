TokenThrift 🪙
1 prompt = -96% output tokens, ~80% cheaper replies. Any language in → English slang out.
📸 Before / After (real test)
Same model (prism-ml/bonsai-27b). Same question: "qual è la differenza tra TCP e UDP?"

❌ Without TokenThrift. The answer is so long it takes 2 screenshots:

before-1before-2
✅ With TokenThrift. One line:

after
503 in / ~650 out → 503 in / 22 out. Same info, same input cost, -96% output tokens.

💸 The problem: you pay for filler
LLMs are paid chatterboxes. Every "Certamente! Ecco una spiegazione...",every "In conclusione", every polite intro is a token you bought and never wanted.

Worse: on most APIs output tokens cost 3–5× more than input tokens.Verbose replies are literally the most expensive part of your bill.

⚙️ How it works
One system prompt. Paste it once, done. It forces any model to:

Reply in compressed English internet slang (u, tbh, np, w/, 2, 4...)
Drop articles, greetings, filler, intros, apologies
Answer in max 1–3 lines, straight to the point
Always output English, whatever language you type in
🧠 Why it works (real numbers, not theory)
Test: "qual è la differenza tra TCP e UDP?" — bonsai-27b, LM Studio.

Input	Output	Total
Default	503	~650	~1,150
TokenThrift	503	22	~525
-96% output tokens — the expensive ones: APIs price output 3–5× input
~80% cheaper per reply — input cost is identical to default:this model ships with a ~500-token built-in system prompt, TokenThrift replaces it at the same price
~30× faster locally: generation is sequential. 650 → 22 tokensgenerated is the whole difference in perceived speed.
🎯 Compatibility: which model, which version
Your model	Version to use	Expected result
7B–30B, community merges	tokenthrift-full.txt (~500 tok)	Works. Weakest models may garble slang
30B+ / frontier (Qwen3, Gemma 3, Llama...)	tokenthrift-compact.txt (~270 tok)	Clean output, max savings
Tested on: prism-ml/bonsai-27b (LM Studio) ✅ -96% output tokens
Works in: any UI with a system prompt slot. LM Studio, Open WebUI, SillyTavern, API wrappers
Setup: paste as system prompt (not in chat!) → new chat → temp 0.4–0.7 → reasoning OFF.

🤔 Why you should use it
You call APIs → every reply gets up to 96% cheaper
You run local models → replies finish up to 30× faster
You multilingual-chat → one consistent English output, any input
You hate walls of text → answers that respect your time
One paste. Zero config. -96% tokens. ⭐ Star it, thrift it.

License
MIT — do whatever you want, just don't sue me.
