---
title: "Inlineassembler | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assembler [C++]"
  - "Assembler [C++], Inline"
  - "Assemblysprache [C++], Inline"
  - "Inlineassembler [C++]"
  - "Inlineassembly [C++]"
ms.assetid: 7e13f18f-3628-4306-8b81-4a6d09c043fe
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Inlineassembler
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Die Assemblysprache dient vielen Zwecken, wie etwa der Verbesserung der Programmgeschwindigkeit, der Verringerung der Speicheranforderungen und der Steuerung der Hardware.  Sie können den Inlineassembler verwenden, um Assemblysprachanweisungen ohne zusätzliche Assembly\- und Verknüpfungsschritte direkt in die C\- und C\+\+\-Quellprogramme einzubetten.  Der Inlineassembler wird in den Compiler integriert, daher benötigen Sie keinen getrennten Assembler wie den Microsoft Macro Assembler \(MASM\).  
  
> [!NOTE]
>  Programme mit Inlineassemblercode sind nicht vollständig auf andere Hardwareplattformen übertragbar.  Wenn Ihnen Portabilität wichtig ist, vermeiden Sie beim Entwerfen die Verwendung des Inlineassemblers.  
  
 Die Inlineassembly wird von ARM\- und [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\-Prozessoren nicht unterstützt.  In folgenden Themen wird erklärt, wie der Inlineassembler von Visual C\/C\+\+ mit x86\-Prozessoren zu verwenden ist:  
  
-   [Übersicht über Inlineassembler](../../assembler/inline/inline-assembler-overview.md)  
  
-   [Vorteile von Inlineassemblys](../../assembler/inline/advantages-of-inline-assembly.md)  
  
-   [\_\_asm](../../assembler/inline/asm.md)  
  
-   [Verwenden der Assemblysprache in \_\_asm\-Blöcken](../../assembler/inline/using-assembly-language-in-asm-blocks.md)  
  
-   [Verwenden von C oder C\+\+ in \_\_asm\-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)  
  
-   [Verwenden und Beibehalten von Registern in der Inlineassembly](../../assembler/inline/using-and-preserving-registers-in-inline-assembly.md)  
  
-   [Springen zu Bezeichnungen in der Inlineassembly](../../assembler/inline/jumping-to-labels-in-inline-assembly.md)  
  
-   [Aufrufen von C\-Funktionen in der Inlineassembly](../../assembler/inline/calling-c-functions-in-inline-assembly.md)  
  
-   [Aufrufen von C\+\+\-Funktionen in der Inlineassembly](../../assembler/inline/calling-cpp-functions-in-inline-assembly.md)  
  
-   [Definieren von \_\_asm\-Blöcken als C\-Makros](../../assembler/inline/defining-asm-blocks-as-c-macros.md)  
  
-   [Optimieren der Inlineassembly](../../assembler/inline/optimizing-inline-assembly.md)  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Intrinsische Compilerfunktionen und Assemblysprache](../../intrinsics/compiler-intrinsics-and-assembly-language.md)   
 [C\+\+\-Sprachreferenz](../../cpp/cpp-language-reference.md)