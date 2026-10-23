# Local Setup (Run Without a Cloud Account)

Use this guide if you need candidate data to stay on your own computer. It uses a local model runner, so no conversation leaves your machine.

## What You Need
- A computer with enough memory for a mid-size model (16 GB RAM is a practical minimum; more is better)
- [Ollama](https://ollama.com) or [LM Studio](https://lmstudio.ai), either one
- A model that handles long context. Check the model card for the context window before you choose. The knowledge files together are roughly 20,000 words.
- The files from this repository

## Option A: LM Studio (Simplest, Graphical)
1. Install LM Studio and download a model from its search screen. Choose one with a long context window.
2. Open a new chat. In the settings panel, set **Context Length** high enough for the knowledge files (start with 32,768 tokens).
3. Paste the full contents of `instructions/system-prompt.md` into the **System Prompt** box.
4. Paste the contents of every file in `knowledge/` (including the `01-question-bank/` folder) into the same box, under the instructions. Put a heading above each file's text so the model can tell them apart.
5. Start the chat. The assistant opens the assessment as soon as the candidate says hello.

## Option B: Ollama (Command Line)
1. Install Ollama and pull a model:
   ```
   ollama pull <model-name>
   ```
2. Create a file called `Modelfile` in the repository folder with this content:
   ```
   FROM <model-name>
   PARAMETER num_ctx 32768
   SYSTEM """
   (paste instructions/system-prompt.md here, then the knowledge files)
   """
   ```
3. Build and run it:
   ```
   ollama create intake-assessment -f Modelfile
   ollama run intake-assessment
   ```

Build the `Modelfile` with a script rather than by hand if the knowledge files change often. Keep the file in the `.gitignore` if it contains a real evaluator password.

## Check It Works
- The assistant should greet the candidate and ask for a name.
- It should never say an answer is right or wrong.
- It should address the candidate as "sir."
- If it starts teaching, or gives answers, stop and check that the instructions were pasted in full.

## Privacy Notes
- Local runners keep your prompts and responses on your machine by default, but check the settings of any interface you add on top.
- Store candidate transcripts and scoring reports outside the repository, or in the folder the `.gitignore` already excludes.
- Keep the evaluator password out of any file you share.

## Troubleshooting
| Problem | Likely cause | Fix |
|---|---|---|
| Assistant forgets the questions partway through | Context window too small | Raise the context length setting |
| Assistant ignores the "sir" rule or the no-feedback rule | Instructions cut off | Re-paste the full system prompt, instructions first |
| Responses are very slow | Model too large for your memory | Choose a smaller model |
