---
title: Compilerfehler C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: bcc801bb5802598e936d577f08729214bb7e13a1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759788"
---
# <a name="compiler-error-c2768"></a>Compilerfehler C2768

"Function": Unzulässige Verwendung von expliziten Vorlagen Argumenten

Der Compiler konnte nicht feststellen, ob eine Funktionsdefinition eine explizite Spezialisierung einer Funktions Vorlage sein sollte oder ob die Funktionsdefinition für eine neue Funktion vorgesehen war.

Dieser Fehler wurde in Visual Studio .NET 2003 im Rahmen der Verbesserungen der Compilerkonformität eingeführt.

Im folgenden Beispiel wird C2768 generiert:

```cpp
// C2768.cpp
template<typename T>
void f(T) {}

void f<int>(int) {}   // C2768

// an explicit specialization
template<>
void f<int>(int) {}

// global nontemplate function overload
void f(int) {}
```
