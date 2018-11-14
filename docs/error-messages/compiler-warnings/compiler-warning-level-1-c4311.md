---
title: Compilerwarnung (Stufe 1) C4311
ms.date: 11/04/2016
f1_keywords:
- C4311
helpviewer_keywords:
- C4311
ms.assetid: ddc579d0-d051-47bc-915d-71ffb32323c9
ms.openlocfilehash: 5f9b8ce710879913fdad1be5c0f22f8e3f4ed9d7
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518163"
---
# <a name="compiler-warning-level-1-c4311"></a>Compilerwarnung (Stufe 1) C4311

'Variable': Zeigerverkürzung von 'Typ' zu 'Typ'

Diese Warnung erkennt Abschneidefehler bei 64-Bit-Zeigern. Wenn Code beispielsweise für eine 64-Bit-Architektur kompiliert wird, wird der Wert eines Zeigers (64 Bit) abgeschnitten, falls er einem `int` (32 Bit) zugewiesen wurde. Weitere Informationen finden Sie unter [Regeln für die Verwendung von Zeigern](/windows/desktop/WinProg64/rules-for-using-pointers).

Weitere Informationen zu den häufigsten Gründen von Warnung C4311 finden Sie unter [Häufige Compilerfehler](/windows/desktop/WinProg64/common-compiler-errors).

Im folgenden Codebeispiel wird C4311 beim Kompilieren für ein 64-Bit-Ziel generiert und dann veranschaulicht, wie Sie dieses Problem beheben können:

```
// C4311.cpp
// compile by using: cl /W1 C4311.cpp
int main() {
   void* p = &p;
   unsigned int i = (unsigned int) p;   // C4311 for 64-bit targets
   unsigned long long j = (unsigned long long) p;   // OK
}
```