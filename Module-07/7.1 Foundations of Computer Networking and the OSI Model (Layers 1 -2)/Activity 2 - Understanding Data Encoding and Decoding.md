## Activity Objective

This activity introduces the concept of binary encoding and decoding using the ASCII standard. Students will manually convert binary values to text and observe how individual bytes (8-bit binary sequences) represent characters. By completing this exercise, students will gain foundational insight into how data is prepared for transmission across a network and how it is reconstructed at the receiving end. This understanding is essential for grasping how communication occurs between devices in a computer network.

## Activity Instructions
Follow the instructions below:
1. Open your web browser to [Browserling Binart to Text](https://www.browserling.com/tools/binary-to-text).
2. In the Binary box, type `01001000` and click the "Convert" button (this binary value represents the letter H using ASCII). You should see the letter H.
3. Replace the binary input with `01100101` and click "Convert" (this binary value represents the letter e). You should see the letter e.
4. Replace the binary input with `01101100` and click "Convert" (this binary value represents the letter l). You should see the letter l.
5. Repeat the same step using `01101100` again and click "Convert" (this is another l). You should see the letter l.
7. Replace the binary input with `01101111` and click "Convert" (this binary value represents the letter o). You should see the letter o.
8. Now replace everything in the Binary box with `01001000 01100101 01101100 01101100 01101111` and click "Convert" (this simulates how a computer receives multiple bytes together and decodes them all at once). You should now see the word Hello.
9. Go to [Browserling Text to Binary](https://www.browserling.com/tools/text-to-binary) and type your name or a short word (this tool shows how readable text is converted into binary before being sent over a network).
10. Copy the binary output that appears.
11. Return to the Binary to Text tool and paste the binary string into the Binary box (this simulates how the receiving computer decodes the binary back into readable text).
12. Click the "Convert" button. You should see the original word you typed.
