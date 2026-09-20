# Run-ready exercise package

This copy was adjusted so the exercise notebooks can be run by students without deliberately incomplete Python cells stopping execution.

## What was changed

- Filled executable `TODO` / `...` implementation placeholders and removed `NotImplementedError` blockers while preserving the original equations, datasets, model architectures, training recipes, and learning sequence.
- Kept the original exercise prompts and `TODO` comments as learning cues; report/reflection prose is still for students to complete.
- Added a short “Run-ready course copy” note to notebooks that previously contained executable student placeholders.
- Corrected the Ex03 Colab setup so `Ex_3_core.py` is fetched from the public `DL-for-Engineers-Public-Course` repository without requiring a private GitHub token.
- Filled the three Ex03 loss-weight choices exactly as instructed by that notebook: data-only `(1,0,0)`, PINN `(1,10,10)`, and physics/IC-only `(0,100,100)`.
- Wrapped the deliberate Ex01 traceback demonstration so it still shows the expected error but does not stop **Run all**.
- Fixed the Ex05 GNN prediction variable mismatch (`pred` / `pred_gnn`) that caused a `NameError` in the plotting cell.
- Made Ex09.1, Ex09.2, and Ex10.1 control/sweep notebooks self-contained by including the residual/loss functions they previously asked students to paste from notebook 01.
- Adjusted the deterministic Ex10.2 button-cell noise check from a 3-sigma to a 4-sigma worst-point tolerance; the seeded sample produces about 14.5 mV maximum error for 4 mV noise, so the previous 12 mV cutoff stopped a correct run.
- Made optional PDF export cells fail gracefully if `markdown`/`weasyprint` cannot be installed in a runtime.
- Made the PyBaMM comparison notebook attempt installation automatically and skip the optional comparison cleanly if PyBaMM is unavailable.
- Added missing notebook cell IDs for better compatibility with current/future Jupyter/Colab validation.

## Validation performed

- Static syntax validation across all notebooks.
- Verified there are **no executable `NotImplementedError` blockers** and **no unresolved `...` placeholders** left in code.
- Executed the complete Ex01 notebook set successfully.
- Executed Ex02 environment/tensor/autograd notebooks successfully; the long training notebook was not used as a full-duration timing test.
- Executed Ex04 notebook 01 successfully.
- Executed Ex05 environment, CNN, and graph-basics notebooks successfully, and smoke-tested the GNN notebook after fixing its variable-name issue.
- Executed Ex06 notebook 01 successfully.
- Executed Ex10.2 notebook 01 successfully after the tolerance correction.

## Important runtime note

Several training-heavy PINN/GNN notebooks are intentionally computationally expensive. “Run-ready” means the code is complete and structurally executable; it does not mean every notebook will finish quickly on CPU. Colab GPU/CPU choice and package availability can change runtime substantially.

Sequential report notebooks may require result files produced by earlier notebooks, exactly as described in their existing instructions.
