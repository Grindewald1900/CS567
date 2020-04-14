## CS571 - Graph Theory and Algorithms
### Assignment 5
### Group members :
### Yi Ren (002269013)&ensp;&ensp;    Wentao Lu (002276355)  

**Some background**  
With the rapid development of CPU manufacturing technology, it has become more and more difficult to improve the single core performance, that's why CPU manufacturers turned to develop multicore processors. As consequence, people began to put more effort on parallel computing research, which means a problem can be solved by more than one processors simultaneously. In this way, reconfiguration was raised to satisfy the need of this kind of problems. Compared with traditional models, reconfigurable models can make better use of hardware resources, that means the processors could be used to run the tasks when available. As a result, reconfigurable models make it possible to solve the problem in a more efficient and quicker way.

**The Defination of RMBM**

The Reconfigurable Multiple Bus Machine (RMBM), is one of the models for reconfiguration. Compared with R-mesh or even RN, RMBM use multiple buses to communicate with one processor. Suppose we have N processors and M buses in this model, we index the processors from 0 to N-1 and buses from 0 to M-1 (see figure 1).  
We define the switch set to be the intersection of a processor and a bus, because there could be more than one switches in the intersection.  In this way, the RMBM model will have M*N switch sets in total.

<div align=center><img src="http://15.222.11.163/wp-content/uploads/2020/04/RMBM-2-1024x734.png" width="50%" height="50%"></div>  
</br>
<center> Figure 1.  The architecture of RMBM </center>  
</br>

For a single switch, variant kinds of switches could be included.   
● Connect switch: connect a port to the bus, like C(i,j,0) in figure 2, it connect the write port of processor i to bus j.  
● Segment switch: disconnect or segment the bus, which means these switches is used to divide the bus into segments, like S(i,j,0) and S(i,j,1) in figure 2, which segment bus j to three parts.  
● Fuse switch: connect the fuse line to buses. For example, f(i,j) fuse processor i to bus j, if processor i open some other fuse switch such as f(i,j+1) and f(i,j-1), then bus j-1, j and j+1 will be fused together.  
<div align=center><img src="http://15.222.11.163/wp-content/uploads/2020/04/RMBM-3.png" width="50%" height="50%"></div>  
</br>
<center> Figure 2.  The structure of RMBM switch </center>

**Some Variants**  
Generally speaking, RMBM model has two basic functions ,segment and fuse, which is mentioned above. Segment means the processor is able to divide a bus into separate segments while fuse means different buses could be connected.  
Base on segment and fuse, RMBM has four variants.   
● Basic RMBM (B-RMBM), which is non-reconfigurable, just like a PRAM. Connect switch is the only choice to constitute its switch set. In this way, B-RMBM is not able to fuse or segment buses.  
● Segmenting RMBM (S-RMBM), Compared to B-RMBM, it has the segment switch other than connect switch. S-RMBM has the ability to segment but not fuse.  
● Fusing RMBM (F-RMBM), the F-RMBM has both fuse switch and connect switch. F-RMBM is able to fuse buses, however, it cannot segment buses.  
● Extended RMBM (E-RMBM), it has all the three switches mentioned, in this way, E-RMBM has the ability to fuse and segment buses.

**Directed Variants**  

**Problems can be solved**  

**Relation between RMBM and shared memory models**
