---
title: Compilerfehler C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 4776ddede31dbcebe56a5919fd111f4df7248215
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182690"
---
# <a name="compiler-error-c2299"></a>Compilerfehler C2299

"Function": verhaltensänderung: eine explizite Spezialisierung kann kein Kopierkonstruktor oder kopierzuordnungsoperator sein.

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual C++ 2005 durchgeführt wurde, generiert werden: in früheren Versionen von Visual C++ zulässig explizite spezialisierungen für einen Kopierkonstruktor oder ein Kopierzuweisungsoperator verwendet.

Um C2299 beheben zu können, nehmen Sie keine der Kopierkonstruktor oder Zuweisungsoperator eine Vorlagenfunktion, aber stattdessen eine nicht-Template-Funktion, die ein Klassentyps verwendet. Jeder Code, der Kopierkonstruktor oder Zuweisungsoperator aufruft, indem Sie die Vorlagenargumente explizit angeben, muss die Vorlagenargumente zu entfernen.

Im folgende Beispiel wird die C2299 generiert:

```
// C2299.cpp
// compile with: /c
class C {
   template <class T>
   C (T t);

   template <> C (const C&);   // C2299
   C (const C&);   // OK
};
```