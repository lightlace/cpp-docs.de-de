---
title: "Springen zu Bezeichnungen in der Inlineassembly | Microsoft Docs"
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
  - "__asm-Schlüsselwort [C++], Bezeichnungen"
  - "Berücksichtigung der Groß-/Kleinschreibung, Bezeichnungen in der Inlineassembly"
  - "Inlineassembly, Springen zu Bezeichnungen"
  - "Springen zu Bezeichnungen in der Inlineassembly"
  - "Bezeichnungen, In __asm-Blöcken"
  - "Bezeichnungen, In der Inlineassembly"
ms.assetid: 36c18b97-8981-4631-9dfd-af6c14a04297
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Springen zu Bezeichnungen in der Inlineassembly
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Microsoft\-spezifisch  
 Wie eine gewöhnliche C\# oder C\+\+\-Bezeichnung weist eine Bezeichnung in einem Block Bereich `__asm` während der Funktion, in der er definiert wurde \(nicht nur im Block\).  `goto` und Assemblyanweisungen können Anweisungen zu den Bezeichnungen innerhalb oder außerhalb der Bindung `__asm`\-Block.  
  
 Die Bezeichnungen, die in `__asm` Blöcke definiert sind, wird die Groß\-\/Kleinschreibung nicht beachtet. `goto` können diese Assemblyanweisungen \- Anweisungen und Sprungmarken ohne Berücksichtigung der Groß\-\/Kleinschreibung verweisen.  C\- und C\+\+\-Bezeichnungen wird die Groß\-\/Kleinschreibung beachtet, wenn sie nur von `goto`\-Anweisungen verwendet werden.  Assemblyanweisungen können eine oder C\+\+\-Bezeichnung ohne Berücksichtigung der Groß\-\/Kleinschreibung wechseln.  
  
 Der folgende Code zeigt alle Permutationen an:  
  
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
  
 Verwenden Sie C\-Bibliotheks funktionsnamen nicht als Bezeichnungen in `__asm` Blöcke.  Beispielsweise können Sie gereizt werden, um `exit` als Bezeichnung verwendet werden soll, wie folgt:  
  
```  
; BAD TECHNIQUE: using library function name as label  
jne exit  
   .  
   .  
   .  
exit:  
   ; More __asm code follows  
```  
  
 Da **Beenden** der Name der Wechselstrom\-Bibliotheksfunktion ist, kann dieser Code einen Sprung zur **Beenden**\-Funktion statt an die gewünschte Position.  
  
 Wie in MASM\-Programmen, liefert das Dollar \(Symbol\)`$`als aktueller Adressenzähler.  Es handelt sich um eine Bezeichnung für die Anweisung, die gerade assembliert wird.  In `__asm` Blöcke ist die wichtigste mit langen bedingte Sprünge auszuführen:  
  
```  
jne $+5 ; next instruction is 5 bytes long  
jmp farlabel  
; $+5  
   .  
   .  
   .  
farlabel:  
```  
  
 **Microsoft ENDES bestimmten**  
  
## Siehe auch  
 [Inlineassembler](../../assembler/inline/inline-assembler.md)