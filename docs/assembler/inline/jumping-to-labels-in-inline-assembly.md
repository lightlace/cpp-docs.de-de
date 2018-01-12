---
title: Springen zu Bezeichnungen in der Inlineassembly | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline assembly, jumping to labels
- labels, in inline assembly
- __asm keyword [C++], labels
- case sensitivity, labels in inline assembly
- labels, in __asm blocks
- jumping to labels in inline assembly
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1170a12aefeb53083d5627b1b84639403ea17182
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="jumping-to-labels-in-inline-assembly"></a>Springen zu Bezeichnungen in der Inlineassembly
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wie eine normale C oder C++ Bezeichnung und eine Bezeichnung in einem `__asm` Block ist der Gültigkeitsbereich der Funktion, die in der sie (nicht nur in dem Block definiert ist). Beide Assemblyanweisungen und `goto` Anweisungen können springen zu Bezeichnungen innerhalb oder außerhalb der `__asm` Block.  
  
 Bezeichnungen `__asm` Blöcke sind nicht in der Groß-/Kleinschreibung beachtet; beide `goto` Anweisungen und Assemblyanweisungen verweisen auf diese Bezeichnungen unabhängig von der Fall. C- und C++-Bezeichnungen Groß-/Kleinschreibung beachtet nur bei Verwendung durch `goto` Anweisungen. Assemblyanweisungen können auf eine C- oder C++-Bezeichnung ohne Berücksichtigung von Groß-springen.  
  
 Der folgende Code zeigt alle Permutationen:  
  
```  
void func( void )  
{  
   goto C_Dest;  /* Legal: correct case   */  
   goto c_dest;  /* Error: incorrect case */  
  
   goto A_Dest;  /* Legal: correct case   */  
   goto a_dest;  /* Legal: incorrect case */  
  
   __asm  
   {  
      jmp C_Dest ; Legal: correct case  
      jmp c_dest ; Legal: incorrect case  
  
      jmp A_Dest ; Legal: correct case  
      jmp a_dest ; Legal: incorrect case  
  
      a_dest:    ; __asm label  
   }  
  
   C_Dest:       /* C label */   
   return;  
}  
int main()  
{  
}  
```  
  
 Verwenden Sie nicht als Bezeichnungen in der C-Bibliothek-Funktionsnamen `__asm` blockiert. Möchten Sie verwenden z. B. möglicherweise `exit` als Bezeichnung, wie folgt:  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 Da **beenden** ist der Name einer C-Bibliothek-Funktion mit diesem Code kann dazu führen, dass einen Sprung zu den **beenden** -Funktion anstelle von an die gewünschte Position.  
  
 Wie in MASM-Programme, Dollarsymbols (`$`) dient als den aktuellen Speicherort Leistungsindikator. Es ist eine Bezeichnung für die Anweisung, die derzeit zusammengestellt. In `__asm` blockiert sein Hauptverwendungszweck besteht, lange bedingte Sprünge:  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)