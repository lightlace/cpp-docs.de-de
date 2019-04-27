---
title: Zugreifen auf C- oder C++-Daten in __asm-Blöcken
ms.date: 08/30/2018
helpviewer_keywords:
- data members [C++], in __asm blocks
- data access [C++], in __asm blocks
- __asm keyword [C++], data members
- structure types in __asm blocks
ms.assetid: e99f5a28-0381-4090-8ece-6af8f2436a49
ms.openlocfilehash: 1f56cc5c049c1501ea09c76f31be3ab9dea5ed10
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167607"
---
# <a name="accessing-c-or-c-data-in-asm-blocks"></a>Zugreifen auf C- oder C++-Daten in __asm-Blöcken

**Microsoft-spezifisch**

Ein praktisches Feature der Inlineassembly ist die Möglichkeit, die auf C- oder C++-Variablen anhand des Namens verweisen. Ein `__asm` Block verweisen auf die Symbole, einschließlich der Variablennamen, die im Gültigkeitsbereich befinden, in der Block angezeigt wird. Z. B. wenn die C-Variable `var` befindet sich im Bereich, der die Anweisung

```cpp
__asm mov eax, var
```

Speichert den Wert des `var` im "eax".

Wenn eine Klasse, Struktur oder union-Member einen eindeutigen Namen hat, eine `__asm` Block kann mit nur den Membernamen, ohne die Variable verweisen oder `typedef` Namen vor dem Punkt (**.**) Operator. Wenn Sie der Namen des Members nicht eindeutig ist, jedoch muss man eine Variable oder `typedef` Name unmittelbar vor dem Punkt-Operator. Z. B. die Strukturtypen in der folgenden Beispiel-Freigabe `same_name` als ihren Membernamen:.

Wenn Sie Variablen mit den Typen deklarieren

```cpp
struct first_type hal;
struct second_type oat;
```

alle Verweise auf das Element `same_name` müssen den Namen den Variablen verwenden, da `same_name` ist nicht eindeutig. Aber das Element `weasel` einen eindeutigen Namen hat, sodass Sie nur die Elementnamen mit verweisen können:

```cpp
// InlineAssembler_Accessing_C_asm_Blocks.cpp
// processor: x86
#include <stdio.h>
struct first_type
{
   char *weasel;
   int same_name;
};

struct second_type
{
   int wonton;
   long same_name;
};

int main()
{
   struct first_type hal;
   struct second_type oat;

   __asm
   {
      lea ebx, hal
      mov ecx, [ebx]hal.same_name ; Must use 'hal'
      mov esi, [ebx].weasel       ; Can omit 'hal'
   }
   return 0;
}
```

Beachten Sie, dass das Auslassen der Variablenname einfach Schreiben von Code aus Gründen der benutzerfreundlichkeit. Die gleiche Assemblyanweisungen generiert werden, und zwar unabhängig davon, ob der Variable Name vorhanden ist.

Sie können Datenelemente in C++ ohne Berücksichtigung der zugriffseinschränkungen zugreifen. Sie können keine Member jedoch Funktionen aufrufen.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Verwenden von C oder C++ in __asm-Blöcken](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>