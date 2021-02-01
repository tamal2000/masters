
## Challenges 

## how to make AI research to increase power efficient 
momory used by 
- Large memory
- Computation
solution: 
- compression network. mean less neurons by pruning 
- C
- Quantization: 
    - lower the bit of the inputs 
    - memory usage reduce 
    - power consumption reduces
    - Latency reduce 
    - Silicon area??
    - find the tradeoff between performance and cost
- how quantization works?
    - scaling vector and 8bit value 
    - Semmentric quantization
    - Asymmetric quantization 

- Simulate quntization
    - quantization is generally simulate in floating point instead of actually running in integer math. 
    - no dedicated kernael nescsary 
    - find min/max 
    - round(x-min/s)
    - running errors is small so pc or mobile will be similar. 
    - old networks works fine with quantization. 
- quantization aware trining
    - rounding operation doenst ahve a gradient
    - solution: 
        - redefined gradient op as 'straing-trough'
        - random rounding 

- RQ:
    - No data
    - No back propagation 
    - No architecture changes 
- rounding method: 
    - stochastic(best) round up and down. 
    - how to find this: 
        - taylor serise expansion of loss: jakovian and hassine matrix 
        
