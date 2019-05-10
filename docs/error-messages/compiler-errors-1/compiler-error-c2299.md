---
title: Compilerfehler C2299
ms.date: 11/04/2016
f1_keywords:
- C2299
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
ms.openlocfilehash: 39659baebf7dc1859a69021f60ed452964ae61af
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447961"
---
# <a name="compiler-error-c2299"></a>Compilerfehler C2299

"Function": verhaltensänderung: eine explizite Spezialisierung kann kein Kopierkonstruktor oder kopierzuordnungsoperator sein.

Dieser Fehler kann außerdem infolge einer konformitätsverbesserung für Compiler, die für Visual Studio 2005 durchgeführt wurde, generiert werden: frühere Versionen von Visual C++ explizite spezialisierungen für einen Kopierkonstruktor oder einen Kopierzuweisungsoperator zulässig.

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