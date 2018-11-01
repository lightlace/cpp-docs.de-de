---
title: while-Anweisung (C) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- while
dev_langs:
- C++
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6993f209f5e7c5ab6f56ae886f2d57ba90a19936
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48860650"
---
# <a name="while-statement-c"></a>while-Anweisung (C)

Mit der `while`-Anweisung können Sie eine Anweisung solange wiederholen, bis ein angegebener Ausdruck den Wert "false" aufweist.

## <a name="syntax"></a>Syntax

*iteration-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (**  *expression*  **)**  *statement*

Der *Ausdruck* muss einen arithmetischen Typ oder einen Zeigertyp aufweisen. Die Ausführung erfolgt folgendermaßen:

1. Der *Ausdruck* wird ausgewertet.

1. Wenn der *Ausdruck* zu Beginn den Wert „false“ hat, wird der Text der `while`-Anweisung nicht ausgeführt, und das Steuerelement wird von der `while`-Anweisung an die nächste Anweisung im Programm übergeben.

   Wenn der *Ausdruck* den Wert „true“ hat (ungleich null), wird der Text der Anweisung ausgeführt und der Prozess ab Schritt 1 wiederholt.

Die `while`-Anweisung kann auch beendet werden, wenn eine **break**-, `goto`- oder `return`-Anweisung im Anweisungstext ausgeführt wird. Verwenden Sie die **continue**-Anweisung, um eine Iteration zu beenden, ohne die `while`-Schleife zu beenden. Die **continue**-Anweisung übergibt das Steuerelement an die nächste Iteration der `while`-Anweisung.

In diesem Beispiel wird die `while`-Anweisung veranschaulicht:

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

In diesem Beispiel werden Zeichen aus `string2` nach `string1` kopiert. Wenn `i` größer als oder gleich 0 ist, wird `string2[i]` an `string1[i]` zugewiesen und `i` dekrementiert. Wenn `i` 0 erreicht oder niedriger ist, wird die Ausführung der `while`-Anweisung beendet.

## <a name="see-also"></a>Siehe auch

[while-Anweisung (C++)](../cpp/while-statement-cpp.md)
