BigReactors Controller
======================
This LUA script takes advantage of [parallel](http://www.computercraft.info/wiki/Parallel_(API)) coroutines to control the several aspects of a BigReactors setup.  
It provides minimal status reporting to a connected monitor (turbine energy buffer &Delta; in RF/t).

The following hysteresis values are hardcoded for optimal performance:
- turbine inductor [turbine energy buffer capacity]: on = 10%, off = 90%
- reactor state [turbine rotor speed]: on = 1750 RPM, off = 1850 RPM
- control rod raising [reactor casing temperature]: begin = 100ºC, end = 120ºC

A shut-off mechanism is set to trigger when the fuel level is less or equal than 4000 mB.  
When triggered, the turbine inductor is disengaged and all control rod levels are set to 100%.  
This reset procedure also occurs when the script begins execution.

As a precaution, the max flow rate on the turbine should be set to less than 1000 mB/t.  
Manual refuelling during active operation is discouraged.
