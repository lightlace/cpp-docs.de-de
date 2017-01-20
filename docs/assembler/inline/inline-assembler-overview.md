---
title: "Inlineassembler-&#220;bersicht"
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
  - "__asm-Schlüsselwort [C++], Aufrufen des Inlineassemblers"
  - "Inlineassembler"
  - "Inlineassembly, Inlineassembler"
  - "Aufrufen des Inlineassemblers"
ms.assetid: d990331a-0e33-4760-8d7a-b720b0288335
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Inlineassembler-&#220;bersicht
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Der Inlineassembler können Sie Assemblysprachanweisungen in C\# und C\+\+\-Quellprogrammen ohne zusätzliche Assembly\- und Link Bereitstellungsschritte einbetten.  Der Inlineassembler wird in den Compiler erstellt benötigen Sie keinen separaten Assembler \(z. B. der Microsoft Macro Assembler \(MASM\).  
  
 Da der Inlineassembler nicht Schritte der separaten Assemblys und des Links erfordert, ist es einfacher als ein separater Assembler.  Inlineassemblycode kann jedes C oder C\+\+\-Variable oder Funktionsnamens verwenden, die im Gültigkeitsbereich befindet, ist es einfach, sodass er mit C\- und C\+\+\-Code des Programms zu integrieren.  Und da der Assemblycode mit C\- und C\+\+\-Anweisungen kombiniert werden kann, kann diese Aufgaben ausführen, die lästig oder in C oder C\+\+ nicht unmöglich sind.  
  
 Das Schlüsselwort [\_\_asm](../../assembler/inline/asm.md) den Inlineassembler auf und kann, oder C\+\+\-Anweisung scheinen, wo eine gültig ist.  Sie kann nicht allein angegeben werden.  Es muss eine Assemblyanweisung, einer Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen werden, oder allerwenigsten aus einem leeren Paar Klammern folgen.  Der Begriff „Block“ bezieht sich auf eine beliebige Stelle`__asm`\-Anweisung bzw. Gruppe von Anweisungen, ob in geschweifte Klammern an.  
  
 Der folgende Code ist ein einfacher `__asm`\-Block, der in geschweifte Klammern eingeschlossen wird.  \(Der Code ist eine benutzerdefinierte Funktion einleitungs sequence\).  
  
```  
// asm_overview.cpp  
// processor: x86  
void __declspec(naked) main()  
{  
    // Naked functions must provide their own prolog...  
    __asm {  
        push ebp  
        mov ebp, esp  
        sub esp, __LOCAL_SIZE  
    }  
  
    // ... and epilog  
    __asm {  
        pop ebp  
        ret  
    }  
}  
```  
  
 Alternativ können Sie `__asm` vor jeder Assemblyanweisung setzen:  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE  
```  
  
 Da das `__asm`\-Schlüsselwort ein Trennzeichen ist, können Sie auch Assemblyanweisungen auf dieselbe Zeile einfügen:  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)