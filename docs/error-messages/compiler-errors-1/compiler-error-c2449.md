---
title: Compilerfehler C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: f674bbec7cee8c00792848ee7e51b1e46299dd58
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302071"
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