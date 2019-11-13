---
title: Compilerwarnung (Stufe 3) C4018
ms.date: 11/04/2016
f1_keywords:
- C4018
helpviewer_keywords:
- C4018
ms.assetid: 6e8cbb04-d914-4319-b431-cbc2fbe40eb1
ms.openlocfilehash: e136a82f8a0ecb3f5375d3a486dd017df7edb6e0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051981"
---
# <a name="compiler-warning-level-3-c4018"></a>Compilerwarnung (Stufe 3) C4018

' Ausdruck ': nicht übereinstimmende/nicht signierte Übereinstimmung

Beim Vergleichen einer Zahl mit Vorzeichen und Vorzeichen muss der Compiler den signierten Wert in einen Ganzzahl ohne Vorzeichen-Wert konvertieren.

Diese Warnung wird möglicherweise korrigiert, wenn Sie einen der beiden Typen beim Testen von signierten und nicht signierten Typen umwandeln.

Im folgenden Beispiel wird C4018 generiert:

```cpp
// C4018.cpp
// compile with: /W3
int main() {
   unsigned int uc = 0;
   int c = 0;
   unsigned int c2 = 0;

   if (uc < c) uc = 0;   // C4018

   // OK
   if (uc == c2) uc = 0;
}
```