---
title: "__cpuid, __cpuidex | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__cpuid_cpp"
  - "__cpuid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__cpuid intrinsic"
  - "cpuid instruction"
  - "cpuid intrinsic"
ms.assetid: f8c344d3-91bf-405f-8622-cb0e337a6bdc
caps.latest.revision: 38
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 36
---
# __cpuid, __cpuidex
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Generiert die `cpuid`\-Anweisung, die auf x86 und [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] verfügbar ist.  Diese Anweisung fragt den Prozessor nach Informationen zu unterstützten Funktionen und dem CPU\-Typ ab.  
  
## Syntax  
  
```  
void __cpuid(  
   int cpuInfo[4],  
   int function_id  
);  
  
void __cpuidex(  
   int cpuInfo[4],  
   int function_id,  
   int subfunction_id  
);  
```  
  
#### Parameter  
 \[out\] `cpuInfo`  
 Ein Array aus vier Ganzzahlen, das die Informationen enthält, die in EAX, EBX, ECX and EDX zu unterstützten Funktionen der CPU zurückgegeben werden.  
  
 \[in\] `function_id`  
 Ein Code, der die abzurufenden Informationen angibt und in EAX übergeben wird.  
  
 \[in\] `subfunction_id`  
 Ein zusätzlicher Code, der abzurufende Informationen angibt und in ECX übergeben wird.  
  
## Anforderungen  
  
|Systemintern|Architektur|  
|------------------|-----------------|  
|`__cpuid`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`__cpuidex`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Headerdatei** \<intrin.h\>  
  
## Hinweise  
 Diese systeminterne Funktion speichert die unterstützten Funktionen und CPU\-Informationen, die von der `cpuid`\-Anweisung in `cpuInfo` zurückgegeben wird, einem Array aus vier 32\-Bit\-Ganzzahlen, das mit den Werten der Register EAX, EBX, ECX und EDX \(in dieser Reihenfolge\) gefüllt ist.  Die zurückgegebenen Informationen haben je nach dem Wert, der als `function_id`\-Parameter übergeben wird, eine andere Bedeutung.  Die mit verschiedenen Werten von `function_id` zurückgegebenen Informationen sind prozessorabhängig.  
  
 Die systeminterne `__cpuid`\-Funktion löscht das ECX\-Register, bevor die `cpuid`\-Anweisung aufgerufen wird.  Die systeminterne Funktion `__cpuidex` legt den Wert des ECX\-Registers auf `subfunction_id` fest, bevor sie die `cpuid`\-Anweisung generiert.  Damit können Sie zusätzliche Informationen zum Prozessor sammeln.  
  
 For more information about the specific parameters to use and the values returned by these intrinsics on Intel processors, see the documentation for the `cpuid` instruction in [Intel 64 and IA\-32 Architectures Software Developers Manual Volume 2: Instruction Set Reference](http://go.microsoft.com/fwlink/p/?LinkID=510021) and [Intel Architecture Instruction Set Extensions Programming Reference](http://go.microsoft.com/fwlink/p/?LinkID=506627).  In der Intel\-Dokumentation werden die Begriffe "leaf" und "subleaf" für die in EAX und ECX übergebenen Parameter `function_id` and `subfunction_id` verwendet.  
  
 Weitere Informationen zu den spezifischen zu verwendenden Parametern und den von diesen systeminternen Funktionen auf AMD\-Prozessoren zurückgegebenen Werten finden Sie in der Dokumentation für die `cpuid`\-Anweisung im [AMD64 Architecture Programmer's Manual Volume 3: General\-Purpose and System Instructions](http://go.microsoft.com/fwlink/p/?LinkId=510023) und in den [Revision Guides](http://go.microsoft.com/fwlink/p/?LinkId=510023) für spezifische Prozessorfamilien.  In der AMD\-Dokumentation werden die Begriffe "function number" und "subfunction number" für die in EAX und ECX übergebenen Parameter `function_id` and `subfunction_id` verwendet.  
  
 Wenn das `function_id`\-Argument 0 ist, gibt `cpuInfo[0]` die höchste verfügbare nicht erweiterte `function_id` aus, die vom Prozessor unterstützt wird.  Der Hersteller des Prozessors ist in `cpuInfo[1]`, `cpuInfo[2]` und cpuInfo\[3\] codiert.  
  
 Die Unterstützung für bestimmte Erweiterungen des Anweisungssatzes sowie CPU\-Funktionen ist in den `cpuInfo`\-Ergebnissen codiert, die für höhere function\_id\-Werte zurückgegeben werden.  Weitere Informationen finden Sie in den weiter oben verknüpften Handbüchern und im folgenden Beispielcode.  
  
 Einige Prozessoren unterstützen Informationen zur erweiterten Funktions\-CPUID.  Wenn dies unterstützt wird, können `function_id`\-Werte von 0x80000000 verwendet werden, um Informationen zurückzugeben.  Legen Sie zum Bestimmen des maximal zulässigen aussagekräftigen Werts `function_id` auf 0x80000000 fest.  Der für erweiterte Funktionen maximal unterstützte Wert von `function_id` wird in `cpuInfo[0]` geschrieben.  
  
## Beispiel  
 Dieses Beispiel zeigt einige der Informationen, die über die systeminternen Funktionen `__cpuid` und `__cpuidex` zur Verfügung stehen.  Die Anwendung führt die Erweiterungen des Anweisungssatzes auf, die vom aktuellen Prozessor unterstützt werden.  Die Ausgabe zeigt ein mögliches Ergebnis für einen bestimmten Prozessor.  
  
```  
// InstructionSet.cpp   
// Compile by using: cl /EHsc /W4 InstructionSet.cpp  
// processor: x86, x64  
// Uses the __cpuid intrinsic to get information about   
// CPU extended instruction set support.  
  
#include <iostream>  
#include <vector>  
#include <bitset>  
#include <array>  
#include <string>  
#include <intrin.h>  
  
class InstructionSet  
{  
    // forward declarations  
    class InstructionSet_Internal;  
  
public:  
    // getters  
    static std::string Vendor(void) { return CPU_Rep.vendor_; }  
    static std::string Brand(void) { return CPU_Rep.brand_; }  
  
    static bool SSE3(void) { return CPU_Rep.f_1_ECX_[0]; }  
    static bool PCLMULQDQ(void) { return CPU_Rep.f_1_ECX_[1]; }  
    static bool MONITOR(void) { return CPU_Rep.f_1_ECX_[3]; }  
    static bool SSSE3(void) { return CPU_Rep.f_1_ECX_[9]; }  
    static bool FMA(void) { return CPU_Rep.f_1_ECX_[12]; }  
    static bool CMPXCHG16B(void) { return CPU_Rep.f_1_ECX_[13]; }  
    static bool SSE41(void) { return CPU_Rep.f_1_ECX_[19]; }  
    static bool SSE42(void) { return CPU_Rep.f_1_ECX_[20]; }  
    static bool MOVBE(void) { return CPU_Rep.f_1_ECX_[22]; }  
    static bool POPCNT(void) { return CPU_Rep.f_1_ECX_[23]; }  
    static bool AES(void) { return CPU_Rep.f_1_ECX_[25]; }  
    static bool XSAVE(void) { return CPU_Rep.f_1_ECX_[26]; }  
    static bool OSXSAVE(void) { return CPU_Rep.f_1_ECX_[27]; }  
    static bool AVX(void) { return CPU_Rep.f_1_ECX_[28]; }  
    static bool F16C(void) { return CPU_Rep.f_1_ECX_[29]; }  
    static bool RDRAND(void) { return CPU_Rep.f_1_ECX_[30]; }  
  
    static bool MSR(void) { return CPU_Rep.f_1_EDX_[5]; }  
    static bool CX8(void) { return CPU_Rep.f_1_EDX_[8]; }  
    static bool SEP(void) { return CPU_Rep.f_1_EDX_[11]; }  
    static bool CMOV(void) { return CPU_Rep.f_1_EDX_[15]; }  
    static bool CLFSH(void) { return CPU_Rep.f_1_EDX_[19]; }  
    static bool MMX(void) { return CPU_Rep.f_1_EDX_[23]; }  
    static bool FXSR(void) { return CPU_Rep.f_1_EDX_[24]; }  
    static bool SSE(void) { return CPU_Rep.f_1_EDX_[25]; }  
    static bool SSE2(void) { return CPU_Rep.f_1_EDX_[26]; }  
  
    static bool FSGSBASE(void) { return CPU_Rep.f_7_EBX_[0]; }  
    static bool BMI1(void) { return CPU_Rep.f_7_EBX_[3]; }  
    static bool HLE(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[4]; }  
    static bool AVX2(void) { return CPU_Rep.f_7_EBX_[5]; }  
    static bool BMI2(void) { return CPU_Rep.f_7_EBX_[8]; }  
    static bool ERMS(void) { return CPU_Rep.f_7_EBX_[9]; }  
    static bool INVPCID(void) { return CPU_Rep.f_7_EBX_[10]; }  
    static bool RTM(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_7_EBX_[11]; }  
    static bool AVX512F(void) { return CPU_Rep.f_7_EBX_[16]; }  
    static bool RDSEED(void) { return CPU_Rep.f_7_EBX_[18]; }  
    static bool ADX(void) { return CPU_Rep.f_7_EBX_[19]; }  
    static bool AVX512PF(void) { return CPU_Rep.f_7_EBX_[26]; }  
    static bool AVX512ER(void) { return CPU_Rep.f_7_EBX_[27]; }  
    static bool AVX512CD(void) { return CPU_Rep.f_7_EBX_[28]; }  
    static bool SHA(void) { return CPU_Rep.f_7_EBX_[29]; }  
  
    static bool PREFETCHWT1(void) { return CPU_Rep.f_7_ECX_[0]; }  
  
    static bool LAHF(void) { return CPU_Rep.f_81_ECX_[0]; }  
    static bool LZCNT(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_ECX_[5]; }  
    static bool ABM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[5]; }  
    static bool SSE4a(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[6]; }  
    static bool XOP(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[11]; }  
    static bool TBM(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_ECX_[21]; }  
  
    static bool SYSCALL(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[11]; }  
    static bool MMXEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[22]; }  
    static bool RDTSCP(void) { return CPU_Rep.isIntel_ && CPU_Rep.f_81_EDX_[27]; }  
    static bool _3DNOWEXT(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[30]; }  
    static bool _3DNOW(void) { return CPU_Rep.isAMD_ && CPU_Rep.f_81_EDX_[31]; }  
  
private:  
    static const InstructionSet_Internal CPU_Rep;  
  
    class InstructionSet_Internal  
    {  
    public:  
        InstructionSet_Internal()  
            : nIds_{ 0 },  
            nExIds_{ 0 },  
            isIntel_{ false },  
            isAMD_{ false },  
            f_1_ECX_{ 0 },  
            f_1_EDX_{ 0 },  
            f_7_EBX_{ 0 },  
            f_7_ECX_{ 0 },  
            f_81_ECX_{ 0 },  
            f_81_EDX_{ 0 },  
            data_{},  
            extdata_{}  
        {  
            //int cpuInfo[4] = {-1};  
            std::array<int, 4> cpui;  
  
            // Calling __cpuid with 0x0 as the function_id argument  
            // gets the number of the highest valid function ID.  
            __cpuid(cpui.data(), 0);  
            nIds_ = cpui[0];  
  
            for (int i = 0; i <= nIds_; ++i)  
            {  
                __cpuidex(cpui.data(), i, 0);  
                data_.push_back(cpui);  
            }  
  
            // Capture vendor string  
            char vendor[0x20];  
            memset(vendor, 0, sizeof(vendor));  
            *reinterpret_cast<int*>(vendor) = data_[0][1];  
            *reinterpret_cast<int*>(vendor + 4) = data_[0][3];  
            *reinterpret_cast<int*>(vendor + 8) = data_[0][2];  
            vendor_ = vendor;  
            if (vendor_ == "GenuineIntel")  
            {  
                isIntel_ = true;  
            }  
            else if (vendor_ == "AuthenticAMD")  
            {  
                isAMD_ = true;  
            }  
  
            // load bitset with flags for function 0x00000001  
            if (nIds_ >= 1)  
            {  
                f_1_ECX_ = data_[1][2];  
                f_1_EDX_ = data_[1][3];  
            }  
  
            // load bitset with flags for function 0x00000007  
            if (nIds_ >= 7)  
            {  
                f_7_EBX_ = data_[7][1];  
                f_7_ECX_ = data_[7][2];  
            }  
  
            // Calling __cpuid with 0x80000000 as the function_id argument  
            // gets the number of the highest valid extended ID.  
            __cpuid(cpui.data(), 0x80000000);  
            nExIds_ = cpui[0];  
  
            char brand[0x40];  
            memset(brand, 0, sizeof(brand));  
  
            for (int i = 0x80000000; i <= nExIds_; ++i)  
            {  
                __cpuidex(cpui.data(), i, 0);  
                extdata_.push_back(cpui);  
            }  
  
            // load bitset with flags for function 0x80000001  
            if (nExIds_ >= 0x80000001)  
            {  
                f_81_ECX_ = extdata_[1][2];  
                f_81_EDX_ = extdata_[1][3];  
            }  
  
            // Interpret CPU brand string if reported  
            if (nExIds_ >= 0x80000004)  
            {  
                memcpy(brand, extdata_[2].data(), sizeof(cpui));  
                memcpy(brand + 16, extdata_[3].data(), sizeof(cpui));  
                memcpy(brand + 32, extdata_[4].data(), sizeof(cpui));  
                brand_ = brand;  
            }  
        };  
  
        int nIds_;  
        int nExIds_;  
        std::string vendor_;  
        std::string brand_;  
        bool isIntel_;  
        bool isAMD_;  
        std::bitset<32> f_1_ECX_;  
        std::bitset<32> f_1_EDX_;  
        std::bitset<32> f_7_EBX_;  
        std::bitset<32> f_7_ECX_;  
        std::bitset<32> f_81_ECX_;  
        std::bitset<32> f_81_EDX_;  
        std::vector<std::array<int, 4>> data_;  
        std::vector<std::array<int, 4>> extdata_;  
    };  
};  
  
// Initialize static member data  
const InstructionSet::InstructionSet_Internal InstructionSet::CPU_Rep;  
  
// Print out supported instruction set extensions  
int main()  
{  
    auto& outstream = std::cout;  
  
    auto support_message = [&outstream](std::string isa_feature, bool is_supported) {  
        outstream << isa_feature << (is_supported ? " supported" : " not supported") << std::endl;  
    };  
  
    std::cout << InstructionSet::Vendor() << std::endl;  
    std::cout << InstructionSet::Brand() << std::endl;  
  
    support_message("3DNOW",       InstructionSet::_3DNOW());  
    support_message("3DNOWEXT",    InstructionSet::_3DNOWEXT());  
    support_message("ABM",         InstructionSet::ABM());  
    support_message("ADX",         InstructionSet::ADX());  
    support_message("AES",         InstructionSet::AES());  
    support_message("AVX",         InstructionSet::AVX());  
    support_message("AVX2",        InstructionSet::AVX2());  
    support_message("AVX512CD",    InstructionSet::AVX512CD());  
    support_message("AVX512ER",    InstructionSet::AVX512ER());  
    support_message("AVX512F",     InstructionSet::AVX512F());  
    support_message("AVX512PF",    InstructionSet::AVX512PF());  
    support_message("BMI1",        InstructionSet::BMI1());  
    support_message("BMI2",        InstructionSet::BMI2());  
    support_message("CLFSH",       InstructionSet::CLFSH());  
    support_message("CMPXCHG16B",  InstructionSet::CMPXCHG16B());  
    support_message("CX8",         InstructionSet::CX8());  
    support_message("ERMS",        InstructionSet::ERMS());  
    support_message("F16C",        InstructionSet::F16C());  
    support_message("FMA",         InstructionSet::FMA());  
    support_message("FSGSBASE",    InstructionSet::FSGSBASE());  
    support_message("FXSR",        InstructionSet::FXSR());  
    support_message("HLE",         InstructionSet::HLE());  
    support_message("INVPCID",     InstructionSet::INVPCID());  
    support_message("LAHF",        InstructionSet::LAHF());  
    support_message("LZCNT",       InstructionSet::LZCNT());  
    support_message("MMX",         InstructionSet::MMX());  
    support_message("MMXEXT",      InstructionSet::MMXEXT());  
    support_message("MONITOR",     InstructionSet::MONITOR());  
    support_message("MOVBE",       InstructionSet::MOVBE());  
    support_message("MSR",         InstructionSet::MSR());  
    support_message("OSXSAVE",     InstructionSet::OSXSAVE());  
    support_message("PCLMULQDQ",   InstructionSet::PCLMULQDQ());  
    support_message("POPCNT",      InstructionSet::POPCNT());  
    support_message("PREFETCHWT1", InstructionSet::PREFETCHWT1());  
    support_message("RDRAND",      InstructionSet::RDRAND());  
    support_message("RDSEED",      InstructionSet::RDSEED());  
    support_message("RDTSCP",      InstructionSet::RDTSCP());  
    support_message("RTM",         InstructionSet::RTM());  
    support_message("SEP",         InstructionSet::SEP());  
    support_message("SHA",         InstructionSet::SHA());  
    support_message("SSE",         InstructionSet::SSE());  
    support_message("SSE2",        InstructionSet::SSE2());  
    support_message("SSE3",        InstructionSet::SSE3());  
    support_message("SSE4.1",      InstructionSet::SSE41());  
    support_message("SSE4.2",      InstructionSet::SSE42());  
    support_message("SSE4a",       InstructionSet::SSE4a());  
    support_message("SSSE3",       InstructionSet::SSSE3());  
    support_message("SYSCALL",     InstructionSet::SYSCALL());  
    support_message("TBM",         InstructionSet::TBM());  
    support_message("XOP",         InstructionSet::XOP());  
    support_message("XSAVE",       InstructionSet::XSAVE());  
}  
```  
  
  **GenuineIntel**  
 **Intel\(R\) Core\(TM\) i5 2500 CPU 3,30 GHz**  
**3DNOW wird nicht unterstützt.**  
**3DNOWEXT wird nicht unterstützt.**  
**ABM wird nicht unterstützt.**  
**ADX wird nicht unterstützt.**  
**Unterstützt AES**  
**Unterstützt AVX**  
**AVX2 wird nicht unterstützt.**  
**AVX512CD wird nicht unterstützt.**  
**AVX512ER wird nicht unterstützt.**  
**AVX512F wird nicht unterstützt.**  
**AVX512PF wird nicht unterstützt.**  
**BMI1 wird nicht unterstützt.**  
**BMI2 wird nicht unterstützt.**  
**Unterstützt CLFSH**  
**Unterstützt CMPXCHG16B**  
**Unterstützt CX8**  
**ERMS wird nicht unterstützt.**  
**F16C wird nicht unterstützt.**  
**FMA wird nicht unterstützt.**  
**FSGSBASE wird nicht unterstützt.**  
**Unterstützt FXSR**  
**HLE wird nicht unterstützt.**  
**INVPCID wird nicht unterstützt.**  
**Unterstützt LAHF**  
**LZCNT wird nicht unterstützt.**  
**Unterstützt MMX**  
**MMXEXT wird nicht unterstützt.**  
**MONITOR wird nicht unterstützt.**  
**MOVBE wird nicht unterstützt.**  
**Unterstützt MSR**  
**Unterstützt OSXSAVE**  
**Unterstützt PCLMULQDQ**  
**Unterstützt POPCNT**  
**PREFETCHWT1 wird nicht unterstützt.**  
**RDRAND wird nicht unterstützt.**  
**RDSEED wird nicht unterstützt.**  
**Unterstützt RDTSCP**  
**RTM wird nicht unterstützt.**  
**Unterstützt SEP**  
**SHA wird nicht unterstützt.**  
**Unterstützt SSE**  
**Unterstützt SSE2**  
**Unterstützt SSE3**  
**Unterstützt SSE4.1**  
**Unterstützt SSE4.2**  
**SSE4a wird nicht unterstützt.**  
**Unterstützt SSSE3**  
**Unterstützt SYSCALL**  
**TBM wird nicht unterstützt.**  
**XOP wird nicht unterstützt.**  
**Unterstützt XSAVE**   
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)