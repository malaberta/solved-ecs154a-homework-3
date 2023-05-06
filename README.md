Download Link: https://assignmentchef.com/product/solved-ecs154a-homework-3
<br>
<h1>Problem 1: UpDownCounter.circ</h1>

Implement a 3 bit synchronous up/down counter that stops counting when it reaches the minimum/maximum count. For example, if the count is at 111 and you are told to count up you should stay at 111. Or if you were at 000 and told to count down you should stay at 000.




<strong>CountUpIn and CountDownIn in will never both be 1 at the same time.</strong>




This circuit should be constructed as a <strong>Moore</strong> Model Machine

<h2>Inputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">EnableIn</td>

   <td width="208">1</td>

   <td width="208">Connect to the enable port of your registers/flip-flops. When 1 your circuit works normally. When 0 your circuit does nothing.</td>

  </tr>

  <tr>

   <td width="208">CountUpIn</td>

   <td width="208">1</td>

   <td width="208">Increase the count by 1 unless you are at 111.</td>

  </tr>

  <tr>

   <td width="208">CountDownIn</td>

   <td width="208">1</td>

   <td width="208">Decrease the count by 1 unless you are at 000</td>

  </tr>

  <tr>

   <td width="208">clkIn</td>

   <td width="208">1</td>

   <td width="208">Connect this to the clock ports of your registers/flip-flops. Do nothing else with this.</td>

  </tr>

 </tbody>

</table>




<h2>Outputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">Count</td>

   <td width="208">3</td>

   <td width="208">The current value of the counter</td>

  </tr>

 </tbody>

</table>




<h1>Problem 2: FourBitParity.circ</h1>

Build a <strong>Moore </strong>Model circuit that calculates the even parity over a <strong>group of 4 bits</strong>. You will receive 1 bit of input at a time. The circuit should output a 1 if after receiving the last bit in the group there were an even number of 1’s in the group and a 0 at all other times. 0000 is considered to be an even number of 1’s.

This is not a sliding window problem but instead a chunk based problem. This means instead of looking at the last 4 bits received you look at the first group of 4 bits, then the second group of 4 bits, then the third group of 4 bits, etc.

<h2>Example Input and Output</h2>

Input:    0111 1000 1010 1100

Output: 0000 0000 0000 1000 1

If the output looks like it “is delayed one clock cycle” that is because you are building a Moore Model Machine and the output of a Moore Machine cannot change until the next rising clock edge because its output depends on state only.

<h2>Inputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">EnableIn</td>

   <td width="208">1</td>

   <td width="208">Connect to the enable port of your registers/flip-flops. When 1 your circuit works normally. When 0 your circuit does nothing.</td>

  </tr>

  <tr>

   <td width="208">InputBitIn</td>

   <td width="208">1</td>

   <td width="208">The current bit being input into your circuit.</td>

  </tr>

  <tr>

   <td width="208">ClkIn</td>

   <td width="208">1</td>

   <td width="208">Connect this to the clock ports of your registers/flip-flops. Do nothing else with this.</td>

  </tr>

 </tbody>

</table>




<h2>Outputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">IsEvenOut</td>

   <td width="208">1</td>

   <td width="208">1 if there were an even number of 1’s in the last group of 4 bits and 0 otherwise.</td>

  </tr>

 </tbody>

</table>







<h1>Problem 3: Vending.circ</h1>

Implement a <strong>Mealy</strong> model circuit to control a coin-operated vending machine. This machine only accepts quarters, dimes, and nickels. Coins are inserted until a total of 30 cents or more is deposited. <strong>Only 1 coin is deposited at a time</strong>. Once a total of 30 or more cents has been deposited your circuit should set Give_Mechandise to 1 to dispense the product in the vending machine. You should also set the change outputs for the circuit to give back the appropriate amount of change. Assume that the machine can give one dime and/or nickel back. If the customer does something silly like entering a quarter followed by a quarter (total of 50 cents), correct change does not have to be provided (20 cents) but the maximum amount of change should be given (15 cents). Note that only 1 input can be high at a time.




<h2></h2>

<h2>Inputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">EnableIn</td>

   <td width="208">1</td>

   <td width="208">Connect to the enable port of your registers/flip-flops. When 1 your circuit works normally. When 0 your circuit does nothing.</td>

  </tr>

  <tr>

   <td width="208">QuarterReceived</td>

   <td width="208">1</td>

   <td width="208">1 if the user entered a quarter into the machine and 0 otherwise</td>

  </tr>

  <tr>

   <td width="208">DimeReceived</td>

   <td width="208">1</td>

   <td width="208">1 if the user entered a dime into the machine and 0 otherwise</td>

  </tr>

  <tr>

   <td width="208">NickelReceived</td>

   <td width="208">1</td>

   <td width="208">1 if the user entered a nickel into the machine and 0 otherwise</td>

  </tr>

  <tr>

   <td width="208">ClkIn</td>

   <td width="208">1</td>

   <td width="208">Connect this to the clock ports of your registers/flip-flops. Do nothing else with this</td>

  </tr>

 </tbody>

</table>




<h2>Outputs</h2>

<table width="624">

 <tbody>

  <tr>

   <td width="208">Pin</td>

   <td width="208">Size (in bits)</td>

   <td width="208">Explanation</td>

  </tr>

  <tr>

   <td width="208">Give_Merchandise_Out</td>

   <td width="208">1</td>

   <td width="208">1 if the user has entered 30 cents and 0 otherwise</td>

  </tr>

  <tr>

   <td width="208">Give_Dime_Out</td>

   <td width="208">1</td>

   <td width="208">1 if a dime should be given back as change and 0 otherwise</td>

  </tr>

  <tr>

   <td width="208">Give_Nickel_out</td>

   <td width="208">1</td>

   <td width="208">1 if a nickel should be given back as change and 0 otherwise</td>

  </tr>

 </tbody>

</table>