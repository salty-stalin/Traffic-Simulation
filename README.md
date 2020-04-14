""" Traffic Simulation Code of a 4x4 grid based on stochastic kinetic theory model

array car1 holds properties of each car [x-position,y-position,velocity,lane,direction]

each road is represented by an array where each cell is either 1 or 0 has a car or doesnt have a car





direction representation                        0==UP    
                                 2==LEFT                3==RIGHT
                                               1==DOWN 
Lane arrays: 

   0=↑ 6=↓             1=↑ 7=↓                 2=↑  8=↓
    
    
                         9=←                                   
                         3=→


                        4=→
                        10=←
                        
                        
                        5=→
                        11=←
                        
                        
                        
                        
The motion of car is treated separately and as follows:

1. Each car wants to drive at the speed limit and so if velocity of car (V) is below the speed limit V max; V is increased by 1 

2. Cars drive in either positive/negative x−direction or positive/negative y−direction and they don’t want to hit the car in front. 
If a car is at position i and the car in front is at site i + d then if V ≥ d, V is set equal to d −1. 
This stops the cars from accelerating and hitting the car in front 

3. Unexpected events cause slowing down. This is a random component that is intended to model external inﬂuences, such as what is happening
 on the other carriageway, or just irrational behaviour by drivers. If V > 0 then, with a probability P, V is reduced to V −1. 
 There is also constant standing chance of a total car breakdown where V is set to 0, this has 1% of occurring. 
 All of this happens after V has been updated by the ﬁrst two rules. 4. Each vehicle is moved forward V places, using the new value of V
 
When approaching cross roads:
    
1. Ifacarhasapproachedthecrossroads,ithastostop (V = 0) atthe”trafﬁclightposition” a position just before the center of cross roads. 

2. When the car has stopped it has to decide where to go, this is done randomly
 
3. When the car has decided its direction and it is the cars turn to drive it will check if the position it wants to go to is occupied. If it is occupied the car waits at its current position and ends it turn of movement. If the position is unoccupied the car goes to that position.
                        
                        
                        
                        
                        
