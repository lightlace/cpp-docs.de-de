---
title: Compilerfehler C2449
ms.date: 11/04/2016
f1_keywords:
- C2449
helpviewer_keywords:
- C2449
ms.assetid: 544bf0b6-daa0-40e8-9f21-8e583d472a2d
ms.openlocfilehash: 6fd62813fdf3b50c0e329fc423e100d55a36ae12
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75299022"
---
# <a name="compiler-error-c2449"></a>Compilerfehler C2449

"{" im Datei Gültigkeitsbereich gefunden (fehlender Funktions Header?)

Eine öffnende geschweifter Klammer tritt im Datei Gültigkeitsbereich auf.

Dieser Fehler kann durch ein Semikolon zwischen einem Funktions Header und der öffnenden geschweiften Klammer der Funktionsdefinition verursacht werden.

Im folgenden Beispiel wird C2499 generiert:

```c
// C2449.c
// compile with: /c
void __stdcall func(void) {}   // OK
void __stdcall func(void);  // extra semicolon on this line
{                         // C2449 detected here
```
