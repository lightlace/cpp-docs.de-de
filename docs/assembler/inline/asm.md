---
title: "__asm | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__asm"
  - "__asm_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__asm-Schlüsselwort [C++]"
  - "__asm-Schlüsselwort [C++], Im Vergleich zu asm-Blöcken"
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# __asm
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Das `__asm`\-Schlüsselwort ruft den Inlineassembler auf und kann immer da auftreten, wo eine C\- oder C\+\+\-Anweisung gültig ist.  Es kann nicht allein stehen.  Ihm muss eine Assemblyanweisung, eine Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen sind, oder zumindest ein leeres Paar geschweifter Klammern folgen.  Der Begriff "`__asm`\-Block" bezieht sich hier auf eine beliebige Anweisung bzw. Gruppe von Anweisungen, unabhängig davon, ob in geschweifte Klammern gesetzt oder nicht.  
  
> [!NOTE]
>  Visual C\+\+\-Unterstützung für das standardmäßige `asm`\-C\+\+\-Schlüsselwort ist dahingehend eingeschränkt, dass der Compiler keinen Fehler für das Schlüsselwort generiert.  Ein `asm`\-Block generiert jedoch keinen sinnvollen Code.  Verwenden Sie `__asm` anstelle von `asm`.  
  
 Syntax:  
  
 \_\_asm *assembly\-instruction* \[ ; \]  
  
 \_\_asm { *assembly\-instruction\-list* } \[ ; \]  
  
## Grammatik  
 `__asm`  `assembly-instruction`  `;` opt  
  
 `__asm {`  `assembly-instruction-list`  `};` opt  
  
 *assembly\-instruction\-list*:  
 `assembly-instruction` `;` opt  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;` opt  
  
 Wenn es ohne geschweifte Klammern verwendet wird, bedeutet das `__asm`\-Schlüsselwort, dass der Rest der Zeile eine Assemblysprachanweisung ist.  Wenn es mit geschweiften Klammern verwendet wird, bedeutet es, dass jede Zeile zwischen den geschweiften Klammern eine Assemblysprachanweisung ist.  Aus Gründen der Kompatibilität mit früheren Versionen wird `_asm` synonym für `__asm` verwendet.  
  
 Da das `__asm`\-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie Assemblyanweisungen in die gleiche Zeile einfügen:  
  
 Vor Visual C\+\+ 2005 führte die Anweisung  
  
```  
__asm int 3  
```  
  
 nicht dazu, dass systemeigener Code generiert wurde, wenn er mit **\/clr** kompiliert wurde. Der Compiler übersetzte die Anweisung in eine CLR\-Unterbrechungsanweisung.  
  
 `__asm int 3` führt jetzt zur Generierung von systemeigenem Code für die Funktion.  Wenn eine Funktion einen Haltepunkt im Code verursachen und diese Funktion in MSIL kompiliert werden soll, verwenden Sie [\_\_debugbreak](../../intrinsics/debugbreak.md).  
  
## Beispiel  
 Das folgende Codefragment ist ein einfacher `__asm`\-Block, der in geschweifte Klammern eingeschlossen ist:  
  
```  
__asm {  
   mov al, 2  
   mov dx, 0xD007  
   out dx, al  
}  
```  
  
 Alternativ können Sie `__asm` vor jede Assemblyanweisung setzen:  
  
```  
__asm mov al, 2  
__asm mov dx, 0xD007  
__asm out dx, al  
```  
  
 Da das `__asm`\-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie auch Assemblyanweisungen in die gleiche Zeile einfügen:  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 Alle drei Beispiele generieren den gleichen Code, aber das erste Format \(der `__asm`\-Block ist in geschweifte Klammern eingeschlossen\) bietet einige Vorteile.  Die geschweiften Klammern trennen den Assemblycode klar von C\- oder C\+\+\-Code und vermeiden so die unnötige Wiederholung des `__asm`\-Schlüsselworts.  Geschweifte Klammern können auch Mehrdeutigkeiten verhindern.  Wenn Sie eine C\- oder C\+\+\- Anweisung in die gleiche Zeile wie einen `__asm`\-Block eingeben möchten, müssen Sie den Block in geschweifte Klammern einschließen.  Ohne die Klammern kann der Compiler nicht feststellen, wo Assemblycode endet und C\- oder C\+\+\-Anweisungen beginnen.  Und Sie können Text einfach aus bestehenden MASM\-Quelldateien kopieren und einfügen, da der Text in geschweiften Klammer das gleiche Format aufweist wie gewöhnlicher MASM\-Text.  
  
 Anders als bei geschweiften Klammern in C und C\+\+ wirkt sich das Einschließen eines `__asm`\-Blocks in geschweifte Klammern nicht auf den Variablenbereich aus.  Sie können `__asm`\-Blöcke auch schachteln. Schachtelung wirkt sich nicht auf den Variablenbereich aus.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../../cpp/keywords-cpp.md)   
 [Inlineassembler](../../assembler/inline/inline-assembler.md)