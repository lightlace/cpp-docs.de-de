---
title: "MASM for x64 (ml64.exe)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ml64.exe"
  - "ml"
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# MASM for x64 (ml64.exe)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der Assembler wird der ml64.exe Assemblersprache, der [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] akzeptiert.  Weitere Informationen über ml64.exe\-Compileroptionen finden Sie unter [ML and ML64 Command\-Line Reference](../../assembler/masm/ml-and-ml64-command-line-reference.md).  
  
 Inline ASM wird nicht für [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]unterstützt.  Verwenden Sie MASM oder systeminterne Funktionen des Compilers \([x64 Intrinsics](assetId:///5d1f5d3e-156e-4ebf-932e-fd09be7ced62)\).  
  
 Die beiden Problemumgehungen sind separate Assembly mit MASM \(x64\) und vollständig unterstützt systeminterne Funktionen des Compilers verfügbar.  Wir haben viele systeminterne Funktionen hinzugefügt, um Kunden zu ermöglichen, Insbesondere FUNCTION\-Anweisungen zu verwenden \(z. B.  privilegierte, der Überprüfung\/Test, ineinandergegriffen Bit, ETC…\) in plattformübergreifendem eine Weise zu schließen.  
  
## ml64\-Specific Direktive  
 Verwenden Sie die folgenden Direktiven mit ml64.exe:  
  
-   [.ALLOCSTACK](../../assembler/masm/dot-allocstack.md)  
  
-   [.ENDPROLOG](../../assembler/masm/dot-endprolog.md)  
  
-   [.PUSHFRAME](../../assembler/masm/dot-pushframe.md)  
  
-   [.PUSHREG](../../assembler/masm/dot-pushreg.md)  
  
-   [.SAVEREG](../../assembler/masm/dot-savereg.md)  
  
-   [.SAVEXMM128](../../assembler/masm/dot-savexmm128.md)  
  
-   [.SETFRAME](../../assembler/masm/dot-setframe.md)  
  
 Außerdem wurden die [PROC](../../assembler/masm/proc.md)\-Direktive zur Verwendung mit ml64.exe aktualisiert.  
  
## 32\-Bit\-Adressiermethode \(Adressen\-Größen\-Überschreibung\)  
 MASM gibt die Adresse der Überschreibung der Größe 0x67 aus, wenn ein Speicher operand 32\-Bit\-Register enthält.  Die folgenden Beispiele führen beispielsweise die Adressen Überschreibung Haupt\- ausgegeben werden:  
  
```  
mov rax, QWORD PTR [ecx]  
mov eax, DWORD PTR [ecx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10d+0100h]  
prefetch [eax]  
movnti rax, QWORD PTR [r8d]  
```  
  
 MASM wird davon ausgegangen, dass beim Ausführen einer 32\-Bit\-Verschiebung alleine des Speichers operand angezeigt wird, das 64\-Bit\-Adressieren vorgesehen ist.  Es gibt derzeit keine Unterstützung für 32\-Bit adressierend mit solchen Operanden.  
  
 Schließlich generiert das Kombinieren von Registern Haupt\- in einem Speicher operanden, wie im folgenden Code dargestellt, einen Fehler.  
  
```  
mov eax, DWORD PTR [rcx*2+r10d]  
mov eax, DWORD PTR [ecx*2+r10+0100h]  
```  
  
## Siehe auch  
 [Microsoft Macro Assembler Reference](../../assembler/masm/microsoft-macro-assembler-reference.md)