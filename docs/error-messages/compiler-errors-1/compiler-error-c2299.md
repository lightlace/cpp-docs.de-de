---
title: Compilerfehler C2299 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2299
dev_langs:
- C++
helpviewer_keywords:
- C2299
ms.assetid: d001c2bc-f6fd-47aa-8e42-0eb824d6441d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4977f4a5ac81cf4c04d3b143f6f7e670a9d9279
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46049617"
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