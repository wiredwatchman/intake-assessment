# Multicraft Technician Intake Assessment

An AI-run technical and personality assessment for skilled-trades candidates. It tests across electrical, PLC and controls, hydraulics, pneumatics, mechanical, CNC and robotics, network communications, and safety. It also looks at teamwork, communication, and accountability.

The assistant never tells a candidate whether an answer is right or wrong. It asks follow-up questions, so the candidate's reasoning shows.

- **Length:** 45 to 60 minutes
- **Questions:** 35 to 50 across three phases
- **Built for:** Automotive manufacturing, adaptable to other industrial settings (power plants, water treatment, food processing, data centers)

## Quick Start
1. Create a Claude Project.
2. Paste `instructions/system-prompt.md` into the project instructions.
3. Upload the files in `knowledge/` as project knowledge.
4. Replace `(Your Company)` with your organization's name.
5. Start a chat in the project.

Full details are in [`docs/how-it-works.md`](docs/how-it-works.md).

## Contents
```
instructions/   The assistant's instructions
knowledge/      Company context, question bank, scoring rubric
docs/           How it works, changelog
```

## Privacy and Security
- **Keep the evaluator password private.** Anyone who has it can read full candidate evaluations. The repository ships with a placeholder.
- **Review the company context** before publishing. Remove any internal system names or details you don't want public.

## Running It Locally
The same instructions and knowledge files can be used with a local model runner such as Ollama or LM Studio, for teams that need data kept on-premises. See `docs/` for notes (to be written).

## Video
[Link to YouTube video: ADD LINK]

## License
See [LICENSE](LICENSE).
