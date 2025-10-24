# High-level approach
Following the implementation steps listed in the project description, I started by adding a variable to control how many packets could be in flight at the same time from the sender. For the second step, I made sure that sequence numbers were not being printed twice by storing all received sequence numbers and checking that newly received packets were not in this list. In step three, I changed this configuration to be more like a buffer, where packets were organized by sequence number, and I only printed out the next expected sequence number in order. For step four, I implemented packet loss detection by using a timeout variable where the sender would only wait for the duration of the timeout period for an acknowledgement before assuming that the packet had been dropped. Once the timeout period had passed, the sender would retransmit the packet and repeat the process. I skipped step 5 since I am not enrolled in 5700, and moved on to step 6. For step 6, I used the time library to record the time at which I sent packets and the time at which I received acknowledgements to estimate RTT, then I adjusted the timeout dynamically based on these measurements. For step 7, I implemented the AIMD (Additive Increase Multiplicative Decrease) protocol to increase the window size gradually on success but decrease it rapidly on packet loss.

## Challenges faced:
- I think that the thing that I struggled most with on this project was determining exactly how to implement each step. I had a high level overview understanding but especially as I got to around step 4 or 6, the direction I should take to get the optimal solution began to become more unclear as there were more options and different protocols to consider and understand. 
## A list of my favorite properties/features
- Sliding window protocol
- Out of order packet handling
- Packet loss detection and retransmission
- AIMD implementation
## Testing:
I tested the code by running the available tests and configurations multiple times to ensure that the result was consistent.