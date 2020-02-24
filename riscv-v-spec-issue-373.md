# riscv-v-spec Issue #373

Author: David-Horner

David-Horner 发现在 rs1 = 0 时很多指令的 op.vx 和 op.vi 编码都可以简化，所以他建议 rvv 保留这些 rs1 = 0 的编码，使用更简单的等价指令代替它们，从而最大限度消除冗余编码。

例如：

当 rs1 = 0 时	，下列 op.vx 和 op.vi 指令都等价于 vmv.v.v：
	
	vadd, vsaddu, vsadd, vor, vxor
	vsll, vsrl, vsra, vssrl, vssra
	vslideup, vslidedown

当 rs1 = 0 时	，下列 op.vx 和 op.vi 指令都等价于 rs1 = 0 的 vnsrl：

	vnsra, vnclipu, vnclip
	
当 rs1 = 0 时	，

*  vaadd 和 vasub 的 op.vx 和 op.vi 的值相当于移位计数为1的 vssra 。
*  vaaddu 和 vasubu 的 op.vx 和 op.vi 等价于移位计数为1的 vssrl 。
*  vand 的 op.vx 和 op.vi 等于 vmv.v.i imm=0（或 vmv.v.x rs1 = x0 ）。