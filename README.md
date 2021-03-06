# LPD

**February 18, 2022**

This **repository** is a collection of files supporting the research in the paper `Low-Power Deployment of Large Distributed Service Applications on Multiple Clouds` by _Babneet Singh, Ravneet Kaur, Murray Woodside, and John W. Chinneck_ of Carleton University.

This is a **brief guide** to the contents:

1. **104 LQN files:**
   - Found in lqn-model-files.zip.
   - `model_A(\d\d)_case-(\d\d).lqn` is the LQN model generated by `lqngen`.

2. **Model diagrams:**
   - The diagrams for 5 tuning models are in `Appendix B` of `BabneetSinghThesis.pdf`.
   - The 104 model diagrams can be generated by passing the `lqngen` models through `lqn2ps`.

3. **Details about the cloud model:**
   - See `Appendix A` in `BabneetSinghThesis.pdf`

4. **104 graph models:**
   - Found in `lqnverif_final_24Feb21_latest.zip`.
   - `mcad_original.lqn` contains the LPD solution without inter-cloud delays. 
   - `mcad_delay.lqn` contains the LPD solution with inter-cloud delays. 
   - These LQN models can converted to diagrams using `lqn2ps`.

5. **Results Analysis:**
   - Found in `ResultsAnalysis.xlsx` spreadsheet.

6. **LQN tutorial:**
   - Found in `LQN-tutorial.pdf`.

7. **Code:**
   - Found in `cloud_deployment.zip`.
   - Cloud descriptions: in `/cloud_configs`.
   - Server/node descriptions: in `/server_configs`.
   - AppPerfModel (LPD and final bounds): in `/src/ca/carleton/perf/AppPerfModel.java#L1015`.
   - GenCPlexData (takes LPD solution as an LQN model and generates the CPLEX dat file): in `/src/ca/carleton/perf/GenCPlexData.java#L131`.
   - Verifier (generates LQN models for the LPD solution with and without inter-cloud delays): in `/src/ca/carleton/partioner/Verifier.java#L461`. 

8. **Cplex:**
   Found in `cplex_lpd.zip`.
   - `mcad.mod`: CPLEX (MIQP) model for LPD (minimizes power while satisfying RT).
   - `mcad_rt.mod`: CPLEX (MIQP) model for minimizing inter-cloud network delay.
   - `mcad_first_feasible.mod`: CPLEX (MIQP) model for LPD but only reports the first feasible solution.
