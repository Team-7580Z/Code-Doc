# Odemntry 

---
description: Postion Tracking other wise reffered to as odemntry is how a robot can figure out its exact location. Our team uses this in our auton to get the robots location and then uses a motion planing algriothm to go to a spot we told it to. 

As you countine to read about it keep in mind that our team used tracking wheels in our drive train.
---

## Benifits of Odemntry

Odemntry has the potential of giving your robots many benifts. One of these is if used with tracking wheels you can have a extemly precise postion. The next benift of this is that when used with a simple control loop you can have your robot correct for its mistakes made ealier. 

## Example of Odmntry
Our code devloped our code using help from 205X Programming Annoted Video and 5005X's odmenty paper

1. First we need to get the encoder values
                    
        lPos = ltracking.get_value();
        rPos = rtacking.get_value();
        sPos = stracking.get_value();

2. Now we need to get the diffrence between the current tracking values and the previous one

        LDelta = lPos - LPrevPos;
        RDelta = rPos - RPrevPos;
        SDelta = sPos - SPrevPos;
3. Now we can update the previous encoder values

        LPrevPos = lPos;
        RPrevPos = rPos;
        SPrevPos = sPos;
4. Now we need to get the distance moved
        
        LDistDistance = LDelta * Lwheeldistance;
        RDistDistance = RDeta * RWheelDistance;
        SDistDistance = SDelta * SWheeelDistance;
5. Now we need to get the change in angle
        deltaA = (LDistDistance + RDistDistance)/(LeftDistance+RightDistance);
6. If the angle did not change at all we just set the x and y coordinates with the distance the tracking wheels rotated

        if (deltaA == 0) {
            localX = SDistDistance;
            localY = LDistDistance;
        }
        