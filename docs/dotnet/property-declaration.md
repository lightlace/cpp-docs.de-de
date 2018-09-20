---
title: Eigenschaftendeklaration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 019b8eae17952bfe53fd8fbf14db4bafce1bf463
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438300"
---
# <a name="property-declaration"></a>Eigenschaftendeklaration

Die Möglichkeit zum Deklarieren einer Eigenschaft in einer verwalteten Klasse wurde von Managed Extensions für C++ in Visual C++ geändert.

In der Managed Extensions erstellen, von denen jede `set` oder `get` Eigenschaftenaccessor als unabhängige Methode angegeben ist. Die Deklaration der einzelnen Methoden wird mit dem Präfix die `__property` Schlüsselwort. Der Name der Methode beginnt entweder mit `set_` oder `get_` gefolgt von den tatsächlichen Namen der Eigenschaft (wie für den Benutzer sichtbar). Daher eine `Vector` Bereitstellen einer `x` koordinieren `get` Eigenschaft würde nennen Sie sie `get_x` und der Benutzer würde so aufrufen, als `x`. Diese Benennungskonvention und eine separate Spezifikation der Methoden gibt tatsächlich die zugrunde liegenden laufzeitimplementierung der Eigenschaft an. Hier ist z. B. unsere `Vector` mit einem Satz von Koordinaten Eigenschaften:

```
public __gc __sealed class Vector {
public:
   __property double get_x(){ return _x; }
   __property double get_y(){ return _y; }
   __property double get_z(){ return _z; }

   __property void set_x( double newx ){ _x = newx; }
   __property void set_y( double newy ){ _y = newy; }
   __property void set_z( double newz ){ _z = newz; }
};
```

Dies verteilt, die Funktionalität, die mit einer Eigenschaft und muss der Benutzer die zugeordneten Sets und ruft lexikalisch zu vereinheitlichen. Darüber hinaus ist es ausführlich. In der neuen Syntax, handelt es sich eher dem C# -Code, der `property` Schlüsselwort folgt durch den Typ der Eigenschaft und nicht erweiterten Namen. Die `set` und `get` -Zugriffsmethode werden innerhalb eines Blocks nach dem Eigenschaftennamen. Beachten Sie, dass im Gegensatz zu c#, die Signatur der Zugriffsmethode angegeben ist. Hier ist z. B. im obenstehenden Codebeispiel wird in der neuen Syntax übersetzt.

```
public ref class Vector sealed {
public:
   property double x {
      double get() {
         return _x;
      }

      void set( double newx ) {
         _x = newx;
      }
   } // Note: no semi-colon
};
```

Die Zugriffsmethoden der Eigenschaft unterschiedliche Zugriffsebenen - wieder, wie z. B. eine `public get` und `private` oder `protected set`, eine Bezeichnung explizit Zugriff kann angegeben werden. Standardmäßig gibt die Zugriffsebene der Eigenschaft, die von der einschließenden Zugriffsebene an. Z. B. in der obigen Definition von `Vector`sowohl die `get` und `set` Methoden sind `public`. Zu den `set` Methode `protected` oder `private`, würde die Definition wie folgt überarbeitet werden:

```
public ref class Vector sealed {
public:
   property double x {
      double get() {
         return _x;
      }

   private:
      void set( double newx ) {
         _x = newx;
      }

   } // note: extent of private culminates here

// note: dot is a public method of Vector
double dot( const Vector^ wv );

// etc.
};
```

Im Rahmen eines Zugriffsschlüsselworts auf innerhalb einer Eigenschaft erweitert, bis die schließende Klammer der Eigenschaft oder die Spezifikation eines Zugriffsschlüsselworts zusätzliche auf. Es geht nicht über die Definition der Eigenschaft, die die einschließende Zugriffsebene hinaus in dem die Eigenschaft definiert ist. In der oben genannten Deklaration, z. B. `Vector::dot()` ist eine öffentliche Methode.

Das Schreiben der festlegen/Abrufen von Eigenschaften für die drei `Vector` Koordinaten umfasst drei Schritte:

1. Deklarieren Sie einen privaten Status-Member des entsprechenden Typs.

1. Wenn der Benutzer wünscht, dass zum Abrufen des Werts zurückgeben.

1. Weisen sie den neuen Wert.

In der neuen Syntax ist steht eine Kurzsyntax für die Eigenschaft der dieses Nutzungsmuster automatisiert:

```
public ref class Vector sealed {
public:
   // equivalent shorthand property syntax
   property double x;
   property double y;
   property double z;
};
```

Die interessanten Nebeneffekt, dass die Kurzschreibweise der Syntax-Eigenschaft ist, dass obwohl der statusmember der backstage vom Compiler generiert wird, nicht innerhalb der Klasse nur über die Set/Get-Accessoren.

## <a name="see-also"></a>Siehe auch

[Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[Eigenschaft](../windows/property-cpp-component-extensions.md)