# openE906 仿真测试报告

## 测试环境

| 项目 | 说明 |
|------|------|
| 处理器 | T-Head openE906 RISC-V |
| 仿真器 | iverilog |
| 工具链 | Xuantie-900 GCC (riscv64-unknown-elf) V2.0.3 |
| 运行环境 | Docker (jiqian/opene906-env:v2.2) |

## 测试结果汇总

| 用例 | 结果 | 关键数据 |
|------|------|----------|
| `hello_world` | ✅ PASS | 环境基本功能验证 |
| `coremark` | ✅ PASS | **3.26** CoreMark/MHz |
| `memcp` | ✅ PASS | 1024字节拷贝 / **1028** 周期 |
| `memset` | ✅ PASS | 1024字节初始化 / **1024** 周期 |
| `ISA_RV32IMAC` | ✅ PASS | 整数/乘除/原子指令集验证 |
| `csr_rw_extend` | ✅ PASS | 自定义CSR寄存器读写验证 |

## 详细结果

### hello_world
```
Hello Friend!
Welcome to T-HEAD World!
a is 1!
b is 2!
c is 0!
!!! PASS !!!after ASM c is changed to 3!
```
### coremark
```
VCUNT_SIM: CoreMark has been run 2 times, one times cost 306789 cycles !
VCUNT_SIM: CoreMark 1.0 : 3.259569 (iterations/sec)/MHz
```
### memcp
```
VCUNT_SIM:Memory copy for 1024 bytes cost 1028 CPU cycles!
```
### memset
```
VCUNT_SIM:Memory set from 0x0 to 0x400 cost 1024 CPU cycles!
```
### ISA_RV32IMAC
```
simulation finished successfully
```
### csr_rw_extend
```
simulation finished successfully
```


## 性能对比参考

| 处理器 | CoreMark/MHz |
|--------|-------------|
| **E906 (本测试)** | **3.26** |
| ARM Cortex-M4 | 3.42 |
| ARM Cortex-M3 | 3.32 |
| ARM Cortex-M0 | 2.33 |
| T-Head E902 | 2.10 |

## 结论

openE906 处理器在仿真环境中所有基础功能测试均通过，CoreMark 得分与 ARM Cortex-M4 处于同一水平，内存操作效率优秀（接近每周期单字节）。
