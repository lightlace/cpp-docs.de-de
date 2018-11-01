---
title: Compilerfehler C2712
ms.date: 11/04/2016
f1_keywords:
- C2712
helpviewer_keywords:
- C2712
ms.assetid: f7d4ffcc-7ed2-459b-8067-a728ce647071
ms.openlocfilehash: 19b9c5a54bf405114bd4d596c2a2cc4708aadcc9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507912"
---
# <a name="compiler-error-c2712"></a>Compilerfehler C2712

> __try kann nicht in Funktionen verwendet werden, die eine Objektentladung benötigen

## <a name="remarks"></a>Hinweise

Fehler C2712 kann auftreten, bei Verwendung von [/EHsc](../../build/reference/eh-exception-handling-model.md), und eine Funktion mit strukturierter Ausnahmebehandlung auch Objekte besitzt, die Entladung (Zerstörung) benötigen.

Folgende Lösungen sind möglich:

- Verschieben Sie Code, der SEH benötigt, zu einer anderen Funktion.

- Schreiben Sie Funktionen, die SEH verwenden, neu, um die Verwendung von lokalen Variablen und Parameter, die über Destruktoren verfügen, zu vermeiden. Verwenden Sie SEH nicht in Konstruktoren oder Destruktoren

- Kompilieren ohne /EHsc

Fehler C2712 kann auch auftreten, wenn Sie eine Methode deklariert, indem Aufrufen der [__event](../../cpp/event.md) Schlüsselwort. Da das Ereignis in einer Multithreadumgebung verwendet werden kann, generiert der Compiler Code, der Bearbeitung des zugrunde liegenden Ereignisobjekts verhindert und schließt dann den generierten Code in eine SEH- [Try-finally-Anweisung](../../cpp/try-finally-statement.md). Folglich wird Fehler C2712 auftreten, wenn Sie die Ereignismethode aufrufen und ein Argument, dessen Typ einen Destruktor enthält, als Wert übergeben. Eine Lösung besteht in diesem Fall darin, das Argument als konstanten Verweis zu übergeben.

C2712 kann auch auftreten, wenn Sie mit der Kompilierung **/CLR: pure** und deklarieren Sie einen statischen Array von Zeigern auf Funktionen in einer `__try` Block. Ein statischer Member benötigt den Compiler an die dynamische Initialisierung unter **/CLR: pure**, wodurch eine C++-Ausnahmebehandlung impliziert. Eine C++-Ausnahmebehandlung ist jedoch in einem `__try`-Block nicht zulässig.

Die **/CLR: pure** und **/CLR: safe** Compileroptionen in Visual Studio 2015 als veraltet markiert und in Visual Studio 2017 nicht unterstützt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2712 generiert und gezeigt, wie Sie diesen Fehler beheben:

```cpp
// C2712.cpp
// compile with: /clr:pure /c
struct S1 {
   static int smf();
   void fnc();
};

void S1::fnc() {
   __try {
      static int (*array_1[])() = {smf,};   // C2712

      // OK
      static int (*array_2[2])();
      array_2[0] = smf;
    }
    __except(0) {}
}
```