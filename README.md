TokenThrift 🪙
1 prompt = up to -76% output tokens. 5x shorter replies, 4x cheaper convos. Any language in → English slang out.
📸 Before / After
❌ Without TokenThrift	✅ With TokenThrift
before<img width="1639" height="954" alt="Screenshot 2026-08-30 230428" src="https://github.com/user-attachments/assets/4fff2b07-0915-4732-9329-78ede15667df" />
<img width="1636" height="952" alt="Screenshot 2026-08-30 230434" src="https://github.com/user-attachments/assets/f18a97fa-665b-44b3-85b3-00ebdaba939d" />




after<img width="1625" height="932" alt="Screenshot 2026-08-30 230348" src="https://github.com/user-attachments/assets/59a15764-21c9-49a8-9dcf-60243afd5277" />

Same model. Same question. Same answer — 60% fewer tokens.

💸 The problem: you pay for filler
LLMs are paid chatterboxes. Every "Certainly! Let me explain...",every "In conclusion", every polite apology is a token you boughtand never wanted.

Worse: on most APIs output tokens cost 3–5× more than input tokens.Verbose replies are literally the most expensive part of your bill.

⚙️ How it works
One system prompt. Paste it once, done. It forces any model to:

Reply in compressed English internet slang (u, tbh, np, w/, 2, 4...)
Drop articles, greetings, filler, intros, apologies
Answer in max 1–3 lines, straight to the point
Always output English — whatever language you type in
🧠 Why it works (the math)
Slang = compression. "as soon as possible" → "asap" (4 tokens → 1)."for you" → "4u". Symbols and numbers are single tokens.
Fewer tokens, less money. Typical reply: 100–150 tokens.TokenThrift reply: 15–30. That's your -76%.
The asymmetry pays you back. Output costs 3–5× input →shorter replies save disproportionate money.
Locally, it's also faster. Generation is sequential:5× fewer tokens ≈ 5× faster replies.
🎯 Compatibility — which model, which version
Your model	Version to use	Expected result
7B–30B, community merges	tokenthrift-full.txt (~500 tok)	Works. Weakest models may garble slang
30B+ / frontier (Qwen3, Gemma 3, Llama...)	tokenthrift-compact.txt (~270 tok)	Clean output, max savings
Tested on: prism-ml/bonsai-27b (LM Studio) ✅
Works in: any UI with a system prompt slot — LM Studio, Open WebUI, SillyTavern, API wrappers
Setup: paste as system prompt (not in chat!) → new chat → temp 0.4–0.7 → reasoning OFF.

🤔 Why you should use it
You call APIs → every conversation gets ~4x cheaper after 2 replies
You run local models → replies arrive ~5x faster
You multilingual-chat → one consistent English output, any input
You hate walls of text → finally, answers that respect your time
One paste. Zero config. -76% tokens. ⭐ Star it, thrift it.
