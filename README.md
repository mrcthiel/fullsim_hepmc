### Instructions to run the fullsim with hepmc input

set the release:
cmsrel CMSSW_9_4_13
cd CMSSW_9_4_13/src
cmsenv

clone the repositorie
git clone git@github.com:mrcthiel/fullsim_hepmc.git
scram b -j8

cmsRun GEN-SIM.py nM=1 nE=0 nQ=2
cmsRun step1_DIGIPREMIX_S2_DATAMIX_L1_DIGI2RAW_HLT.py
cmsRun step2_RAW2DIGI_RECO_RECOSIM_EI.py
cmsRun step1_PAT.py


