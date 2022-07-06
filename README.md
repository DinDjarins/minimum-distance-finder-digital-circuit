
# Distance Minimization Digital Circuit

 A digital circuit that finds minimum distance between multiple room and router locations.

## Task
 - Design a digital circuit to output the room and router location which are closest to each other.
 - Sixteen locations are stored in 7-bit binary form in a .bin file (12 rooms and 4 routers).
 - Only 6 bits represent the location, the rest 1 bit (MSB) is flag bit to differentiate between room and router.   
     
        MSB                         Representation
         1                              Room
         0                              Router

#### Note
 - In case of multiple favourable rooms and router locations, the room should be selected such that its location from the reference position is minimum.

## Approach
 - Given binary file is stored in a ROM.
 - Now counter to ROM is iterated in such a way that it resets when it finds first router location, this router location and it's count value are then stored in registers.
 - Then the adder is fed the stored location of first router and the room locations through ROM (counter is now iterated for all locations but only valid room locations are fed to adder).
 - The distance is then stored to be compared with next distance.
 - The minimum of two distances is stored, which is then compared to next minimum and so on (count value of room location corresponding to minimum distance is also stored).
 - Once all room locations have been compared with first router, the minimum distance of rooms from that router is stored and the counter is iterated again such that it resets when it finds a router location on a count value higher than the previously stored router's count value.
 - Then the adder is fed the stored location of second router and the room locations through ROM (counter is now iterated for all locations but only valid room locations are fed to adder).
 - The distance is then stored to be compared with next distance.
 - The minimum of two distances is stored, which is then compared to next minimum and so on (count value of room distance corresponding to minimum distance is also stored).
 - Once all room locations have been compared with second router, the minimum distance of rooms from that router now is compared to previously stored distance distance of rooms from first router and the counter is iterated again such that it resets when it finds a router location on a count value higher than the previously stored router's count value.
 - The minimum of two is stored, which is then compared to next minimum and so on (count value of room and router locations corresponding to minimum distance are also stored).
 - Finally the count value of the required room and router location are viewed on 7-segment display.

## P.S.
 - Binary file of desired locations can be made by running 'locations.py'.
