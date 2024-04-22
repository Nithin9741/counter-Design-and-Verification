# counter MOD-12 Design-and-Verification

![image](https://github.com/Nithin9741/counter-Design-and-Verification/assets/101901668/e7f0f258-c6e2-4dde-92b8-9a8fc720097b)

An active high-loadable up/down counter is a digital circuit programmed to count up or down based on user input. The counter can be loaded with an initial value, which sets the starting point for counting.      
When counting up, the counter increments by one on each clock cycle, and when counting down, the counter decrements by one on each clock cycle. The direction of counting is determined by a control signal, which can be set to either "up" or "down" mode.

![image](https://github.com/Nithin9741/counter-Design-and-Verification/assets/101901668/a9bdc65f-ff4b-42a2-bee1-34317e6f9126)

 # Features:
• Reset      
• Mode         
 ❖ UP: Increment by one on each clock cycle.       
 ❖ DOWN: Decrement by one on each clock cycle.     
• Load    
• Datain     
 ❖ When Load is high, Counter can be loaded with the initial value dat in, which sets the starting point for counting.
• Dataout

# ❖ Strategies:

• Reset    
 ❖ Reset should be distributed such that low value should occur number of times than high.     
 ❖ Reference Model: if reset is “1” then output variable made equal to “0”.         
• Load      
 ❖ Load should be distributed such that low value should occur number of times than high.      
 ❖ Reference Model: If the Load is high output variable should be datain.       
• Mode      
 ❖ Mode can be equally distributed.        

 # ❖ Reference Model:        
 
 ▪ UP: if mode is high then if output variable is “11” then output variable made equal to “0” otherwise increment by “1”.
 ▪ DOWN: if mode is low then if output variable is “0” then output variable made equal to “11” otherwise decrement by “1”.
 • Datain
 ❖ Datain is randomized such that value of datain should be in the range of 0 to 11.
 • Dataout
 ❖ Score board: Dataout is compared with the output variable in reference model.

# ❖ Transaction:

• Random: Reset, Mode, Load, Datain Transactors:    
• Generator: Generates random transaction.     
• Driver: Drives Reset, Load, Mode and Datain signals.     
• Monitor: collects the Dataout and random transactions.      
• Reference Model: Mimic the design inside the environment from transaction data which is collected in the monitor.    
• Scoreboard: Compares the data in reference model and Dataout generated in the design and generates coverage.   

# ❖ Coverage Model:

• Reset {implicit bins}   
• Load {implicit bins}    
• Mode {implicit bins}     
• Datain {explicit bin [bin range [0:11]]}   
• Dataout {explicit bin [bin range [0:11]]}   
• Load X Datain   
• Mode X Load X Datain    

# ❖ Call backs:       

• Scoreboard : Callback triggers the coverage model      
