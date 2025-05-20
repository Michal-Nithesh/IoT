# 8051 Assembly Language Program using Keil Simulator

## Aim
To write and execute an 8051 assembly language program using the Keil µVision simulator.

## Procedure

1. **Open Keil µVision IDE**.
2. **Create a new project**:
   - Go to `Project` > `New uVision Project`.
   - Name your project and save it in a desired folder.
3. **Select Device**:
   - Choose the 8051 microcontroller (e.g., AT89C51) from the list and click OK.
4. **Add a new assembly file**:
   - Right-click on `Source Group 1` > `Add New Item to Group 'Source Group 1'`.
   - Select `Assembly File (.A51)` and give it a name.
5. **Write the assembly code** in the editor window.
6. **Build the project**:
   - Go to `Project` > `Build Target`.
   - Fix any errors or warnings.
7. **Debug the program**:
   - Click on the "Start/Stop Debug Session" icon.
   - Use step-by-step execution, watch registers, memory, and ports.
8. **Verify output**:
   - Use peripherals and register windows to verify output.

## Code - 1
```asm
ORG 00H
SJMP START
ORG 30H
START:
MOV A, #03H
MOV R0, #03H
ADD A,R0
MOV R1,A
END
```

## OUTPUT:

The sum of 03H + 03H is stored in R1 (06H).


# 8051 Assembly Language Program using Keil Simulator

## Aim
To test data transfer between registers and memory in 8051 microcontroller using Keil µVision.

## Procedure

1. **Open Keil µVision IDE**.
2. **Create a new project**:
   - Navigate to `Project` > `New uVision Project`.
   - Name the project and save it in a desired directory.
3. **Select the target device**:
   - Choose `AT89C51` or any compatible 8051 microcontroller.
4. **Add a new Assembly file**:
   - Right-click on `Source Group 1` > `Add New Item to Group 'Source Group 1'`.
   - Choose `Assembly File (.A51)`, name the file, and click Add.
5. **Write the program code** in the editor window.
6. **Build the project**:
   - Go to `Project` > `Build Target` or press `F7`.
   - Ensure there are no syntax errors.
7. **Start debugging**:
   - Click the "Start/Stop Debug Session" button.
   - Use memory window and watch registers to monitor data transfer.
8. **Initialize memory**:
   - Before running, manually load values into memory from `30H` to `34H`.
9. **Run the program** and observe results.

## Code
```asm
ORG 00H
MOV R0,#30H
MOV R1,#40H
MOV R3,#05
MOV A,@R0
UP: MOV @R1,A
INC R0
INC R1
DJNZ R1,UP
END
```

## OUTPUT

The contents of memory from 30H to 34H are copied to 40H to 44H.
