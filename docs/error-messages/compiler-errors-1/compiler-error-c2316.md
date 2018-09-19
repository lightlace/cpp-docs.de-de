---
title: Compilerfehler C2316 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2316
dev_langs:
- C++
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2868d3a81fcbc94d8b20adcdc775363eb0a8eaeb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033016"
---
# <a name="compiler-error-c2316"></a>Compilerfehler C2316

> "*Ausnahme*": kann nicht abgefangen werden, da Destruktor und/oder Kopierkonstruktor nicht zugegriffen werden kann

Eine Ausnahme wurde durch einen Wert oder Verweis abgefangen, aber auf den copy-Konstruktor und/oder den Zuweisungsoperator konnte nicht zugegriffen werden.

Dieser Code wurde vom Versionen von Visual C++ vor Visual Studio 2003 akzeptiert, jetzt jedoch einen Fehler.

Übereinstimmung mit Standards in Visual Studio 2015 Änderungen dieser Fehler auf ungültige Catch-Anweisungen von abgeleiteten MFC-Ausnahmen anzuwenden `CException`. Da `CException` verfügt über eine geerbte privaten Kopierkonstruktor der Klasse und ihrer ableitungen nicht kopiert werden, und können nicht anhand des Werts bedeutet auch, dass sie können nicht abgefangen werden, als Wert übergeben werden. Catch-Anweisungen, die MFC-Ausnahmen nach Wert, der zuvor führte zu einer nicht abgefangenen Ausnahmen zur Laufzeit abgefangen, aber der Compiler jetzt ordnungsgemäß identifiziert, diese Situation und meldet Fehler C2316. Um dieses Problem zu beheben, empfehlen wir, dass Sie die MFC-TRY/CATCH-Makros verwenden, anstatt Ihre eigenen Ausnahmehandler schreiben, aber wenn dies nicht für Ihren Code geeignet ist, MFC-Ausnahmen durch Verweis stattdessen abfangen an.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2316 generiert:

```
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

extern "C" int printf_s(const char*, ...);

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&)
    {
    }
};

void f(const B&)
{
}

int main()
{
    try
    {
        B aB;
        f(aB);
    }
    catch (B b) {   // C2316
        printf_s("Caught an exception!\n");
    }
}
```