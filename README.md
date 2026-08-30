TokenThrift 🪙
y pay 4 filler wen 1 line do trick

Keep ur model. Same brain. Less tokens.

-96% output tokens in a real test (prism-ml/bonsai-27b, LM Studio) — full receipts below.

See it · Files · Setup · Why it works · Compatibility · Honest numbers · License

See it
Same model. Same question: "qual è la differenza tra TCP e UDP?"

🗣️ Normal model — ~650 tokens	TokenThrift — 22 tokens
The answer is so long it takes 2 screenshots	One line
before<img width="1636" height="952" alt="Screenshot 2026-08-30 230434" src="https://github.com/user-attachments/assets/12fb87d4-e572-448f-a14d-21c75ba05c89" />
<img width="1639" height="954" alt="Screenshot 2026-08-30 230428" src="https://github.com/user-attachments/assets/e189d7f3-7819-46c2-ac4e-3e4c86083bda" />

after<img width="1625" height="932" alt="Screenshot 2026-08-30 230348" src="https://github.com/user-attachments/assets/d62c0b32-022b-4d93-a797-9c983814da19" />


503 in / ~650 out → 503 in / 22 out. Same info. Italian in, compressed English out.

Files
Two versions. Pick one.

File	Prompt cost	For
tokenthrift-full.txt	~500 tok	Small models (7B–30B, community merges): they need the examples
tokenthrift-compact.txt	~270 tok	Strong models (Qwen3, Gemma 3, Llama...): cleaner output, lower overhead
Setup
1. copy the .txt2. paste as SYSTEM PROMPT (not in chat!)3. new chat4. temp 0.4–0.7 · reasoning OFF
Works in any UI with a system prompt slot: LM Studio, Open WebUI, SillyTavern, API wrappers.

Why it works
slang = compression. "as soon as possible" → "asap" (4 tokens → 1). "for you" → "4u". symbols & numbers are single tokens.
output is the expensive part. APIs price output 3–5× input. shorter replies save disproportionate money.
generation is sequential. locally, 30× fewer tokens generated ≈ 30× faster replies.
any language in → English slang out. one consistent output, whatever you type.
Compatibility
Your model	Version	Expected
7B–30B, community merges	full	works; weakest may garble slang
30B+ / frontier	compact	clean, max savings
Tested on: prism-ml/bonsai-27b (LM Studio) ✅

Honest numbers
Important. TokenThrift only shrinks output tokens.

the prompt itself costs ~500 (full) / ~270 (compact) input tokens per conversation
input savings: zero. it replaces the model's default system prompt, it doesn't remove it
on already-terse tasks savings shrink; on verbose tasks they explode
the -96% above is one real test, one model, one question engineered to elicit verbosity — your mileage varies by model and workload
Real win: readability + speed. Cost savings are the bonus. Want your own numbers? Run a before/after with your prompts and check the token counters.

Why u should use it
u call APIs → output is the expensive part
u run local → replies finish up to 30× faster
u multilingual-chat → consistent English out, any input
u hate walls of text → answers respect ur time
1 paste. 0 config. ⭐ star it, thrift it.

README Inspired by caveman — go star that too (https://github.com/JuliusBrussee/caveman).

License
MIT — do whatever, don't sue.
