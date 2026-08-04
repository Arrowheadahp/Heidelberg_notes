Outline of the most used canny edge detector:
1. Calculate robust Gradient image using [[Edge Detection]]: $D_x*G*I,D_y*G*I$
2. Find edge points (edgels): using [[Non-Maximum Suppression]]
3. Link up neighbouring edge points to get chains: 
4. Perform hysteresis to clean up chains

Humans perceive edges very differently where edges depends on the semantic 