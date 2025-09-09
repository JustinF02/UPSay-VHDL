# VHDL on VS Code with GHDL + GTKWave

This project uses **VHDL** with [GHDL](https://github.com/ghdl/ghdl) as the compiler/simulator and [Wave Surfer](https://marketplace.visualstudio.com/items?itemName=surfer-project.surfer) as the waveform viewer.  
Follow these steps to set up your environment on Windows x86-64:

## Installation

1. **Install VS Code extensions**  
   - [VHDL LS](https://marketplace.visualstudio.com/items?itemName=hbohlin.vhdl-ls) for syntax highlighting and linting.  
   - [Wave Surfer](https://marketplace.visualstudio.com/items?itemName=surfer-project.surfer)

2. **Install GHDL**  
   - Download the Windows release from [GHDL Releases](https://github.com/ghdl/ghdl/releases).  
   - Extract the archive (e.g., `C:\ghdl`).  
   - Add `C:\ghdl\bin` to your system `PATH`.  
   - Verify installation:  
     ```bash
     ghdl --version
     ```

---

## Compile and Run

Example with `half_adder.vhd` and `tb_half_adder.vhd`:

```bash
#Analyze source files
ghdl -a half_adder.vhd
ghdl -a tb_half_adder.vhd

#Elaborate testbench
ghdl -e tb_half_adder

#Run simulation and dump waveforms
ghdl -r tb_half_adder --vcd=waves.vcd

#visualize waves through surfer
