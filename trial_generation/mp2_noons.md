# Using MP2 NOONs to Generate Active Space

_NOTE: Please use the **latest** example input file on whichever branch you are on_
1. Checkout the branch `mp2_noons` on Pynterface.
2. In the input script, set `mp2_dryrun` to `True`, and `psit` to `"rcas"`. 
3. Run the calculation. As of the moment, selection of active space based on MP2 NOONs is done manually by the user. Pynterface will exit after the MP2 calculation, and produce 2 files `mp2_noons.csv`, which is a 1-D array of the MP2 NOONs in descending order, and `mp2_nos.csv`, the corresponding MP2 NOs. User can examine the NOONs and choose a cutoff threshold for the desired active space size. Note that if the system is open shell, the RHF object will be cast to a UHF object and UMP2 will be performed instead of RMP2.
4. Run the CAS/HCI(SCF) calculation with the chosen active space, and make sure to read in `mp2_nos.csv` as initial guess for the CAS/HCI(SCF) calculation (set `cas_read_csv = True` and `mos_csv_file = mp2_nos.csv` or whatever name you changed the MO csv file to).