---
title: Ein Trackinghandle für einen geschachtelten Wert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxed value types, tracking handle to
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c7e26efae93b509700c3bb0c992d9f397559e99f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380727"
---
# <a name="a-tracking-handle-to-a-boxed-value"></a>Ein Trackinghandle für einen geschachtelten Wert

Die Verwendung von ein Trackinghandle für einen Werttyp-Verweis wurde von Managed Extensions für C++ in Visual C++ geändert.

Beim Boxing handelt es sich um eine Besonderheit des unified CLR-Typsystems. Werttypen direkt enthalten ihren Zustand, während ein implizites Paar um Verweistypen handelt: die benannte Entität ist ein Handle für ein unbenanntes Objekt, das auf dem verwalteten Heap zugeordnet. Eine Initialisierung oder Zuweisung eines Werts, geben Sie eine `Object`, z. B. erfordert, dass der Werttyp innerhalb der CLR-Heap - Dies ist, in dem das Bild des boxing, es tritt auf, - platziert werden zunächst durch Zuordnen des zugeordneten Speichers aus, und klicken Sie dann durch Kopieren der Werttyp des Zustands , und anschließend die Adresse dieser anonymen Wertverweis/hybride zurückgegeben werden. Also, wenn eine in C# -Code schreibt

```cpp
object o = 1024; // C# implicit boxing
```

Es passiert sehr viel mehr als deutlich von der Einfachheit des Codes vorgenommen wird. Das Design von C# -Code vereinfacht die nicht nur Vorgänge im Hintergrund ausgeführt werden, sondern auch die Abstraktion von boxing selbst. In Managed Extensions for C++ auf der anderen Seite besorgt, dass dies würde dazu führen, um ein falsches Gefühl der Effizienz, die in den Benutzer durch das Anfordern der expliziten Anweisung eingefügt:

```cpp
Object *o = __box( 1024 ); // Managed Extensions explicit boxing
```

Boxing ist implizit in Visual C++:

```cpp
Object ^o = 1024; // new syntax implicit boxing
```

Die `__box` -Schlüsselwort dient einen wichtigen Dienst innerhalb der Managed Extensions, die nicht vorhanden ist standardmäßig in Sprachen wie c# und Visual Basic: bietet sowohl ein Vokabular als auch zur direkten Bearbeitung von geschachtelten Instanzen auf dem verwalteten Heap behandeln. Betrachten Sie beispielsweise das folgende kleine Programm:

```cpp
int main() {
   double result = 3.14159;
   __box double * br = __box( result );

   result = 2.7;
   *br = 2.17;
   Object * o = br;

   Console::WriteLine( S"result :: {0}", result.ToString() ) ;
   Console::WriteLine( S"result :: {0}", __box(result) ) ;
   Console::WriteLine( S"result :: {0}", br );
}
```

Die zugrunde liegende Code für die drei Aufrufe der `WriteLine` anzeigen, die die verschiedenen Kosten für den Zugriff auf den Wert, der einen geschachtelten Wert Geben Sie (Dank Yves hier Dolce, hat diese Unterschiede), wenn den Aufwand in Zusammenhang mit den einzelnen von die angezeigten Zeilen angezeigt Aufruf.

```cpp
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;
ldstr      "result :: {0}"
ldloca.s   result  // ToString overhead
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead
call       void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", __box(result) ) ;
Ldstr    " result :: {0}"
ldloc.0
box    [mscorlib]System.Double // box overhead
call    void [mscorlib]System.Console::WriteLine(string, object)

// Console::WriteLine( S"result :: {0}", br );
ldstr    "result :: {0}"
ldloc.0
call     void [mscorlib]System.Console::WriteLine(string, object)
```

Übergeben direkt zu den geschachtelten Werttyp `Console::WriteLine` eliminiert sowohl das Boxing aufzurufende `ToString()`. (Es ist natürlich das frühere Boxing initialisiert `br`, sodass wir nichts gewinnen nicht, es sei denn, Sie legen wir wirklich `br` funktioniert.

In der neuen Syntax ist die Unterstützung für geschachtelte Werttypen wesentlich Eleganter und integrierte innerhalb des Typsystems und behalten Sie die Power an. Hier ist z. B. die Übersetzung von der früheren kleines Programm:

```cpp
int main()
{
   double result = 3.14159;
   double^ br = result;
   result = 2.7;
   *br = 2.17;
   Object^ o = br;
   Console::WriteLine( "result :: {0}", result.ToString() );
   Console::WriteLine( "result :: {0}", result );
   Console::WriteLine( "result :: {0}", br );
}
```

## <a name="see-also"></a>Siehe auch

[Werttypen und ihr Verhalten (C++/CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)<br/>
[Vorgehensweise: Explizites Anfordern von Boxing](../dotnet/how-to-explicitly-request-boxing.md)