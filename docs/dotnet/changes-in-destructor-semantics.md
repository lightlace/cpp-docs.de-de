---
title: Änderungen in der Destruktorsemantik | Microsoft Docs
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
ms.openlocfilehash: 8a3d078300ca0e51ba8eb035d5428d300b0413a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33113199"
---
# <a name="changes-in-destructor-semantics"></a>Änderungen in der Destruktorsemantik
Semantik für Klassendestruktoren haben deutlich von Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions wurde ein Destruktor der Klasse innerhalb einer Verweisklasse aber nicht innerhalb einer Wertklasse zulässig. Dies wurde nicht in der neuen Syntax geändert. Die Semantik der Klassendestruktor wurden jedoch geändert. Dieses Thema konzentriert sich auf die Gründe, ändern und erläutert, wie sie die Übersetzung von vorhandenen CLR-Code auswirkt. Es ist wahrscheinlich die wichtigste auf Programmiererebene Änderung zwischen den beiden Versionen der Sprache.  
  
## <a name="non-deterministic-finalization"></a>Nicht deterministischen  
 Bevor ein Objekt zugeordnete Arbeitsspeicher, durch den Garbage Collector eine zugeordnete freigegeben wird `Finalize` -Methode, falls vorhanden, wird aufgerufen. Sie können diese Methode als eine Art Super-Destruktor vorstellen, da es nicht von der Anwendung Lebensdauer des Objekts gebunden ist. Auf diese werden als Abschluss verweisen. Die zeitliche Abfolge der nur wenn oder auch, ob eine `Finalize` Methode wird aufgerufen, ist nicht definiert. Dies ist, was bedeutet, es wird argumentiert, dass die Garbagecollection nicht deterministischen weist.  
  
 Nicht deterministischen funktioniert gut mit der Verwaltung des dynamischen Arbeitsspeichers. Wenn der Speicherplatz knapp wird, zum Einsatz kommt der Garbage Collector. In Collection einer Garbage-Umgebung werden keine Destruktoren auf freien Arbeitsspeicher benötigt. Nicht deterministischen funktioniert, jedoch nicht, wenn ein Objekt eine wichtige Ressource, z. B. eine datenbankverbindung oder eine Sperre irgendeine verwaltet. In diesem Fall sollten wir diese Ressource so bald wie möglich freizugeben. In der systemeigenen-Welt, die mit einem Konstruktor/Destruktor Schlüsselpaar erreicht wird. Als die Lebensdauer des Objekts beendet wird, wenn der lokale Block, in dem sie deklariert wurde, beendet oder der Stapel aufgrund einer Ausnahme kommt der Destruktor ausgeführt wird und die Ressource wird automatisch freigegeben. Dieser Ansatz eignet sich sehr gut, und seine Abwesenheit in Managed Extensions wurde vermissen.  
  
 Von der CLR bereitgestellte Lösung ist für eine Klasse zum Implementieren der `Dispose` Methode der `IDisposable` Schnittstelle. Hier ist das Problem, das `Dispose` einen expliziten Aufruf durch den Benutzer erfordert. Dies ist fehleranfällig. Die C#-Sprache stellt eine bequeme Form der Automatisierung in Form eines speziellen `using` Anweisung. Der Managed Extensions-Entwurf bereitgestellt keine spezielle Unterstützung.  
  
## <a name="destructors-in-managed-extensions-for-c"></a>Destruktoren in Managed Extensions for C++  
 In Managed Extensions wird der Destruktor einer Verweisklasse implementiert, mithilfe der folgenden zwei Schritte:  
  
1.  Der Benutzer bereitgestellte Destruktor wird intern auf umbenannt `Finalize`. Wenn die Klasse eine Basisklasse verfügt (Beachten Sie, dass unter dem CLR-Objektmodell wird nur die einfache Vererbung unterstützt wird), fügt der Compiler einen Aufruf des Finalizers nach Ausführung des Codes Benutzer angegeben. Betrachten Sie beispielsweise die folgende einfache Hierarchie der Managed Extensions-Sprachspezifikation entnommen:  
  
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
  
 In diesem Beispiel werden beide Destruktoren umbenannt `Finalize`. `B`der `Finalize` wird ein Aufruf der `A`des `Finalize` Methode hinzugefügt, die nach dem Aufruf von `WriteLine`. Dies ist, was standardmäßig während des Abschlusses der Garbage Collector aufgerufen wird. Hier ist die interne Transformation könnte folgendermaßen aussehen:  
  
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
  
1.  Im zweiten Schritt synthetisiert der Compiler einen virtuellen Destruktor. Dieser Destruktor ist unsere Benutzer-Programmen von Managed Extensions entweder direkt oder über eine Anwendung die Löschausdruck aufgerufen. Er wird nie vom Garbage Collector aufgerufen.  
  
     Zwei Anweisungen sind in dieser gebildeter Destruktor platziert. Ist ein Aufruf von `GC::SuppressFinalize` um sicherzustellen, dass es keine weiteren Aufrufe von sind `Finalize`. Das zweite ist, den eigentlichen Aufruf von `Finalize`, die den Benutzer bereitgestellten Destruktor für diese Klasse darstellt. Hier ist dies könnte folgendermaßen aussehen:  
  
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
  
 Diese Implementierung kann der Benutzer die Klasse explizit aufrufen, um `Finalize` Methode jetzt statt zu einem Zeitpunkt, Sie keine Kontrolle über haben, es ist nicht wirklich tie mit der `Dispose` Methode Lösung. Dies ist in Visual C++ geändert.  
  
## <a name="destructors-in-new-syntax"></a>Destruktoren in der neuen Syntax  
 In der neuen Syntax wird der Destruktor intern auf umbenannt der `Dispose` -Methode und die Reference-Klasse wird automatisch erweitert, und Implementieren der `IDispose` Schnittstelle. Unter "Visual C++", d. h. wird Klassenpaar wie folgt transformiert:  
  
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
  
 Wenn entweder ein Destruktor explizit in der neuen Syntax aufgerufen wird, oder wenn `delete` wird angewendet, um ein Trackinghandle des zugrunde liegenden `Dispose` -Methode wird aufgerufen. Ist eine abgeleitete Klasse, die einen Aufruf von der `Dispose` -Methode der Basisklasse zum Abschluss der künstlichen Methode eingefügt wird.  
  
 Aber dies ist uns nicht abrufen, bis hin zur deterministischer Abschluss. Für die Durchführung erreicht, benötigen wir die zusätzliche Unterstützung von lokalen Verweis-Objekten. (Dies hat keine analoge Unterstützung in Managed Extensions und ist keine Übersetzungsproblem.)  
  
## <a name="declaring-a-reference-object"></a>Deklarieren Sie einen Verweis-Objekt  
 Visual C++ unterstützt die Deklaration eines Objekts einer Verweisklasse auf dem lokalen Stapel oder als Member einer Klasse ab, als wäre er direkt zugegriffen werden kann. In Kombination mit der Zuordnung des Destruktors mit der `Dispose` -Methode, das Ergebnis ist die automatische Aufruf der Finalisierungssemantik für Verweistypen.  
  
 Zuerst definieren wir unsere Reference-Klasse so, dass, Erstellen von Objekten als Erwerb einer Ressource über den Klassenkonstruktor Funktionen. Zweitens release wir im Klassendestruktor, die Ressource dann abgerufen, wenn das Objekt erstellt wurde.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // everything else...  
};  
```  
  
 Das Objekt ist lokal mithilfe der Typname, jedoch ohne die zugehörigen Hat deklariert. Alle Vorkommen des Objekts, z. B. das Aufrufen einer Methode erfolgen über den Punkt der Member-Auswahl (`.`) anstelle von Pfeil (`->`). Am Ende des Blocks wird der zugehörige Destruktor in transformiert `Dispose`, automatisch aufgerufen, wie hier gezeigt:  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here -  
   // that is, r.Dispose() is invoked  
}  
```  
  
 Wie bei der `using` -Anweisung in c#, ist dies nicht die zugrunde liegenden CLR-Einschränkung, dass alle Referenztypen gibt muss auf dem CLR-Heap zugewiesen werden. Die zugrunde liegende Semantik bleiben unverändert. Der Benutzer konnte gleichwertig geschrieben haben, Folgendes (und dies ist wahrscheinlich die interne, vom Compiler durchgeführten Transformation):  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 Tatsächlich in der neuen Syntax Destruktoren werden erneut gekoppelt mit Konstruktoren als eine automatisierte Abrufs oder der Freigabe Mechanismus an ein lokales Objekt Lebensdauer gebunden.  
  
## <a name="declaring-an-explicit-finalize"></a>Deklarieren von expliziten Finalize-Methode  
 In der neuen Syntax wie wir gesehen haben, der Destruktor wird synthetisiert in die `Dispose` Methode. Dies bedeutet, dass wenn der Destruktor nicht explizit aufgerufen wird, der Garbage Collector während des Abschlusses, nicht wie bisher eine zugeordnete findet, `Finalize` Methode für das Objekt. Zur Unterstützung von-Löschung gewechselt und der Abschluss haben wir eine spezielle Syntax zum Bereitstellen eines Finalizers eingeführt. Zum Beispiel:  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 Die `!` Präfix ist analog zu Tilde (`~`) wird der Destruktor einer Klasse – das heißt, beide Methoden nach der Lebensdauer ein Tokens, die den Namen der Klasse mit einem Präfix haben. Wenn die gebildeter `Finalize` Methode in einer abgeleiteten Klasse einen Aufruf der Basisklasse vorkommt `Finalize` Methode am Ende eingefügt wird. Wenn der Destruktor explizit aufgerufen wird, wird der Finalizer unterdrückt. Hier wird die Transformation könnte folgendermaßen aussehen:  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## <a name="moving-from-managed-extensions-for-c-to-visual-c-2010"></a>Migration von Managed Extensions for C++ auf Visual C++ 2010  
 Das Laufzeitverhalten von Managed Extensions for C++-Programms wird geändert, wenn er unter Visual C++ kompiliert wird, wenn eine Verweisklasse einen nicht trivialen Destruktor enthält. Der erforderliche Übersetzung-Algorithmus ist ähnlich der folgenden:  
  
1.  Wenn ein Destruktor vorhanden ist, neu schreiben Sie, um Klassenfinalizer aus.  
  
2.  Wenn eine `Dispose` Methode vorhanden ist, neu schreiben, der in der Destruktor der Klasse.  
  
3.  Wenn ein Destruktor vorhanden ist, aber es ist keine `Dispose` -Methode, behalten Sie den Destruktor beim Ausführen des ersten Elements.  
  
 Verschieben von Code in die neue Syntax von Managed Extensions, können Sie verstößt, führt dieser Transformation. Wenn die Anwendung in irgendeiner Weise bei der Ausführung der zugehörigen abhing, wird das Verhalten der Anwendung im Hintergrund der unterscheiden sich von Ihnen vorgesehenen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltete Typen (C + c++ / CL)](../dotnet/managed-types-cpp-cl.md)   
 [Destruktoren und Finalizer wie: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI)](../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers)