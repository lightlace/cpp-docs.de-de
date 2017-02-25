---
title: "Compilerwarnung (Stufe&#160;1 und&#160;3) C4793 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4793"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4793"
  - "C6630"
  - "C6631"
  - "C6634"
  - "C6635"
  - "C6636"
  - "C6637"
  - "C6638"
  - "C6639"
  - "C6640"
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
caps.latest.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 28
---
# Compilerwarnung (Stufe&#160;1 und&#160;3) C4793
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Funktion wird als systemeigener Code kompiliert: 'Grund'  
  
 Der Compiler kann *function* nicht in verwalteten Code kompilieren, auch wenn die [\/clr](../../build/reference/clr-common-language-runtime-compilation.md)\-Compileroption angegeben wird.  Der Compiler gibt stattdessen Warnung C4793 und eine Meldung mit Erläuterungen zur Fortsetzung aus und kompiliert anschließend *function* in systemeigenen Code.  Die Fortsetzungsmeldung enthält in *reason* Text, der beschreibt, warum *function* nicht in `MSIL` kompiliert werden kann.  
  
 Dies ist eine Warnung der Stufe 1, wenn Sie die `/clr:pure`\-Compileroption angeben.  
  
 In der folgenden Tabelle werden alle möglichen Fortsetzungsmeldungen aufgelistet.  
  
|Meldung mit Grund|Hinweise|  
|-----------------------|--------------|  
|Ausgerichtete Datentypen werden in verwaltetem Code nicht unterstützt.|Die CLR muss Daten nach Bedarf zuordnen können, was unter Umständen nicht möglich ist, wenn die Daten mit Deklarationen wie [\_\_m128](../../cpp/m128.md) oder [align](../../cpp/align-cpp.md) ausgerichtet sind.|  
|Funktionen, die \_\_ImageBase verwenden, werden in verwaltetem Code nicht unterstützt.|`__ImageBase` ist ein spezielles Linkersymbol, das in der Regel nur von systemeigenem Code auf niedriger Ebene zum Laden einer DLL verwendet wird.|  
|Varargs werden von der Compileroption '\/clr' nicht unterstützt.|Systemeigene Funktionen können keine verwalteten Funktionen aufrufen, die über [Variablenargumentlisten](../../misc/variable-argument-lists.md) \(varargs\) verfügen, da für die Funktionen andere Stapellayoutanforderungen gelten.  Wenn Sie aber die `/clr:pure`\-Compileroption angeben, werden Variablenargumentlisten unterstützt, da die Assembly nur verwaltete Funktionen enthalten kann.  Weitere Informationen finden Sie unter [Reiner und überprüfbarer Code](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|  
|Daten, die mit dem Modifizierer \_\_ptr32 deklariert wurden, werden von der 64\-Bit\-CLR nicht unterstützt.|Ein Zeiger muss die gleiche Größe wie ein systemeigener Zeiger auf der aktuellen Plattform haben.  Weitere Informationen finden Sie unter [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md).|  
|Daten, die mit dem Modifizierer \_\_ptr64 deklariert wurden, werden von der 32\-Bit\-CLR nicht unterstützt.|Ein Zeiger muss die gleiche Größe wie ein systemeigener Zeiger auf der aktuellen Plattform haben.  Weitere Informationen finden Sie unter [\_\_ptr32, \_\_ptr64](../../cpp/ptr32-ptr64.md).|  
|Eine oder mehrere systeminterne Funktionen werden in verwaltetem Code nicht unterstützt.|Der Name der systeminternen Funktion ist zum Zeitpunkt der Ausgabe der Meldung nicht verfügbar.  Aber eine systeminterne Funktion, die diese Meldung verursacht, stellt i. d. R. eine Computeranweisung auf niedriger Ebene dar.|  
|Die systemeigene Inlineassembly \_\_asm wird in verwaltetem Code nicht unterstützt.|[Inlineassemblycode](../../assembler/inline/asm.md) kann beliebigen systemeigenen Code enthalten, der nicht verwaltet werden kann.|  
|Ein virtueller Funktionsthunk muss als systemeigen kompiliert werden, wenn es sich nicht um den Typ \_\_clrcall handelt.|Ein virtueller Funktionsthunk, bei dem es sich nicht um den Typ [\_\_clrcall](../../cpp/clrcall.md) handelt, muss eine nicht verwaltete Adresse verwenden.|  
|Eine Funktion, die \_setjmp verwendet, muss als systemeigen kompiliert werden.|Die CLR muss zur Steuerung der Programmausführung in der Lage sein.  Die [setjmp](../../cpp/using-setjmp-longjmp.md)\-Funktion umgeht jedoch die reguläre Programmausführung durch Speicherung und Wiederherstellung von Informationen auf niedriger Ebene wie Register und Ausführungsstatus.|  
  
## Beispiel  
 Im folgenden Beispiel wird C4793 generiert.  
  
```  
// C4793.cpp  
// compile with: /c /clr /W3   
// processor: x86  
int asmfunc(void) {   // C4793, compiled as unmanaged, native code  
   __asm {  
      mov eax, 0  
   }  
}  
```  
  
  **Warnung C4793: "asmfunc": Die Funktion wird als systemeigener Code kompiliert:**  
 **Die systemeigene Inlineassembly \_\_asm wird in verwaltetem Code nicht unterstützt.**   
## Beispiel  
 Im folgenden Beispiel wird C4793 generiert.  
  
```  
// C4793_b.cpp  
// compile with: /c /clr /W3  
#include <setjmp.h>  
jmp_buf test_buf;  
  
void f() {  
   setjmp(test_buf);   // C4793 warning  
}  
```  
  
  **Warnung C4793, "f": Die Funktion wird als systemeigener Code kompiliert:**  
 **Eine Funktion, die \_setjmp verwendet, muss als systemeigen kompiliert werden.**