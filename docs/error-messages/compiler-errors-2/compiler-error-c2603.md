---
title: Compilerfehler C2603
ms.date: 11/04/2016
f1_keywords:
- C2603
helpviewer_keywords:
- C2603
ms.assetid: 9ca520d0-f082-4b65-933d-17c3bcf8b02c
ms.openlocfilehash: 5391aed09b7fd448a9d72ea7cc17cd5c26fc5f04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215400"
---
# <a name="compiler-error-c2603"></a>Compilerfehler C2603

> "*Funktion*": Zu viele statische Objekte im Blockbereich mit Konstruktoren/Destruktoren in-Funktion

In Versionen von Visual C++-Compiler vor Visual Studio 2015 oder wenn die [/Zc:threadSafeInit-](../../build/reference/zc-threadsafeinit-thread-safe-local-static-initialization.md) -Compileroption angegeben ist, besteht eine Beschränkung auf die Anzahl von statischen Objekten in einer extern sichtbaren Inlinefunktion man kann 31 .

Um dieses Problem zu beheben, empfehlen wir Sie neuere Version von Visual C++-Compiler-Toolsets zu übernehmen, oder entfernen Sie wenn möglich die /Zc:threadSafeInit--Compileroption. Wenn dies nicht möglich ist, sollten Sie die statische Objekte kombinieren. Wenn die Objekte vom gleichen Typ sind, sollten Sie die Verwendung von einer einzelnen statischen Array dieses Typs, und verweisen auf einzelne Elemente nach Bedarf.

## <a name="example"></a>Beispiel

Der folgende Code generiert C2603 und zeigt eine Möglichkeit, das Problem zu beheben:

```cpp
// C2603.cpp
// Compile by using: cl /W4 /c /Zc:threadSafeInit- C2603.cpp
struct C { C() {} };
extern inline void f1() {
    static C C01, C02, C03, C04, C05, C06, C07, C08, C09, C10;
    static C C11, C12, C13, C14, C15, C16, C17, C18, C19, C20;
    static C C21, C22, C23, C24, C25, C26, C27, C28, C29, C30, C31;
    static C C32;   // C2603 Comment this line out to avoid error
}
```
