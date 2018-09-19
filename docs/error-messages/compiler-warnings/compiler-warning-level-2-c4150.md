---
title: Compilerwarnung (Stufe 2) C4150 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4150
dev_langs:
- C++
helpviewer_keywords:
- C4150
ms.assetid: ff1760ec-0d9f-4d45-b797-94261624becf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d317384d3708679d485ae0a77c6ee9b6622b9c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050423"
---
# <a name="compiler-warning-level-2-c4150"></a>Compilerwarnung (Stufe 2) C4150

Löschen eines Zeigers an unvollständigen Typ 'Typ'. keinen Destruktor namens

Die **löschen** Operator wird aufgerufen, um ein Typ, der deklariert wurde, aber nicht definiert ist, löschen, damit der Compiler keinen Destruktor nicht finden konnte.

Im folgende Beispiel wird die C4150 generiert:

```
// C4150.cpp
// compile with: /W2
class  IncClass;

void NoDestruct( IncClass* pIncClass )
{
   delete pIncClass;
} // C4150, define class to resolve

int main()
{
}
```