---
title: Compilerfehler C2768
ms.date: 11/04/2016
f1_keywords:
- C2768
helpviewer_keywords:
- C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
ms.openlocfilehash: 9c0fb8fb0a98830aaf061ba980e7bdd7903f25e1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50626173"
---
# <a name="compiler-error-c2768"></a>Compilerfehler C2768

'Funktion': Unzulässige Verwendung von expliziten Vorlagenargumenten

Der Compiler konnte nicht bestimmen, ob eine Funktionsdefinition eigentlich eine explizite Spezialisierung einer Funktionsvorlage sein, oder wenn die Funktionsdefinition wurde für eine neue Funktion sein.

Dieser Fehler wurde in Visual Studio .NET 2003 sind als Teil der Übereinstimmung mit Standards Verbesserungen des Compilers eingeführt.

Im folgende Beispiel wird die C2768 generiert:

```
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