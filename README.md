# <img src="https://github.com/Naam/ESPIE/blob/master/espie.jpg" alt="espie image"/>

ESPIE act as an SPI flash chip emulator. ESPIE helps in reducing testing time
iterration using emulation for the reprogrammation phase of the chip.

How does it works?
----------------------
Using a FPGA board (currently [De0-Nano](https://www.terasic.com.tw/cgi-bin/page/archive.pl?Language=English&No=593))
ESPIE exposes one one side an SPI slave that one connect to the master and on
the other slide a medium to communicate with a computer daemon. This daemon
handle the code synchronization between the current computer version and
on-chip one.

Use case: Serial flash memory with socket.
------------------------------------------
<table>
<tr>
<td>
Let's say one have a flash memory on a socket like the following
picture, once one wants to test the code the following step should normally be
done:
</td>
<td>
<img src="https://github.com/Naam/ESPIE/blob/master/example.png" alt="example image" width="100%"/>
</td>
</tr>
</table>
    
1. Code                         
2. Unplug the chip
3. Plug the chip on the programmer (e.g [bus pirate](http://dangerousprototypes.com/docs/Bus_Pirate))
4. Flash the chip
5. Replug the chip on the board
6. Goto 1 if needed

This workflow implies a lot of manual processing, hence time consuming and
potentially dangerous for chip's health. That's why by abstracting those steps
one would gain some precious testing time. Now one would simply:

1. Plug the FPGA to the SPI socket.
2. Plug the FPGA to the PC
3. Run the dameon
4. Code
5. Reset the board
6. Goto 4 if needed




