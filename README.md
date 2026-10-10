# VIP Individual Project Part 2: Beam Design and AI Model Comparison

Compares a SciPy SLSQP optimizer with an iterative AI agent using
llama3.2:1b (Ollama) and gpt-4o-mini (OpenAI API) on a steel beam
mass-minimization problem.

## Setup
1. Install Python 3.10+ and the packages:
   `pip install scipy openai ollama pandas matplotlib`
2. Install Ollama (ollama.com), then run `ollama pull llama3.2:1b`
   and keep Ollama running.
3. Put the provided, unmodified `beam_model.py` in this folder.
4. Set your OpenAI key as an environment variable (never commit it).
   PowerShell: `$env:OPENAI_API_KEY="your-key"`
   Mac/Linux: `export OPENAI_API_KEY=your-key`

## Run
`python USERNAME_beam_ai.py`

Outputs: `USERNAME_beam_ai.csv`, `summary_table.csv`, and `history_*.png`.
The notebook `USERNAME_beam_ai.ipynb` runs the same experiment.

## Settings
- Start design: 50 mm x 80 mm
- 11 proposals per run, 2 runs per model
- Temperature 0.7 for both models
- Same prompt, loop, and validation rule for both models
- Invalid replies are logged and never repaired
- Units: millimeters (the provided function takes mm, although the
  handout says meters)
- Results vary between executions because of sampling temperature