---
title: __asm | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- __asm
- __asm_cpp
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], vs. asm blocks
- __asm keyword [C++]
ms.assetid: 77ff3bc9-a492-4b5e-85e1-fa4e414e79cd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77e09f6af92839c6113c9c5ba375a1583bcf7149
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="asm"></a>__asm
**Microsoft-spezifisch**  
  
 Das `__asm`-Schlüsselwort ruft den Inlineassembler auf und kann immer da auftreten, wo eine C- oder C++-Anweisung gültig ist. Es kann nicht allein stehen. Ihm muss eine Assemblyanweisung, eine Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen sind, oder zumindest ein leeres Paar geschweifter Klammern folgen. Der Begriff "`__asm`-Block" bezieht sich hier auf eine beliebige Anweisung bzw. Gruppe von Anweisungen, unabhängig davon, ob in geschweifte Klammern gesetzt oder nicht.  
  
> [!NOTE]
>  Visual C++-Unterstützung für das standardmäßige `asm`-C++-Schlüsselwort ist dahingehend eingeschränkt, dass der Compiler keinen Fehler für das Schlüsselwort generiert. Ein `asm`-Block generiert jedoch keinen sinnvollen Code. Verwenden Sie `__asm` anstelle von `asm`.  
  
 Syntax:  
  
 __asm *Assemblyanweisung* [;]  
  
 __asm { *Assembly Anweisungsliste* } [;]  
  
## <a name="grammar"></a>Grammatik  
 `__asm`  `assembly-instruction`  `;`Abonnieren von  
  
 `__asm {`  `assembly-instruction-list`  `};`Abonnieren von  
  
 *Assembly-Anweisung-List*:  
 `assembly-instruction` `;`Abonnieren von  
  
 `assembly-instruction` `;` `assembly-instruction-list` `;`Abonnieren von  
  
 Wenn es ohne geschweifte Klammern verwendet wird, bedeutet das `__asm`-Schlüsselwort, dass der Rest der Zeile eine Assemblysprachanweisung ist. Wenn es mit geschweiften Klammern verwendet wird, bedeutet es, dass jede Zeile zwischen den geschweiften Klammern eine Assemblysprachanweisung ist. Aus Gründen der Kompatibilität mit früheren Versionen wird `_asm` synonym für `__asm` verwendet.  
  
 Da das `__asm`-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie Assemblyanweisungen in die gleiche Zeile einfügen:  
  
 Vor Visual C++ 2005 führte die Anweisung  
  
```  
__asm int 3  
```  
  
 nicht dazu, dass systemeigenen Code generiert werden, bei der Kompilierung mit **"/ CLR"**; der Compiler übersetzte die Anweisung in eine CLR-unterbrechungsanweisung.  
  
 `__asm int 3` führt jetzt zur Generierung von systemeigenem Code für die Funktion. Wenn Sie möchten eine Funktion, um einen Haltepunkt im Code verursachen und zu verwenden, wenn Sie diese Funktion in MSIL kompiliert werden soll [__debugbreak](../../intrinsics/debugbreak.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Codefragment ist ein einfacher `__asm`-Block, der in geschweifte Klammern eingeschlossen ist:  
  
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
  
 Da das `__asm`-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie auch Assemblyanweisungen in die gleiche Zeile einfügen:  
  
```  
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al  
```  
  
 Alle drei Beispiele generieren den gleichen Code, aber das erste Format (der `__asm`-Block ist in geschweifte Klammern eingeschlossen) bietet einige Vorteile. Die geschweiften Klammern trennen den Assemblycode klar von C- oder C++-Code und vermeiden so die unnötige Wiederholung des `__asm`-Schlüsselworts. Geschweifte Klammern können auch Mehrdeutigkeiten verhindern. Wenn Sie eine C- oder C++- Anweisung in die gleiche Zeile wie einen `__asm`-Block eingeben möchten, müssen Sie den Block in geschweifte Klammern einschließen. Ohne die Klammern kann der Compiler nicht feststellen, wo Assemblycode endet und C- oder C++-Anweisungen beginnen. Und Sie können Text einfach aus bestehenden MASM-Quelldateien kopieren und einfügen, da der Text in geschweiften Klammer das gleiche Format aufweist wie gewöhnlicher MASM-Text.  
  
 Anders als bei geschweiften Klammern in C und C++ wirkt sich das Einschließen eines `__asm`-Blocks in geschweifte Klammern nicht auf den Variablenbereich aus. Sie können `__asm`-Blöcke auch schachteln. Schachtelung wirkt sich nicht auf den Variablenbereich aus.  
  
 **Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../../cpp/keywords-cpp.md)   
 [Inlineassembler](../../assembler/inline/inline-assembler.md)