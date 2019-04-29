---
title: Compilerfehler C2017
ms.date: 11/04/2016
f1_keywords:
- C2017
helpviewer_keywords:
- C2017
ms.assetid: 1083eed9-9906-4a97-883c-54e52d7e82cd
ms.openlocfilehash: f4a17557e5e4ca1eb3f69561c964c9bbe24bb70d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303782"
---
# <a name="compiler-error-c2017"></a>Compilerfehler C2017

Ungültige Escapesequenz

Eine Escapesequenz, z. B. \t, angezeigt wird, außerhalb einer Zeichen- oder Konstanten.

Im folgende Beispiel wird die C2017 generiert:

```
// C2017.cpp
int main() {
   char test1='a'\n;   // C2017
   char test2='a\n';   // ok
}
```

C2017 kann auftreten, wenn der Stringize-Operator mit Zeichenfolgen verwendet wird, die Escapesequenzen enthalten.

Im folgende Beispiel wird die C2017 generiert:

```
// C2017b.cpp
#define TestDfn(x) AfxMessageBox(#x)
TestDfn(CString("\\") + CString(".h\"\n\n"));   // C2017
```