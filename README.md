# MPC


### Model  

1. State: x,y,psi(orientation),verocity  
2. Actuator: delta(handling), a(accel/break)  
3. update equations:  
        xt+1 = (xt + vt * cos(psit) * dt);  
        yt+1 = (yt + vt * sin(psit) * dt);  
        psit+1 - (psit + vt * deltat / Lf * dt);  
        vt+1 = (vt + at * dt);  


### Timestep Length and Elapsed Duration (N & dt)  

I selected N = 20 and dt = 0.05,  
N >> 20 or dt >> 0.05, line shape sometimes tangled.   
N << 20 or dt << 0.05, line is so prediction is so short and handling is unstable.    


### Polynominal 

I chose 3-order polynominal in order to take advantage of derivative cost culculation (smooth fitting & ocilation adjustment).  

### MPC with Latency  

I put 1 dt latency to ajust index in fg vector for state values.




