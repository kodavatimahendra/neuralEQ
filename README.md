## Instructions to run the Matlab Scripts
The Matlab scripts for the Neurally controlled graphic equalizer can be found in the folder NGEQscripts. The folder includes the following files:

    - GEQfilter.m
    - NGEQ_MatlabNetworkObj.mat
    - NGEQ_parameters.mat
    - NGEQ.m 
    - NGEQfilterAudio.m
    - pareq2.m
    - plotNGEQ.m

### Run the example
To run an example design of the neurally controlled graphic equalizer, run the file `plotNGEQ`, which designs and plots the EQ with given user-set target gains (zig zag by default).

The script uses `NGEQ`, which loads the neural net parameters (`NGEQ_parameters`), to run the filter optimization calculation. Then the `GEQfilter` takes these optimized filter gains and designs the needed equalization band filters using `pareq2`.

### Other matlab files
`NGEQ_MatlabNetworkObj` includes Matlab's net object that has all the required information for Matlab to run the neural network. To use the net object, just give the object the user-set target gains and it outputs the optimized filter gains, e.g., 

```matlab
filterGains = net(12*ones(10,1)).
```

`NGEQfilterAudio.m` can be used to filter audio by giving it the input audio sample and the user-set target gains.

```matlab
out = NGEQfilterAudio(in,targetGains).
```
