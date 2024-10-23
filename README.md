# README

刘鑫宇 23371510

## 用途

> `autoRun.py`: 自动运行asm文件,生成机器码文件,内存文件,并输出寄存器内容
>
> `compareMemory.py`: 针对MIPS中Data Segment的导出文件与Logisim中RAM的Memory导出文件的比较程序
>
> `compareRegister.py`:针对MIPS中寄存器记录文件与`Logisim`中寄存器的日志文件的比较程序

## 使用方式

### 运行`asm`测试文件

```bash
# Mars运行asm文件(test.asm),输出机器码到machine_code.txt,输出Memory结果到mips_memory.txt,将寄存器结果输出到mips_register.txt,具体运行指令输出到mips_saved_bash.sh
python autoRun.py test.asm machine_code.txt mips_memory.txt > mips_registers.txt
```

### 在`Logisim`中生成CPU寄存器日志文件

> 在`Logisim`中导入机器码文件`machine_code.txt`,将寄存器`$0-$31`设置为日志的追踪目标,将日志输出到`logisim_register.txt`

### 在`Logisim`中导出RAM的Memory文件

> 右键RAM,选择`save image`,导出到`logisim_memory.txt`

### 比较Memory文件

```bash
# 比较Memory文件,结果输出到result.txt
python compareMemory.py mips_memory.txt logisim_memory.txt > result.txt
```

### 比较Register文件

```bash
# 比较Register文件,结果输出到result.txt
python compareRegister.py mips_registers.txt logisim_registers.txt >> result.txt
```

或直接运行`bash.sh`