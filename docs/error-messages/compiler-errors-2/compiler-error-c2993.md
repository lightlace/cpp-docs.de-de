---
title: Compilerfehler C2993 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2993
dev_langs:
- C++
helpviewer_keywords:
- C2993
ms.assetid: 4ffd2b78-654b-46aa-95a6-b62101cf91c8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09b3c789cc15d2e146f1c5031003fc74d783e827
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081938"
---
# <a name="compiler-error-c2993"></a>Compilerfehler C2993

'Bezeichner': Unzulässiger Typ für den Nichttyp-Vorlagenparameter 'Parameter'

Sie können eine Vorlage mit einer Struktur oder union-Argument nicht deklarieren. Verwenden von Zeigern auf Strukturen und Unions als Vorlagenparameter übergeben.

Im folgende Beispiel wird die C2993 generiert:

```
// C2993.cpp
// compile with: /c
// C2993 expected
struct MyStruct {
   int a;char b;
};

template <class T, struct MyStruct S>   // C2993

// try the following line instead
// template <class T, struct MyStruct * S>
class CMyClass {};
```

Dieser Fehler wird außerdem infolge einer konformitätsverbesserung für Compiler, die in Visual Studio .NET 2003 durchgeführt wurde generiert werden: Gleitkommawert Nichttyp-Vorlagenparameter nicht mehr zulässig. Der C++-Standard lässt keine Gleitkommawerte Nichttyp Vorlagenparameter zu.

Wenn es sich um eine Funktionsvorlage ist, verweisen verwenden ein Funktionsargument der Gleitkommazahl übergeben Nichttyp-Vorlagenparameter (dieser Code wird in der Visual Studio .NET 2003 und Visual Studio .NET Versionen von Visual C++ gültig sein). Wenn es sich um eine Klassenvorlage ist, ist gibt es keine einfache Lösung.

```
// C2993b.cpp
// compile with: /c
template<class T, float f> void func(T) {}   // C2993

// OK
template<class T>   void func2(T, float) {}
```