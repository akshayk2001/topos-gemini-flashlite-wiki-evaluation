# TOPOS Gemini Flash-Lite Wiki Evaluation

This project compares Gemini 3.1 Flash-Lite with standard thinking and extended thinking on the same one-shot coding task: generating a simple React personal wiki from three fixed PDF sources.

The goal is to evaluate whether increased reasoning effort improves code structure, maintainability, and implementation quality when the prompt, source material, and app requirements are held constant.

## Experiment Design

Both model runs use:

- The same Gemini Flash-Lite model family
- The same one-shot prompt
- The same three source PDFs
- The same React/Vite app requirements
- The same evaluation framework: TOPOS

The only intended variable is reasoning effort:

- `wiki-flashlite-standard/` 
- `wiki-flashlite-extended/`

## Source-Grounded Wiki Task

Each model was asked to create a simple React personal wiki app using only these source files:

- `wiki-sources/bollywood_music.pdf`
- `wiki-sources/meditation_article.pdf`
- `wiki-sources/tennis_article.pdf`

The generated app should include default wiki pages based only on those PDFs, plus local editing, search, deletion, and `localStorage` persistence.

## Evaluation With TOPOS

TOPOS evaluates structural code quality beyond basic correctness. In this project, it is used to compare the generated React apps across three quality pillars:

- `SIMPLE`: avoids unnecessary complexity
- `COMPOSABLE`: keeps modules cleanly decoupled
- `SECURE`: avoids known risky code/data-flow patterns

TOPOS awards quality levels based on how many pillars a file satisfies. This makes the comparison more concrete than simply judging which app “looks better.”

## Running the Apps

Navigate to the root project folder:

```bash
cd topos-comparison-project
```
Run the following commands to generate the wiki for both models:
```bash
cd wiki-flashlite-standard
npm install
npm run dev

cd ..
cd wiki-flashlite-extended
npm install
npm run dev
```
