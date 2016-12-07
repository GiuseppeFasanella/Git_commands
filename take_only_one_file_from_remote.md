```
git fetch <remote> <branch>
git checkout <remote>/<branch> -- relative/path/to/file/or/dir
```

La cosa migliore da fare e' la seguente:

-->Guarda il tuo branch di partenza: si chiama from-CMSSW_8_0_11 in questo esempio

->Aggiungere la repository remota da cui vuoi copiarti un file

->Creare un nuovo branch in cui checkouti il branch della repository remota

--> Torna al branch di partenza

--> Prenditi il file (o i files) che ti servono


```
git remote add gfasanel_cmssw git@github.com:gfasanel/cmssw.git
git fetch gfasanel_cmssw
git checkout -b Full2016_v1 gfasanel_cmssw/ecal_scale_smear_full_2016_v1
git checkout from-CMSSW_8_0_11
git checkout Full2016_v1 -- EgammaAnalysis/ElectronTools/python/calibratedElectronsRun2_cfi.py
git checkout Full2016_v1 -- EgammaAnalysis/ElectronTools/python/calibratedPhotonsRun2_cfi.py
```
