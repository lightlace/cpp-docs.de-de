---
title: "&#196;nderungen in der Destruktorsemantik | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Destruktoren, C++"
  - "Finalizer [C++]"
ms.assetid: f1869944-a407-452f-b99a-04d8c209f0dc
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# &#196;nderungen in der Destruktorsemantik
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Semantik für Klassendestruktoren hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ grundlegend geändert.  
  
 In Managed Extensions war es zwar zulässig, dass ein Klassendestruktor innerhalb einer Verweisklasse steht, nicht jedoch innerhalb einer Wertklasse.  Dies hat sich auch mit der neuen Syntax nicht geändert.  Allerdings hat sich die Semantik des Klassendestruktors verändert.  In diesem Thema werden die Gründe für diese Änderungen und die Auswirkungen auf die Übersetzung von vorhandenem CLR\-Code behandelt.  Es handelt sich dabei wahrscheinlich um die wichtigste Änderung auf Programmierebene zwischen den beiden Sprachversionen.  
  
## Nicht deterministischer Abschluss  
 Bevor der Garbage Collector den einem Objekt zugeordneten Arbeitsspeicher zurückfordert, wird, falls vorhanden, eine zugeordnete `Finalize`\-Methode aufgerufen.  Sie können sich diese Methode als eine Art Super\-Destruktor vorstellen, der nicht an die Programmlebensdauer des Objekts gebunden ist.  Dieser Vorgang wird als Abschluss bezeichnet.  Die zeitliche Regulierung, wann und ob eine `Finalize`\-Methode aufgerufen wird, ist nicht definiert.  Wir sprechen in diesem Zusammenhang von einem nicht deterministischen Abschluss der Garbage Collection.  
  
 Der nicht deterministische Abschluss lässt sich gut mit einer dynamischen Speicherverwaltung kombinieren.  Wenn der verfügbare Speicher knapp wird, kommt der Garbage Collector zum Einsatz.  In einer Umgebung mit Garbage Collection werden keine Destruktoren zur Freigabe von Arbeitsspeicher benötigt.  Der nicht deterministische Abschluss eignet sich hingegen weniger für ein Szenario, in dem ein Objekt eine kritische Ressource verwaltet, z. B. eine Datenbankverbindung oder eine Art Sperre.  In diesem Fall sollte diese Ressource so schnell wie möglich freigegeben werden.  In einer systemeigenen Umgebung wird dies durch ein Konstruktor\/Destruktor\-Paar erreicht.  Sobald die Lebensdauer des Objekts abgelaufen ist, entweder durch Vervollständigung des lokalen Blocks, in dem es deklariert ist, oder durch Auflösung des Stapels aufgrund einer ausgelösten Ausnahme, kommt der Destruktor zum Einsatz, und die Ressource wird automatisch freigegeben.  Dieser Ansatz funktioniert sehr gut und wurde in Managed Extensions noch schmerzlich vermisst.  
  
 Die von der CLR bereitgestellte Lösung besteht darin, für eine Klasse die `Dispose`\-Methode der `IDisposable`\-Schnittstelle zu implementieren.  Problematisch ist dabei jedoch, dass `Dispose` einen expliziten Aufruf vom Benutzer erfordert.  Dieser Vorgang ist fehleranfällig.  Die Programmiersprache C\# bietet eine bequeme Art der Automatisierung in Form einer speziellen `using`\-Anweisung.  Das Managed Extensions\-Design bot keinerlei besondere Unterstützung.  
  
## Destruktoren in Managed Extensions for C\+\+  
 In Managed Extensions wird der Destruktor einer Verweisklasse durch folgende zwei Schritte implementiert:  
  
1.  Der vom Benutzer bereitgestellte Destruktor wird intern in `Finalize` umbenannt.  Wenn die Klasse über eine Basisklasse verfügt \(beachten Sie, dass unter dem CLR\-Objektmodell nur die einfache Vererbung unterstützt wird\), fügt der Compiler nach der Ausführung des vom Benutzer bereitgestellten Codes einen Aufruf des Finalizers der Basisklasse ein.  Gehen wir z. B. von der folgenden einfachen Hierarchie aus, die der Managed Extensions\-Programmiersprachenspezifikation entnommen wurde:  
  
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
  
 In diesem Beispiel werden beide Destruktoren in `Finalize` umbenannt.  Der `Finalize`\-Methode von `B` wird ein Aufruf der `Finalize`\-Methode von `A` hinzugefügt, der auf den Aufruf von `WriteLine` folgt.  Diese Aufrufe werden vom Garbage Collector bei einem Abschluss standardmäßig ausgeführt.  Die interne Transformation könnte folgendermaßen aussehen:  
  
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
  
1.  Im zweiten Schritt synthetisiert der Compiler einen virtuellen Destruktor.  Es ist dieser Destruktor, der von Managed Extensions\-Benutzerprogrammen entweder direkt oder über eine Anwendung des Löschausdrucks aufgerufen wird.  Er wird nie vom Garbage Collector aufgerufen.  
  
     In diesen synthetisierten Destruktor werden zwei Anweisungen eingefügt.  Bei der einen handelt es sich um einen Aufruf von `GC::SuppressFinalize`, der sicherstellen soll, dass keine weiteren Aufrufe von `Finalize` erfolgen.  Bei der zweiten handelt es sich um den eigentlichen Aufruf von `Finalize`, der den vom Benutzer bereitgestellten Destruktor für diese Klasse darstellt.  Dieser könnte folgendermaßen aussehen:  
  
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
  
 Auch wenn der Benutzer mit dieser Implementierung die `Finalize`\-Methode explizit zu einem bestimmten Zeitpunkt aufrufen kann, knüpft dies nicht wirklich an die Lösung der `Dispose`\-Methode an.  Dies wurde in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] geändert.  
  
## Destruktoren in der neuen Syntax  
 In der neuen Syntax wird der Destruktor intern in die `Dispose`\-Methode umbenannt, und die Verweisklasse wird automatisch um die Implementierung der `IDispose`\-Schnittstelle erweitert.  In [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] wird das Klassenpaar demnach folgendermaßen umgewandelt:  
  
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
  
 Wenn jetzt in der neuen Syntax entweder ein Destruktor explizit aufgerufen oder `delete` auf ein Trackinghandle angewendet wird, dann wird die zugrunde liegende `Dispose`\-Methode automatisch aufgerufen.  Wenn es sich dabei um eine abgeleitete Klasse handelt, wird ein Aufruf der `Dispose`\-Methode der Basisklasse am Ende der synthetisierten Methode eingefügt.  
  
 Doch führt uns dies nicht bis zum deterministischen Abschluss.  Dazu ist die zusätzliche Unterstützung lokaler Verweisobjekte erforderlich. \(Da es hierfür keine analoge Unterstützung in Managed Extensions gibt, handelt es sich hierbei nicht um ein Übersetzungsproblem.\)  
  
## Deklarieren eines Verweisobjekts  
 [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] unterstützt die Deklaration eines Objekts einer Verweisklasse auf dem lokalen Stapel oder als ein Member einer Klasse so, als ließe sich darauf direkt zugreifen.  In Kombination mit der Zuordnung des Destruktors zur `Dispose`\-Methode entsteht daraus der automatische Aufruf der Finalisierungssemantik für Referenztypen.  
  
 Zuerst wird die Verweisklasse so definiert, dass die Objekterstellung der Ressourcenbelegung mithilfe des Klassenkonstruktors dient.  Danach werden innerhalb des Klassendestruktors die während der Objekterstellung belegten Ressourcen freigegeben.  
  
```  
public ref class R {  
public:  
   R() { /* acquire expensive resource */ }  
   ~R() { /* release expensive resource */ }  
  
   // … everything else …  
};  
```  
  
 Das Objekt wird anhand des Typnamens, aber ohne den begleitenden Hut, lokal deklariert.  Jegliche Verwendung des Objekts, z. B. das Aufrufen einer Methode, erfolgt nicht über einen Pfeil \(`->`\), sondern über den Memberauswahlpunkt \(`.`\).  Am Ende des Blocks wird der zugehörige, in `Dispose` umgewandelte Destruktor automatisch aufgerufen, wie hier gezeigt:  
  
```  
void f() {  
   R r;   
   r.methodCall();  
  
   // r is automatically destructed here –  
   // that is, r.Dispose() is invoked  
}  
```  
  
 Wie auch bei der `using`\-Anweisung in C\# wird dadurch nicht die zugrunde liegende CLR\-Einschränkung überwunden, dass alle Referenztypen auf dem CLR\-Heap reserviert werden müssen.  Die zugrunde liegende Semantik bleibt unverändert.  Ebenso hätte der Benutzer Folgendes schreiben können \(wobei es sich hierbei wahrscheinlich um die intern vom Compiler ausgeführte Transformation handelt\):  
  
```  
// equivalent implementation  
// except that it should be in a try/finally clause  
void f() {  
   R^ r = gcnew R;   
   r->methodCall();  
  
   delete r;  
}  
```  
  
 Faktisch werden in der neuen Syntax Destruktoren erneut mit Konstruktoren gepaart und bilden auf diese Weise einen automatisierten Belegungs\-\/Freigabe\-Mechanismus, der an die Lebensdauer des lokalen Objekts gebunden ist.  
  
## Deklarieren einer expliziten Finalize\-Methode  
 Wie bereits erwähnt, wird der Destruktor in der neuen Syntax in die `Dispose`\-Methode synthetisiert.  Dies hat zur Folge, dass in Fällen, in denen der Destruktor nicht explizit aufgerufen wird, der Garbage Collector während des Abschlusses keine zugehörige `Finalize`\-Methode für das Objekt vorfindet.  Um sowohl die Zerstörung als auch den Abschluss zu unterstützen, wurde eine besondere Syntax zum Bereitstellen eines Finalizers eingeführt.  Beispiel:  
  
```  
public ref class R {  
public:  
   !R() { Console::WriteLine( "I am the R::finalizer()!" ); }  
};  
```  
  
 Das `!`\-Präfix ist analog zur Tilde \(`~`\), die einen Klassendestruktor einführt. Folglich verfügen beide Methoden, die nach Ablauf der Lebensdauer des Objekts aufgerufen werden, über ein Token, das dem Namen der Klasse vorangestellt wird.  Wenn die synthetisierte `Finalize`\-Methode innerhalb einer abgeleiteten Klasse vorkommt, wird an deren Ende ein Aufruf der `Finalize`\-Methode der Basisklasse eingefügt.  Bei einem expliziten Aufruf des Destruktors wird der Finalizer unterdrückt.  Die Transformation könnte folgendermaßen aussehen:  
  
```  
// internal transformation under new syntax  
public ref class R {  
public:  
   void Finalize() {  
      Console::WriteLine( "I am the R::finalizer()!" );  
   }  
};   
```  
  
## Wechsel von Managed Extensions for C\+\+ zu Visual C\+\+ 2010  
 Das Laufzeitverhalten eines unter [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] kompilierten Managed Extensions for C\+\+\-Programms wird immer dann geändert, wenn eine Verweisklasse einen nicht trivialen Destruktor enthält.  Der erforderliche Übersetzungsalgorithmus ähnelt dem folgenden:  
  
1.  Wenn ein Destruktor vorhanden ist, schreiben Sie diesen zu einem Klassenfinalizer um.  
  
2.  Wenn eine `Dispose`\-Methode vorhanden ist, schreiben Sie diese zu einem Klassendestruktor um.  
  
3.  Wenn ein Destruktor, aber keine `Dispose`\-Methode vorhanden ist, behalten Sie den Destruktor bei, während Sie das erste Element ausführen.  
  
 Bei der Transformation des Codes von Managed Extensions in die neue Syntax kann es vorkommen, dass Sie diese Schritte versehentlich auslassen.  Wenn die Anwendung in irgendeiner Weise von der Ausführung der zugehörigen Finalisierungsmethoden abhängig war, tritt eine stillschweigende Abweichung vom erwarteten Verhalten der Anwendung auf.  
  
## Siehe auch  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Destruktoren und Finalizer in Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md)