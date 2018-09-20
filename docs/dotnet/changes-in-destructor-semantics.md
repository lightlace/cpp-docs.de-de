---
title: Änderungen in der Destruktorsemantik | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- finalizers [C++]
- destructors, C++
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c25045291afed1e8072867ee668716b2f396ef30
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46420022"
---
# <a name="changes-in-destructor-semantics"></a>Änderungen in der Destruktorsemantik

Semantik für Klassendestruktoren haben deutlich von Managed Extensions for C++ auf Visual C++ geändert.

In Managed Extensions wurde dem Klassendestruktoren innerhalb einer Reference-Klasse, aber nicht innerhalb einer Wertklasse zugelassen. Dies wurde in der neuen Syntax nicht geändert. Es wurden jedoch die Semantik der Destruktor einer Klasse geändert. Dieses Thema konzentriert sich auf die Gründe, ändern und erläutert, wie sie die Übersetzung von vorhandenen CLR-Code auswirkt. Es ist wahrscheinlich die wichtigste auf Programmiererebene Änderung zwischen den beiden Versionen der Sprache.

## <a name="non-deterministic-finalization"></a>Nicht deterministische Beendigung

Bevor ein Objekt zugeordnete Arbeitsspeicher wieder, durch den Garbage Collector, ein zugeordnetes freigegeben wird `Finalize` -Methode, sofern vorhanden, aufgerufen wird. Sie können diese Methode als eine Art Superdestruktor vor vorstellen, da es nicht an die Nutzungsdauer eines Objekts gebunden wird. Wir bezeichnen dies als Beendigung. Die zeitplanung für nur wenn oder sogar, ob eine `Finalize` Methode wird aufgerufen, ist nicht definiert. Dies ist, was wir meinen, wenn wir sagen, dass die automatische speicherbereinigung nicht deterministische Beendigung darstellt.

Nicht deterministische Beendigung funktioniert gut mit der Verwaltung des dynamischen Arbeitsspeichers. Wenn der Speicherplatz knapp wird, wird der Garbage Collector. In Collection einer Garbage-Umgebung werden keine Destruktoren zur Freigabe von Arbeitsspeicher benötigt. Nicht deterministische Beendigung funktioniert nicht, allerdings, wenn ein Objekt eine wichtige Ressource, z. B. eine datenbankverbindung oder eine Art von Sperre beibehält. In diesem Fall sollten wir diese Ressource so bald wie möglich freigeben. In der systemeigenen Welt, die mit einem Konstruktor/Destruktor Paar erreicht wird. Als die Lebensdauer des Objekts beendet wird, wenn beendet der lokale Block, in dem sie deklariert ist, oder, wenn der Stapel aufgrund einer ausgelösten Ausnahme kommt der Destruktor ausgeführt wird und die Ressource wird automatisch freigegeben. Dieser Ansatz funktioniert sehr gut, und wurde in Managed Extensions noch schmerzlich vermisst.

Von der CLR-Lösung ist für eine Klasse zum Implementieren der `Dispose` Methode der `IDisposable` Schnittstelle. Das Problem hier besteht, die `Dispose` erfordert einen expliziten Aufruf durch den Benutzer. Dies ist fehleranfällig. Die Programmiersprache c# bietet eine bescheidene Form der Automatisierung in Form eines speziellen `using` Anweisung. Der Managed Extensions-Entwurf bereitgestellt keine besondere Unterstützung.

## <a name="destructors-in-managed-extensions-for-c"></a>Destruktoren in Managed Extensions für C++

In Managed Extensions wird der Destruktor eine Reference-Klasse implementiert, mithilfe der folgenden beiden Schritte aus:

1. Der benutzerdefinierte Destruktor wird intern auf umbenannt `Finalize`. Wenn die Klasse eine Basisklasse hat (Beachten Sie, dass in der CLR-Objektmodell wird nur die einfache Vererbung unterstützt wird), fügt der Compiler einen Aufruf der Finalizer, der nach Ausführung des benutzerdefinierten Codes. Betrachten Sie beispielsweise die folgende einfache Hierarchie der Managed Extensions-Sprachspezifikation entnommen:

```
__gc class A {
public:
   ~A() { Console::WriteLine(S"in ~A"); }
};

__gc class B : public A {
public:
   ~B() { Console::WriteLine(S"in ~B");  }
};
```

In diesem Beispiel werden beide Destruktoren umbenannt `Finalize`. `B`die `Finalize` wird ein Aufruf der `A`des `Finalize` Methode hinzugefügt, die den Aufruf von folgt `WriteLine`. Dies ist, was standardmäßig während des Abschlusses der Garbage Collector aufgerufen wird. Hier ist, wie interne Transformation aussehen könnte:

```
// internal transformation of destructor under Managed Extensions
__gc class A {
public:
   void Finalize() { Console::WriteLine(S"in ~A"); }
};

__gc class B : public A {
public:
   void Finalize() {
      Console::WriteLine(S"in ~B");
      A::Finalize();
   }
};
```

1. Im zweiten Schritt erzeugt der Compiler einen virtuellen Destruktor. Dieser Destruktor ist unsere Managed Extensions Benutzerprogramme entweder direkt oder über eine Anwendung die Delete-Ausdruck aufrufen. Er wird vom Garbage Collector nie aufgerufen.

     Zwei Anweisungen werden in diese synthetisierten Destruktoren platziert. Eine ist ein Aufruf `GC::SuppressFinalize` um sicherzustellen, dass es keine weiteren Aufrufe von sind `Finalize`. Die zweite ist, den eigentlichen Aufruf von `Finalize`, der den benutzerdefinierten Destruktor für diese Klasse darstellt. Hier ist, wie dies aussehen könnte:

```
__gc class A {
public:
   virtual ~A() {
      System::GC::SuppressFinalize(this);
      A::Finalize();
   }
};

__gc class B : public A {
public:
   virtual ~B() {
      System::GC::SuppressFinalize(this);
      B::Finalize();
   }
};
```

Kann von dieser Implementierung die Benutzer die Klasse explizit aufrufen, um `Finalize` Methode jetzt statt zu einem Zeitpunkt an, Sie keine Kontrolle über haben, es ist nicht wirklich Verknüpfen mit der `Dispose` Methode Lösung. Dies wird in Visual C++ geändert.

## <a name="destructors-in-new-syntax"></a>Destruktoren in der neuen Syntax

In der neuen Syntax wird der Destruktor wird umbenannt intern auf den `Dispose` -Methode und die Verweisklasse wird automatisch so erweitert, implementieren die `IDispose` Schnittstelle. Unter Visual C++ wird Klassenpaar, also wie folgt transformiert:

```
// internal transformation of destructor under the new syntax
__gc class A : IDisposable {
public:
   void Dispose() {
      System::GC::SuppressFinalize(this);
      Console::WriteLine( "in ~A");
   }
};

__gc class B : public A {
public:
   void Dispose() {
      System::GC::SuppressFinalize(this);
      Console::WriteLine( "in ~B");
      A::Dispose();
   }
};
```

Wenn ein Destruktor explizit aufgerufen wird, in der neuen Syntax oder `delete` angewendet wird, ein Trackinghandle, der die zugrunde liegende `Dispose` -Methode wird aufgerufen. Ist dies ein Aufruf von einer abgeleiteten Klasse die `Dispose` Methode der Basisklasse am Ende der künstlichen Methode eingefügt wird.

Aber dies erhält keine uns ganz nach deterministische Beendigung. Damit gelangen, benötigen wir die zusätzliche Unterstützung von lokalen Verweis-Objekte. (Dies hat keine analoge Unterstützung in Managed Extensions und ist keiner Übersetzungsproblem.)

## <a name="declaring-a-reference-object"></a>Deklarieren Sie ein Verweisobjekt

Visual C++ unterstützt die Deklaration eines Objekts einer Verweisklasse auf dem lokalen Stack oder als Member einer Klasse ab, als wäre er direkt zugegriffen werden kann. In Kombination mit der Zuordnung des Destruktors mit der `Dispose` -Methode, das Ergebnis ist der automatische Aufruf der Finalization-Semantik für Referenztypen.

Zuerst definieren wir unsere Reference-Klasse, Erstellung von Objekten als dem Erwerb einer Ressource über den Klassenkonstruktor dient. Als Nächstes veröffentlichen wir innerhalb der Destruktor einer Klasse, die Ressource abgerufen, wenn das Objekt erstellt wurde.

```
public ref class R {
public:
   R() { /* acquire expensive resource */ }
   ~R() { /* release expensive resource */ }

   // everything else...
};
```

Das Objekt ist lokal mithilfe der Typname, jedoch ohne die zugehörigen Hat deklariert. Alle Verwendungen des Objekts, z. B. das Aufrufen einer Methode, werden stets der Punktoperator für die Memberauswahl (`.`) anstelle von Pfeil (`->`). Am Ende des Blocks, der zugehörige Destruktor in transformiert `Dispose`, automatisch aufgerufen, wie hier gezeigt:

```
void f() {
   R r;
   r.methodCall();

   // r is automatically destructed here -
   // that is, r.Dispose() is invoked
}
```

Wie bei der `using` Anweisung in c# ist dies nicht die zugrunde liegenden CLR-Einschränkung, dass alle Referenztypen trotzen muss auf dem CLR-Heap zugeordnet werden. Die zugrunde liegende Semantik bleiben unverändert. Ebenso hätte des Benutzers Folgendes schreiben kann (und dies ist wahrscheinlich die interne, vom Compiler durchgeführten Transformation):

```
// equivalent implementation
// except that it should be in a try/finally clause
void f() {
   R^ r = gcnew R;
   r->methodCall();

   delete r;
}
```

Aktiviert ist, unter der neuen Syntax Destruktoren werden wieder mit Konstruktoren gepaart eine automatisierte Abrufs oder der Freigabe Mechanismus, der an ein lokales Objekt Lebensdauer gebunden.

## <a name="declaring-an-explicit-finalize"></a>Deklarieren einen expliziten Finalize-Methode

In der neuen Syntax, wie wir gesehen haben, der Destruktor ist synthetisiert in die `Dispose` Methode. Dies bedeutet, dass wenn der Destruktor nicht explizit aufgerufen wird, den Garbage Collector des während des Abschlusses nicht wie zuvor eine zugeordnete findet `Finalize` Methode für das Objekt. Um Zerstörung und die Beendigung zu unterstützen, haben wir eine spezielle Syntax für die Bereitstellung von eines Finalizers eingeführt. Zum Beispiel:

```
public ref class R {
public:
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }
};
```

Die `!` Präfix ist analog zu Tilde (`~`) dem Klassendestruktoren eingeführt – d. h. beide Methoden über ein Token, die den Namen der Klasse mit einem Präfix verfügen. Wenn die synthetischen `Finalize` Methode tritt auf, in einer abgeleiteten Klasse einen Aufruf der Basisklasse `Finalize` Methode am Ende eingefügt wird. Wenn der Destruktor explizit aufgerufen wird, wird der Finalizer unterdrückt. Sieht aus wie die Transformation aussehen könnte:

```
// internal transformation under new syntax
public ref class R {
public:
   void Finalize() {
      Console::WriteLine( "I am the R::finalizer()!" );
   }
};
```

## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Migration von Managed Extensions for C++ zu Visual C++ 2010

Wenn sie unter Visual C++ kompiliert wird, wenn eine Verweisklasse einen nicht trivialen Destruktor enthält, wird das Laufzeitverhalten einer Managed Extensions for C++-Programm geändert. Der Algorithmus für die erforderliche Übersetzung ist ähnlich der folgenden:

1. Wenn ein Destruktor vorhanden ist, neu schreiben Sie, um Klassenfinalizer aus.

1. Wenn eine `Dispose` Methode vorhanden ist, Schreiben Sie diese in der Destruktor einer Klasse.

1. Wenn ein Destruktor vorhanden ist, aber es gibt keine `Dispose` -Methode, behalten Sie den Destruktor beim Ausführen des ersten Elements.

Verschieben Sie Ihren Code in die neue Syntax von Managed Extensions, können Sie verpassen Sie dieser Transformation wird ausgeführt. Wenn die Anwendung auf irgendeine Weise bei der Ausführung der zugehörigen abhängt, variiert das Verhalten der Anwendung im Hintergrund von der gewünschten.

## <a name="see-also"></a>Siehe auch

[Verwaltete Typen (C++ / CL)](../dotnet/managed-types-cpp-cl.md)<br/>
[Destruktoren und Finalizer in der Vorgehensweise: definieren und Verarbeiten von Klassen und Strukturen (C++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)