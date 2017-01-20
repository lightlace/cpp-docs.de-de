---
title: "Inlineassembler (C)"
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
  - "C"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C]"
  - "Inlineassembler [C]"
ms.assetid: 821acc77-60b1-434c-ba54-2ba930a25ab4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Inlineassembler (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Mit dem Inlineassembler können Sie Assemblysprachanweisungen direkt in C\-Quellprogramme einbetten, ohne zusätzliche Assembly\- oder Verknüpfungsschritte.  Der Inlineassembler ist im Compiler integriert, daher benötigen Sie keinen getrennten Assembler wie den Microsoft Macro Assembler \(MASM\).  
  
 Da der Inlineassembler keine separaten Assembly\- und Verknüpfungsschritte erfordert, ist er einfacher als ein getrennter Assembler.  Der Inlineassemblycode kann alle C\-Variablen und \-Funktionsnamen verwenden, die sich im Gültigkeitsbereich befinden. Daher ist es einfach, ihn in den C\-Programmcode zu integrieren.  Und da der Assemblycode mit C\-Anweisungen kombiniert werden kann, kann er Aufgaben ausführen, die in C allein mühsam oder unmöglich sind.  
  
 Das `__asm`\-Schlüsselwort ruft den Inlineassembler auf und kann überall vorkommen, wo eine C\-Anweisung gültig ist.  Es kann nicht allein stehen.  Ihm muss eine Assemblyanweisung, eine Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen sind, oder zumindest ein leeres Paar geschweifter Klammern folgen.  Der Begriff "`__asm`\-Block" bezieht sich hier auf eine beliebige Anweisung bzw. Gruppe von Anweisungen, unabhängig davon, ob in geschweifte Klammern gesetzt oder nicht.  
  
 Der folgende Code ist ein einfacher `__asm`\-Block, der in geschweifte Klammern eingeschlossen ist. \(Der Code ist eine Prologsequenz für eine benutzerdefinierte Funktion\).  
  
```  
__asm  
{  
   push ebp  
   mov  ebp, esp  
   sub  esp, __LOCAL_SIZE  
}  
```  
  
 Alternativ können Sie `__asm` vor jede Assemblyanweisung setzen:  
  
```  
__asm push ebp  
__asm mov  ebp, esp  
__asm sub  esp, __LOCAL_SIZE  
```  
  
 Da das `__asm`\-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie die Assemblyanweisungen auch in die gleiche Zeile einfügen:  
  
```  
__asm push ebp   __asm mov  ebp, esp   __asm sub  esp, __LOCAL_SIZE   
```  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Funktionsattribute](../c-language/function-attributes.md)