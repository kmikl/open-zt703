# Port expanders

Chip 1 (low 8 bits): 
- Qa --> channel 2 4051/S0 
- Qb --> channel 2 4051/S1 
- Qc --> channel 2 4051/S2 
- Qd --> channel 1 4051/S0 
- Qe --> channel 1 4051/S1 
- Qf --> channel 1 4051/S2 
- Qg --> channel 2 range switch relay 
- Qh --> channel 1 range switch relay 

Chip 2 (high 8 bits): 
- Qa --> SGM3157/IN, switch ADC channel B to CH1(NO) or CH2(NC) 
- Qb --> ADC/DFS 
- Qc --> ADC/S1 
- Qd --> ADC/S2 
- Qe --> keep main power on 
- Qf --> VPS8504/EN, enable DMM power 
- Qg --> SL6SC/EN, enable charge pump (-3V) CH1 or CH2? 
- Qh --> SL6SC/EN, enable charge pump (-3V) CH1 or CH2? 

The channels may be mixed up, did not test them yet.
