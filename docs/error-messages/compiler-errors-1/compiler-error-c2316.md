---
title: Compilerfehler C2316
ms.date: 07/08/2019
f1_keywords:
- C2316
helpviewer_keywords:
- C2316
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
ms.openlocfilehash: 5a3d9052775a5e1cbedfd58ccaaf0ff039a8475d
ms.sourcegitcommit: 07b34ca1c1fecced9fadc95de15dc5fee4f31e5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2019
ms.locfileid: "67693445"
---
# <a name="compiler-error-c2316"></a>Compilerfehler C2316

> "*Class_type*": kann nicht abgefangen werden, da Destruktor und/oder Kopierkonstruktor nicht zugegriffen werden kann oder gelöscht werden

Eine Ausnahme wurde abgefangen, gemäß Wert oder Verweis, sondern den Copy-Konstruktor, der Zuweisungsoperator, oder beide konnte nicht zugegriffen werden.

## <a name="remarks"></a>Hinweise

Übereinstimmung mit Standards in Visual Studio 2015 Änderungen dieser Fehler auf ungültige Catch-Anweisungen von abgeleiteten MFC-Ausnahmen anzuwenden `CException`. Da `CException` verfügt über eine geerbte privaten Kopierkonstruktor der Klasse und ihrer ableitungen werden nicht kopiert und können nicht anhand des Werts bedeutet auch, dass sie können nicht abgefangen werden, als Wert übergeben werden. Catch-Anweisungen, die MFC-Ausnahmen nach Wert, der zuvor führte zu einer nicht abgefangenen Ausnahmen zur Laufzeit abgefangen. Der Compiler wird nun ordnungsgemäß identifiziert diese Situation, und der Fehler C2316 gemeldet. Um dieses Problem zu beheben, empfehlen wir, Sie verwenden Sie die MFC-TRY/CATCH-Makros, anstatt Ihre eigenen Ausnahmehandler schreiben. Wenn dies nicht für Ihren Code geeignet ist, die fangen Sie MFC-Ausnahmen ab, stattdessen als Verweis.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C2316 generiert und zeigt, wie Sie diesen Fehler beheben:

```cpp
// C2316.cpp
// compile with: /EHsc
#include <stdio.h>

struct B
{
public:
    B() {}
    // Delete the following line to resolve.
private:
    // copy constructor
    B(const B&) {}
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
    catch (B b)    // C2316
    {
        printf_s("Caught an exception!\n");
    }
}
```
