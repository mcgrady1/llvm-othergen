set(LLVM_TARGET_DEFINITIONS PPC.td)

tablegen(LLVM PPCGenAsmWriter.inc -gen-asm-writer)
tablegen(LLVM PPCGenAsmMatcher.inc -gen-asm-matcher)
tablegen(LLVM PPCGenDisassemblerTables.inc -gen-disassembler)
tablegen(LLVM PPCGenMCCodeEmitter.inc -gen-emitter)
tablegen(LLVM PPCGenRegisterInfo.inc -gen-register-info)
tablegen(LLVM PPCGenInstrInfo.inc -gen-instr-info)
tablegen(LLVM PPCGenDAGISel.inc -gen-dag-isel)
tablegen(LLVM PPCGenFastISel.inc -gen-fast-isel)
tablegen(LLVM PPCGenCallingConv.inc -gen-callingconv)
tablegen(LLVM PPCGenSubtargetInfo.inc -gen-subtarget)
add_public_tablegen_target(PowerPCCommonTableGen)

add_llvm_target(PowerPCCodeGen
  PPCAsmPrinter.cpp
  PPCBranchSelector.cpp
  PPCCTRLoops.cpp
  PPCHazardRecognizers.cpp
  PPCInstrInfo.cpp
  PPCISelDAGToDAG.cpp
  PPCISelLowering.cpp
  PPCEarlyReturn.cpp
  PPCFastISel.cpp
  PPCFrameLowering.cpp
  PPCMCInstLower.cpp
  PPCMachineFunctionInfo.cpp
  PPCRegisterInfo.cpp
  PPCSubtarget.cpp
  PPCTargetMachine.cpp
  PPCTargetObjectFile.cpp
  PPCTargetTransformInfo.cpp
  PPCSelectionDAGInfo.cpp
  PPCTLSDynamicCall.cpp
  PPCVSXCopy.cpp
  PPCVSXFMAMutate.cpp
  )

add_subdirectory(AsmParser)
add_subdirectory(Disassembler)
add_subdirectory(InstPrinter)
add_subdirectory(TargetInfo)
add_subdirectory(MCTargetDesc)
