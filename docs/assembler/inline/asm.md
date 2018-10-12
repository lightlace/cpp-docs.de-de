---
title: __asm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/09/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
f1_keywords:
- __asm
- _asm
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
ms.openlocfilehash: dd279a6324aec6eba50c6c3b7ffe846200d45fe1
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/12/2018
ms.locfileid: "49161722"
---
# <a name="asm"></a>__asm

**Microsoft-spezifisch**

Das `__asm`-Schlüsselwort ruft den Inlineassembler auf und kann immer da auftreten, wo eine C- oder C++-Anweisung gültig ist. Es kann nicht allein stehen. Ihm muss eine Assemblyanweisung, eine Gruppe von Anweisungen, die in geschweifte Klammern eingeschlossen sind, oder zumindest ein leeres Paar geschweifter Klammern folgen. Der Begriff "`__asm`-Block" bezieht sich hier auf eine beliebige Anweisung bzw. Gruppe von Anweisungen, unabhängig davon, ob in geschweifte Klammern gesetzt oder nicht.

> [!NOTE]
> Visual C++-Unterstützung für das standardmäßige `asm`-C++-Schlüsselwort ist dahingehend eingeschränkt, dass der Compiler keinen Fehler für das Schlüsselwort generiert. Ein `asm`-Block generiert jedoch keinen sinnvollen Code. Verwenden Sie `__asm` anstelle von `asm`.

## <a name="grammar"></a>Grammatik

*ASM-Block*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm** *Assemblyanweisung* **;** <sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm {** *Assembly-Anweisung-List* **}** **;** <sub>deaktivieren</sub>

*Assembly-Anweisung-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-Anweisung* **;** <sub>deaktivieren</sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-Anweisung* **;** *Assembly-Anweisung-List* **;** <sub>deaktivieren</sub>

## <a name="remarks"></a>Hinweise

Wenn es ohne geschweifte Klammern verwendet wird, bedeutet das `__asm`-Schlüsselwort, dass der Rest der Zeile eine Assemblysprachanweisung ist. Wenn es mit geschweiften Klammern verwendet wird, bedeutet es, dass jede Zeile zwischen den geschweiften Klammern eine Assemblysprachanweisung ist. Aus Gründen der Kompatibilität mit früheren Versionen wird `_asm` synonym für `__asm` verwendet.

Da das `__asm`-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie Assemblyanweisungen in die gleiche Zeile einfügen:

Vor Visual C++ 2005 führte die Anweisung

```cpp
__asm int 3
```

führte nicht zu einem systemeigenen Code generiert werden, bei der Kompilierung mit **"/ CLR"**; der Compiler übersetzte die Anweisung in einer CLR-unterbrechungsanweisung.

`__asm int 3` führt jetzt zur Generierung von systemeigenem Code für die Funktion. Wenn Sie möchten eine Funktion, die einen Haltepunkt im Code verursachen und zu verwenden, wenn Sie möchten, dass diese Funktion in MSIL kompiliert [__debugbreak](../../intrinsics/debugbreak.md).

Für die Kompatibilität mit früheren Versionen **_asm** ist ein Synonym für **__asm** , wenn Compileroption [/Za \(spracherweiterungen deaktivieren)](../../build/reference/za-ze-disable-language-extensions.md) angegeben ist.

## <a name="example"></a>Beispiel

Das folgende Codefragment ist ein einfacher `__asm`-Block, der in geschweifte Klammern eingeschlossen ist:

```cpp
__asm {
   mov al, 2
   mov dx, 0xD007
   out dx, al
}
```

Alternativ können Sie `__asm` vor jede Assemblyanweisung setzen:

```cpp
__asm mov al, 2
__asm mov dx, 0xD007
__asm out dx, al
```

Da das `__asm`-Schlüsselwort ein Trennzeichen für Anweisungen ist, können Sie auch Assemblyanweisungen in die gleiche Zeile einfügen:

```cpp
__asm mov al, 2   __asm mov dx, 0xD007   __asm out dx, al
```

Alle drei Beispiele generieren den gleichen Code, aber das erste Format (der `__asm`-Block ist in geschweifte Klammern eingeschlossen) bietet einige Vorteile. Die geschweiften Klammern trennen den Assemblycode klar von C- oder C++-Code und vermeiden so die unnötige Wiederholung des `__asm`-Schlüsselworts. Geschweifte Klammern können auch Mehrdeutigkeiten verhindern. Wenn Sie eine C- oder C++- Anweisung in die gleiche Zeile wie einen `__asm`-Block eingeben möchten, müssen Sie den Block in geschweifte Klammern einschließen. Ohne die Klammern kann der Compiler nicht feststellen, wo Assemblycode endet und C- oder C++-Anweisungen beginnen. Und Sie können Text einfach aus bestehenden MASM-Quelldateien kopieren und einfügen, da der Text in geschweiften Klammer das gleiche Format aufweist wie gewöhnlicher MASM-Text.

Anders als bei geschweiften Klammern in C und C++ wirkt sich das Einschließen eines `__asm`-Blocks in geschweifte Klammern nicht auf den Variablenbereich aus. Sie können `__asm`-Blöcke auch schachteln. Schachtelung wirkt sich nicht auf den Variablenbereich aus.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Schlüsselwörter](../../cpp/keywords-cpp.md)<br/>
[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>