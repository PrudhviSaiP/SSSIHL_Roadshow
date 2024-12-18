#  VSD VLSI Workshop
***Chip design using RISC-V open source architecture.***
***

# Overview Of The Workshop
The workshop provided us with an understanding of how to design a semiconductor chip using RISC-V architecture. It helped us understand the various components of a microprocessor, its various types and the technologies that underlie the working of the processor.   

# Designing a Microprocessor
1. Installed Oracle Virtualbox to use Ubuntu for designing the chip.
   
   ![1](https://github.com/user-attachments/assets/5235a0c4-39ef-4bf2-a0ce-12cb5144e577)
2. Gedit text editor was installed using the terminal and a file was open for writing program code. 

   ![2](https://github.com/user-attachments/assets/dce325e3-cabf-4f83-ba31-61ab72b47087)
3. A sample program was coded in C language and was run using gcc compiler.
   ```
   #include<stdio.h>
   int main(){
     int sum = 0, i, n;
     printf("Enter the value of n = ");
     scanf("%d",&n);
     for(i = 1;i <= n;i++){
       sum = sum + i;
     }
     printf("The Sum of numbers from 1 to %d is %d\n",n,sum);
     return 0;
   }
   ```
    ![3](https://github.com/user-attachments/assets/39002dcf-968a-474c-9622-41afbab572f9)
    ***This is a simple code which will sum numbers form 1 to n, where user can enter n.***

4. Now the same code was complied using RISC-V instruction set architecture.

   ```riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o hello.o hello.c ```

   ![4](https://github.com/user-attachments/assets/3052af5e-008b-4a89-acd7-f8da271a13c2)
   ***The program was successfully compiled without any errors.***
5. Then we saw the instruction set of the RISC-V.

   ![5](https://github.com/user-attachments/assets/40e9d302-95b0-4830-8c3a-139fba3b6fba)
   ![6](https://github.com/user-attachments/assets/f7317058-589c-4757-bcb9-924694eb3275)

6. Docker and Openlane were used to design the processor virtually.

   ![7](https://github.com/user-attachments/assets/bd1055d9-b720-4603-9eb1-f0ab6eec1887)
   ![8](https://github.com/user-attachments/assets/41109d4f-59e8-4a81-999c-06466fe287a9)
   
7. The floorplan was made using the 'run_floorplan' command, and the output was displayed using 'eog designs/picorv32a/runs/13-12_07-00/results/floorplan/picorva32.floorplan.def.png' command in a new terminal.

   ![9](https://github.com/user-attachments/assets/1f9b88ca-5aea-4f9f-931f-bbd1fbfcf9b6)

8. The components are then placed using 'run_placement' command and the output was displayed using 'eog designs/picorv32a/runs/13-12_07-00/results/floorplan/picorva32.placement.def.png' command in a new terminal.

   ![10](https://github.com/user-attachments/assets/6d00f6d2-24d4-4328-a791-7ed6d410f450)
   ![11](https://github.com/user-attachments/assets/1f046d4b-659b-451c-9888-fccd95d32686)

9. Then after that the Clock Tree Synthesis (CTS) was done using the 'run_cts' command.

    ![cts](https://github.com/user-attachments/assets/9f74e9f7-dc57-4b66-91db-515c79bc99ee)

10. Finally the process of establishing physical connections between signal pins using metal layers(routing) was done using the 'run_routing' command.

    
    ![12](https://github.com/user-attachments/assets/44c9e3e9-7aa7-4a76-ae05-5ab77ed9d811)
    ![13](https://github.com/user-attachments/assets/f246610e-bdb3-4c45-bc65-9ed414629993)

**All the commands from step 6 to 10 in a sequence are as follows.**
```
cd Desktop/work/tools/openlane_working_dir/openlane
docker
./flow.tcl -interactive
pakage require openlane 0.9
run_placement
prep -design picorv32a
run_synthesis
run_floorplan
run_placement
run_cts
run_routing
```     
# Running a few codes on vsdsquaran mini
* Blinking led

https://github.com/user-attachments/assets/82228907-3048-4a69-8f4a-a1f4c3257ea4

* Dimming led
  

https://github.com/user-attachments/assets/28f42660-8a66-4d97-99a4-0e761acbbe9f




