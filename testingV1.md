# Boolean Algebra Summative Project

![Circuit Diagram](media/image4.png) <!-- Add circuit image here -->

---

## Table of Contents

1. [Summary](#summary)
2. [Parts List](#parts-list)
3. [Process Work](#process-work)
4. [Logisim Circuit](#logisim-circuit)

---

## Summary

To produce a common anode display of 2 digits, capable of displaying the numbers 55 to 70, inclusively through 4 binary values, represented through LED switches. Each of them correspond to the letter A, B, C, and D. Each of the LED switches which can be turned off and on, represent 0's and 1's respectively. Each LED corresponds to the following place values: A = 2³, B = 2², C = 2¹, and D = 2⁰.

Furthermore, in order to see how it all works, solely turn on and off the LED switches. To do this, the circuit first must be on, by switching the 'Enable Bit' to 1. However, to turn off the entire circuit at any point of time, switch the 'Enable Bit' to 0. To display the first number, 55, start with the binary value of 0000 by turning off LED switches 'A', 'B', 'C', and 'D'. To display the next number, increase the binary value by one each time until all the LED switches are turned on where the maximum number, 70, is reached. For more details, below is a chart that indicates which LED switches must be on and off to display specific numbers.

*This table shows which LED switches are on and off, the binary value, the decimal equivalent, and what number is read on the display. Ensure the 'Enable Bit' is on to display any number.*

| LED A | LED B | LED C | LED D | Binary Value | Display Number |
|-------|-------|-------|-------|--------------|----------------|
| off   | off   | off   | off   | 0000         | 55             |
| off   | off   | off   | on    | 0001         | 56             |
| off   | off   | on    | off   | 0010         | 57             |
| off   | off   | on    | on    | 0011         | 58             |
| off   | on    | off   | off   | 0100         | 59             |
| off   | on    | off   | on    | 0101         | 60             |
| off   | on    | on    | off   | 0110         | 61             |
| off   | on    | on    | on    | 0111         | 62             |
| on    | off   | off   | off   | 1000         | 63             |
| on    | off   | off   | on    | 1001         | 64             |
| on    | off   | on    | off   | 1010         | 65             |
| on    | off   | on    | on    | 1011         | 66             |
| on    | on    | off   | off   | 1100         | 67             |
| on    | on    | off   | on    | 1101         | 68             |
| on    | on    | on    | off   | 1110         | 69             |
| on    | on    | on    | on    | 1111         | 70             |

## Parts List

*The table below indicates all components used & quantities in the final Logisim circuit.*

| Name of Component | Location of Where Used | Total Amount Used |
|-------------------|------------------------|-------------------|
| LED Switch        | 1 x A Input<br>1 x B Input<br>1 x C Input<br>1 x D Input<br>1 x Enable Bit Input | 5 |
| 0 Constant        | 1 x Display 1 & 2 'DP', Display 1 Segment 'a' & 'c' | 1 |
| NOT Gate          | 12 x Enable Bit<br>6 x Display 1<br>4 x Display 2 Segment 'a'<br>4 x Display 2 Segment 'b'<br>1 x Display 2 Segment 'c'<br>3 x Display 2 Segment 'd'<br>3 x Display 2 Segment 'e'<br>2 x Display 2 Segment 'f'<br>6 x Display 2 Segment 'g'<br>2 x Display 1 & 2 'DP' | 43 |
| OR Gate           | 1 x Display 1 Segment 'e'<br>1 x Display 2 Segment 'a'<br>1 x Display 2 Segment 'b'<br>1 x Display 2 Segment 'd'<br>1 x Display 2 Segment 'e'<br>1 x Display 2 Segment 'f'<br>2 x Display 2 Segment 'g' | 8 |
| AND Gate          | 3 x Display 1<br>2 x Display 2 Segment 'a'<br>2 x Display 2 Segment 'b'<br>1 x Display 2 Segment 'c'<br>2 x Display 2 Segment 'd'<br>1 x Display 2 Segment 'e'<br>2 x Display 2 Segment 'f'<br>5 x Display 2 Segment 'g' | 18 |
| XOR Gate          | 1 x Display 2 Segment 'f'<br>1 x Display 2 Segment 'd' | 2 |
| NAND Gate         | 8 x Display 1 'Enable Bit'<br>8 x Display 2 'Enable Bit' | 16 |

## Process Work

Involves any and all rough work that leads up to the final circuit, which is attached as a file and also shown as pictures which can be found in the 'Logisim Circuit' section.

*The chart below shows what number should be displayed, the binary value, the decimal equivalent, and which segments and which display should be receiving inputs of either 0's and 1's, which are represented through blank spaces and x's in the respective order.*

![Segment Mapping Chart](media/image12.png) <!-- Add segment mapping chart here -->

For each K-Map below, once again, x's represent 1's and blank spaces represent 0's. Directly below each of them is their simplified expression and steps/laws if they were reduced further, followed by their corresponding Logisim circuit. Note that for each segment in 'Display 2', a common cathode was used instead of an anode for simplicity while testing since it is visually displeasing to see all other segments turned on, while attempting to test and focus on one single segment.

### Display 1 Segments

| Segment | K-Map | Circuit | Notes |
|---------|-------|---------|--------|
| **Segment 'a'** | ![Display 1 Segment a K-Map](media/image15.jpg) <!-- Add K-Map image --> | | |
| **Segment 'b'** | ![Display 1 Segment b K-Map](media/image15.jpg) <!-- Add K-Map image --> | | 1. Applied DeMorgan's Theorem |
| **Segment 'c'** | ![Display 1 Segment c K-Map](media/image15.jpg) <!-- Add K-Map image --> | | |
| **Segment 'd'** | ![Display 1 Segment d K-Map](media/image15.jpg) <!-- Add K-Map image --> | | |
| **Segment 'e'** | ![Display 1 Segment e K-Map](media/image14.jpg) <!-- Add K-Map image --> | | |
| **Segment 'f'** | ![Display 1 Segment f K-Map](media/image14.jpg) <!-- Add K-Map image --> | | |
| **Segment 'g'** | ![Display 1 Segment g K-Map](media/image14.jpg) <!-- Add K-Map image --> | | |
| **Complete Display 1** | | ![Display 1 Circuit](media/image2.png) <!-- Add circuit image --> | |

### Display 2 Segments

| Segment | K-Map | Circuit | Notes |
|---------|-------|---------|--------|
| **Segment 'a'** | ![Display 2 Segment a K-Map](media/image15.jpg) <!-- Add K-Map image --> | ![Display 2 Segment a Circuit](media/image6.png) <!-- Add circuit image --> | |
| **Segment 'b'** | ![Display 2 Segment b K-Map](media/image15.jpg) <!-- Add K-Map image --> | ![Display 2 Segment b Circuit](media/image5.png) <!-- Add circuit image --> | |
| **Segment 'c'** | ![Display 2 Segment c K-Map](media/image15.jpg) <!-- Add K-Map image --> | ![Display 2 Segment c Circuit](media/image11.png) <!-- Add circuit image --> | |
| **Segment 'd'** | ![Display 2 Segment d K-Map](media/image15.jpg) <!-- Add K-Map image --> | ![Display 2 Segment d Circuit](media/image13.png) <!-- Add circuit image --> | 1. Factored out AC' out of 2nd & 3rd terms.<br>2. Simplified to XOR using (A'B+AB') = A⊕B. |
| **Segment 'e'** | ![Display 2 Segment e K-Map](media/image14.jpg) <!-- Add K-Map image --> | ![Display 2 Segment e Circuit](media/image8.png) <!-- Add circuit image --> | |
| **Segment 'f'** | ![Display 2 Segment f K-Map](media/image14.jpg) <!-- Add K-Map image --> | ![Display 2 Segment f Circuit](media/image9.png) <!-- Add circuit image --> | 1. Changed order of terms for simplicity<br>2. Factored out D' from 2nd & 3rd term<br>3. Simplified to XOR using (A'B+AB') = A⊕B. |
| **Segment 'g'** | ![Display 2 Segment g K-Map](media/image14.jpg) <!-- Add K-Map image --> | ![Display 2 Segment g Circuit](media/image10.png) <!-- Add circuit image --> | |

### Both Digits without 'Enable Bit'

![Both Displays Circuit](media/image7.png) <!-- Add circuit image -->

### Figuring Out 'Enable Bit'

In order to create an expression to turn off the entire circuit at will with just a flick of a switch, a truth table was necessary to determine a minterm expression through a K-Map. When the 'Enable Bit', EB, equals 0, the entire circuit should turn off no matter the value of the final output of any segment's expression, A. Meanwhile, whenever the 'Enable Bit' is on, the circuit should function as if there was no 'Enable Bit' and display numbers as regular, so the desired output, X, should be whatever A should usually display.

However, it must be noted that since this is a common anode instead of a common cathode, that to cause the segment to appear off, the incoming input has to be equal to 1. Therefore, when the desired final output is off, it equals 1 and of course when the desired output is on, it is actually 0. Moreover, since everything but a single output is a 1, a NAND gate suits this situation the best, but some tinkering and experimentation was necessary to get it to work as intended.

#### Enable Bit Truth Table

| EB | A | X |
|----|---|----|
| 0  | 0 | off = 1 |
| 0  | 1 | off = 1 |
| 1  | 0 | off = 1 |
| 1  | 1 | on = 0 |

![Enable Bit K-Map](media/image3.png) <!-- Add K-Map image -->

## Logisim Circuit

*Directly below are two pictures of the Logisim circuit. The one on top is more convenient for tracing the input all the way to the output, while the one below is more convenient for testing it out. Although pictures are shown, the file attached will provide much more convenience.*

![Logisim Circuit Diagram 1](media/image4.png) <!-- Add circuit image -->

![Logisim Circuit Diagram 2](media/image1.png) <!-- Add circuit image -->

---