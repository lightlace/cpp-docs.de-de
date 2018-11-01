---
title: Compilerfehler C2912
ms.date: 11/04/2016
f1_keywords:
- C2912
helpviewer_keywords:
- C2912
ms.assetid: bd55cecd-ab1a-4636-ab8a-a00393fe7b3d
ms.openlocfilehash: b7f87ae2df5350fcfb2b7a662f517d8d7bd51ef8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540074"
---
# <a name="compiler-error-c2912"></a>Compilerfehler C2912

Explizite Spezialisierung 'declaration' ist keine Spezialisierung einer Funktionsvorlage

Nur Vorlagenfunktionen können spezialisiert werden.

Im folgenden Beispiel wird C2912 generiert:

```
// C2912.cpp
// compile with: /c
void f(char);
template<> void f(char);   // C2912
template<class T> void f(T);   // OK
```

Dieser Fehler wird außerdem infolge einer Konformitätsverbesserung für Compiler generiert, die in Visual Studio .NET 2003 durchgeführt wurde: Für jede explizite Spezialisierung müssen Sie die Parameter der expliziten Spezialisierung so wählen, dass sie mit den Parametern der primären Vorlage übereinstimmen.

```
// C2912b.cpp
class CF {
public:
   template <class A> CF(const A& a) {}   // primary template

   // attempted explicit specialization
   template <> CF(const char* p) {}   // C2912

   // try the following line instead
   // template <> CF(const char& p) {}
};
```