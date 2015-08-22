# surveyStrategy
Evaluation of the LSST cadences

We have a multi-pronged attack in evaluating LSST capabilities in discovering NEOs. One of those approaches is to evaluate the completeness of various observing strategies (opsim runs, essentially), under various assumptions of MOPS behavior. So this is basically: 
- start with a mock NEO population (this can be small or large -- a small population can be 'cloned' in H distribution to still give an approximate efficiency for detections). Requirements:
  + appropriate orbit distribution
  + appropriate H distribution 
  + appropriate color distribution
  + approximate lightcurve distribution
- propagate this population through an OpSim run, generating the 'observations' that these objects would receive
  + add trailing losses (calculate traditional SNR losses and 'detection' losses due to point-source detection algorithms)
  + add LSST camera footprint
  + add probability of detecting an object in a particular visit (apply m5)
  + convert 'V' magnitude of observation (determined from Hv and g of the object in the population model, combined with distance and phase angle) into a magnitude in the filter of the observation
- using the series of observations of each object to determine
  + whether an object is detected (under various assumptions of MOPS performance)
  + the arc length of "usable" observations
  + whether or not a color of the object can be determined
  + any other characterization properties? 
  + key metric: completeness @ H=22
