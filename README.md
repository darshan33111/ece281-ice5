# ICE 5: Basic Elevator Controller

VHDL for ECE 281 [ICE 5](https://usafa-ece.github.io/ece281-book/ICE/ICE5.html)

Targeted toward Digilent Basys3. Make sure to install the [board files](https://github.com/Xilinx/XilinxBoardStore/tree/2018.2/boards/Digilent/basys3).

Tested on Windows 11.

---

## Build the project

You can simply open `elevatorController.xpr` and Vivado will do the rest!

## GitHub Actions Testbench

The workflow uses the [setup-ghdl-ci](https://github.com/ghdl/setup-ghdl-ci) GitHub action
to run a *nightly* build of [GHDL](https://ghdl.github.io/ghdl/).

The workflow uses GHDL to analyze, elaborate, and run the entity specified in the `.github/workflows/testbench.yml`.

```yaml
env:
  TESTBENCH_ENTITY: elevator_controller_fsm
```

If successful then GHDL will quietly exit with a `0` code.
If any of the `assert` statements fail **with** `severity failure` then GHDL will cease the simulation and exit with non-zero code; this will also cause the workflow to fail.
Assert statements of other severity levels, such as "error" w

Screenshot: <img width="956" alt="{1FAC9A93-A887-454C-82F6-8A25FC58DF0F}" src="https://github.com/user-attachments/assets/0cdc5173-ffb2-4335-85ef-f2d208ec2cd1" />
