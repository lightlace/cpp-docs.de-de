---
title: Compilerfehler C2449 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2449
dev_langs:
- C++
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e92638eaca1fe951d6b67da7563930214198926
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018768"
---
# <a name="compiler-error-c2449"></a>Compilerfehler C2449

gefunden. ' {' im Dateigültigkeitsbereich (fehlt der Funktionsheader?)

Eine öffnende geschweifte Klammer tritt im Dateigültigkeitsbereich.

Dieser Fehler kann durch ein Semikolon zwischen einem Funktionsheader und die öffnende geschweifte Klammer der Funktionsdefinition verursacht werden.

Im folgende Beispiel wird die C2499 generiert:

```
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```