---
title: "Destruktoren (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ (Operator), Angeben von Destruktoren"
  - "Zerstören von Objekten, Destruktoren"
  - "Destruktoren, Informationen über Destruktoren"
  - "Destruktoren, C++"
  - "Objekte [C++], Zerstören"
  - "Visual C++, Destruktoren"
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Destruktoren (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Destruktorfunktionen sind das Gegenteil von Konstruktorfunktionen.  Sie werden aufgerufen, wenn Objekte zerstört \(freigegeben\) werden.  Legen Sie eine Funktion als Destruktor einer Klasse fest, indem Sie dem Klassennamen eine Tilde \(`~`\) voranstellen.  Beispielsweise wird der Destruktor für die `String`\-Klasse folgendermaßen deklariert: `~String()`.  
  
 In einer \/clr\- Kompilierung hat der Destruktor eine besondere Rolle bei der Freigabe verwalteter und nicht verwalteter Ressourcen.  Weitere Informationen finden Sie unter [Destruktoren und Finalizer in Visual C\+\+](../misc/destructors-and-finalizers-in-visual-cpp.md).  
  
 Der Destruktor wird häufig zum "Bereinigen" verwendet, wenn ein Objekt nicht mehr erforderlich ist.  Betrachten Sie die folgende Deklaration einer `String`\-Klasse.  
  
```  
// spec1_destructors.cpp  
#include <string.h>  
  
class String {  
public:  
   String( char *ch );  // Declare constructor  
   ~String();           //  and destructor.  
private:  
   char    *_text;  
   size_t  sizeOfText;  
};  
  
// Define the constructor.  
String::String( char *ch ) {  
   sizeOfText = strlen( ch ) + 1;  
  
   // Dynamically allocate the correct amount of memory.  
   _text = new char[ sizeOfText ];  
  
   // If the allocation succeeds, copy the initialization string.  
   if( _text )  
      strcpy_s( _text, sizeOfText, ch );  
}  
  
// Define the destructor.  
String::~String() {  
   // Deallocate the memory that was previously reserved  
   //  for this string.  
   if (_text)  
      delete[] _text;  
}  
  
int main() {  
   String str("The piper in the glen...");  
}  
```  
  
 Im vorangehenden Beispiel verwendet der `String::~String`\-Destruktor den `delete`\-Operator, um den Speicherplatz freizugeben, der dynamisch Textspeicher zugeordnet wird.  
  
## Deklarieren von Destruktoren  
 Destruktoren sind Funktionen mit dem gleichen Namen wie die Klasse, jedoch mit einer vorangestellten Tilde \(`~`\).  
  
 Die erste Form der Syntax wird für Destruktoren verwendet, die innerhalb der Klassendeklaration deklariert oder definiert werden. Die zweite Form wird für Destruktoren verwendet, die außerhalb einer Klassendeklaration definiert werden.  
  
 Mehrere Regeln bestimmen die Deklaration von Destruktoren.  Destruktoren:  
  
-   Akzeptieren keine Argumente.  
  
-   Können keinen Rückgabetyp angeben \(einschließlich `void`\).  
  
-   Können keinen Wert mithilfe der `return`\-Anweisung zurückgeben.  
  
-   Können nicht als **const**, `volatile` oder **static** deklariert werden.  Allerdings können sie für die Zerstörung von Objekten aufgerufen werden, die als **const**, `volatile` oder **static** deklariert sind.  
  
-   Können als **virtual** deklariert werden.  Mithilfe von virtuellen Destruktoren können Sie Objekte zerstören, ohne ihren Typ zu kennen. Der richtige Destruktor für das Objekt wird mithilfe des Mechanismus der virtuellen Funktion aufgerufen.  Destruktoren können auch als rein virtuelle Funktionen für abstrakte Klassen deklariert werden.  
  
## Verwenden von Destruktoren  
 Destruktoren werden aufgerufen, wenn eines der folgenden Ereignisse eintritt:  
  
-   Ein Objekt, das mit dem **new**\-Operator zugeordnet ist, wird mithilfe des **delete**\-Operators explizit freigegeben.  Wenn Objekte mithilfe des **delete**\-Operators freigegeben werden, wird Speicherplatz für das "am stärksten abgeleitete Objekt" oder das Objekt freigegeben, das ein vollständiges Objekt und kein Unterobjekt ist, das eine Basisklasse darstellt.  Diese Freigabe des "am stärksten abgeleiteten Objekts" funktioniert nur mit virtuellen Destruktoren auf jeden Fall.  In Mehrfachvererbungssituationen, in denen die Typinformationen nicht dem zugrunde liegenden Typ des eigentlichen Objekts entsprechen, kann ein Fehler bei der Freigabe auftreten.  
  
-   Ein lokales \(automatisches\) Objekt mit Blockgültigkeit verlässt den Gültigkeitsbereich.  
  
-   Die Lebensdauer eines temporären Objekts endet.  
  
-   Ein Programm endet, und es sind globale oder statische Objekte vorhanden.  
  
-   Der Destruktor wird unter Verwendung des vollqualifizierten Namens der Funktion explizit aufgerufen.  \(Weitere Informationen finden Sie unter [Explizite Destruktoraufrufe](../misc/explicit-destructor-calls.md)\).  
  
 Die Fälle, die in der obigen Liste beschrieben werden, stellen sicher, dass alle Objekte mit benutzerdefinierten Methoden gelöscht werden können.  
  
 Wenn eine Basisklasse oder ein Datenmember über einen zugreifbaren Destruktor verfügt und eine abgeleitete Klasse keinen Destruktor deklariert, generiert der Compiler einen.  Dieser vom Compiler generierte Destruktor ruft den Basisklassendestruktor und Destruktoren für Member des abgeleiteten Typs auf.  Standarddestruktoren sind öffentlich.  \(Weitere Informationen zum Zugriff finden Sie unter [Zugriffsspezifizierer für Basisklassen](../misc/access-specifiers-for-base-classes.md)\).  
  
 Destruktoren können beliebig Klassenmemberfunktionen aufrufen und auf Klassenmemberdaten zugreifen.  Wenn eine virtuelle Funktion von einem Destruktor aufgerufen wird, ist die aufgerufene Funktion die Funktion für die Klasse, die gerade zerstört wird.  Weitere Informationen finden Sie unter [Reihenfolge der Destruktion](../misc/order-of-destruction.md).  
  
 Es gibt zwei Einschränkungen bei der Verwendung von Destruktoren.  Die erste Einschränkung besteht darin, dass Sie die Adresse eines Destruktors nicht übernehmen können.  Das zweite Einschränkung ist, dass abgeleitete Klassen nicht die Destruktoren ihrer Basisklasse erben.  Stattdessen, wie bereits erläutert, überschreiben sie immer die Destruktoren der Basisklasse.  
  
## Reihenfolge der Destruktion  
 Wenn ein Objekt den gültigen Bereich verlässt oder gelöscht wird, lautet die Reihenfolge der Ereignisse bei seiner vollständigen Zerstörung wie folgt:  
  
1.  Der Destruktor der Klasse wird aufgerufen, und der Text der Destruktorfunktion wird ausgeführt.  
  
2.  Destruktoren für nicht statische Memberobjekte werden in umgekehrter Reihenfolge aufgerufen, in der sie in der Klassendeklaration stehen.  Die optionale Memberinitialisierungsliste, die bei der Konstruktion dieser Member verwendet wird, wirkt sich nicht auf die Reihenfolge der \(Konstruktion oder\) Zerstörung aus.  \(Weitere Informationen zur Initialisierung von Membern finden Sie auf der Seite zum [Initialisieren von Basen und Membern](assetId:///2f71377e-2b6b-49da-9a26-18e9b40226a1)\).  
  
3.  Destruktoren für nicht virtuelle Basisklassen werden in umgekehrter Reihenfolge der Deklaration aufgerufen.  
  
4.  Destruktoren für virtuelle Basisklassen werden in umgekehrter Reihenfolge der Deklaration aufgerufen.  
  
```  
// order_of_destruction.cpp  
#include <stdio.h>  
  
struct A1      { virtual ~A1() { printf("A1 dtor\n"); } };  
struct A2 : A1 { virtual ~A2() { printf("A2 dtor\n"); } };  
struct A3 : A2 { virtual ~A3() { printf("A3 dtor\n"); } };  
  
struct B1      { ~B1() { printf("B1 dtor\n"); } };  
struct B2 : B1 { ~B2() { printf("B2 dtor\n"); } };  
struct B3 : B2 { ~B3() { printf("B3 dtor\n"); } };  
  
int main() {  
   A1 * a = new A3;  
   delete a;  
   printf("\n");  
  
   B1 * b = new B3;  
   delete b;  
   printf("\n");  
  
   B3 * b2 = new B3;  
   delete b2;  
}  
  
Output: A3 dtor  
A2 dtor  
A1 dtor  
  
B1 dtor  
  
B3 dtor  
B2 dtor  
B1 dtor  
  
```  
  
### Virtuelle Basisklassen  
 Destruktoren für virtuelle Basisklassen werden in umgekehrter Reihenfolge ihrer Darstellung in einem gerichteten azyklischen Diagramm aufgerufen \(Durchlauf vom tiefsten Punkt nach oben, von links nach rechts, Postorder\-Durchlauf\).  Die folgende Abbildung stellt ein Vererbungsdiagramm dar.  
  
 ![Vererbungsdiagramm mit mit virtuellen Basisklassen](../cpp/media/vc392j1.png "vc392J1")  
Vererbungsdiagramm mit virtuellen Basisklassen  
  
 Im Folgenden werden die Klassenköpfe für die in der Abbildung dargestellten Klassen aufgeführt.  
  
```  
class A  
class B  
class C : virtual public A, virtual public B  
class D : virtual public A, virtual public B  
class E : public C, public D, virtual public B  
```  
  
 Um die Reihenfolge zum Löschen der virtuellen Basisklassen eines Objekts vom Typ `E` zu bestimmen, erstellt der Compiler eine Liste mithilfe des folgenden Algorithmus:  
  
1.  Durchlaufen Sie das Diagramm von links, und beginnen Sie mit dem tiefsten Punkt im Diagramm \(in diesem Fall `E`\).  
  
2.  Führen Sie Durchläufe von links aus, bis alle Knoten aufgerufen wurden.  Notieren Sie den Namen des aktuellen Knotens.  
  
3.  Rufen Sie erneut den vorherigen Knoten auf \(nach unten und rechts\), um festzustellen, ob es sich bei dem gemerkten Knoten um eine virtuelle Basisklasse handelt.  
  
4.  Falls der gemerkte Knoten eine virtuelle Basisklasse ist, prüfen Sie anhand der Liste, ob diese bereits erfasst ist.  Handelt es sich nicht um eine Basisklasse, können Sie dies ignorieren.  
  
5.  Sofern der gemerkte Knoten noch nicht in der Liste vorhanden ist, fügen Sie ihn unten hinzu.  
  
6.  Durchlaufen Sie das Diagramm nach oben und entlang des nächsten Pfads nach rechts.  
  
7.  Wechseln Sie zu Schritt 2.  
  
8.  Wenn der letzte nach oben zeigende Pfeil angezeigt wird, notieren Sie den Namen des aktuellen Knotens.  
  
9. Gehen Sie zu Schritt 3.  
  
10. Setzen Sie diesen Vorgang fort, bis der untere Knoten wieder der aktuelle Knoten ist.  
  
 Daher lautet für die Klasse `E` die Reihenfolge der Löschung wie folgt:  
  
1.  Die nicht virtuelle Basisklasse `E`.  
  
2.  Die nicht virtuelle Basisklasse `D`.  
  
3.  Die nicht virtuelle Basisklasse `C`.  
  
4.  Die virtuelle Basisklasse `B`.  
  
5.  Die virtuelle Basisklasse `A`.  
  
 Dieser Prozess erzeugt eine sortierte Liste mit eindeutigen Einträgen.  Kein Klassenname wird zweimal angezeigt.  Sobald die Liste erstellt ist, wird sie in umgekehrter Reihenfolge durchlaufen, und der Destruktor wird für jede Klasse in der Liste \(von der letzten bis zu ersten\) aufgerufen.  
  
 In erster Linie ist die Reihenfolge zum Erstellen oder Löschen wichtig, wenn Konstruktoren oder Destruktoren einer Klasse darauf basieren, dass die andere Komponente erstellt wird oder länger vorhanden ist – beispielsweise wenn der Destruktor für `A` \(in der obigen Abbildung\) darauf basiert, dass `B` bei der Codeausführung noch vorhanden ist \(oder umgekehrt\).  
  
 Folglich sind diese gegenseitigen Abhängigkeiten zwischen den Klassen in einem Vererbungsdiagramm grundsätzlich gefährlich, da später abgeleitete Klassen den am weitesten links stehenden Pfad ändern und somit auch die Reihenfolge zum Erstellen und Löschen verändern können.  
  
### Nicht virtuelle Basisklassen  
 Die Destruktoren für nicht virtuelle Basisklassen werden in umgekehrter Reihenfolge aufgerufen, als die Namen der Basisklassen deklariert werden.  Betrachten Sie die folgende Klassendeklaration:  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 Im vorherigen Beispiel wird der Destruktor für `Base2` vor dem Destruktor für `Base1` aufgerufen.  
  
## Explizite Destruktoraufrufe  
 Einen Destruktor explizit aufzurufen, ist selten notwendig.  Allerdings kann es hilfreich sein, eine Bereinigung von Objekten auszuführen, die an den absoluten Adressen platziert werden.  Diese Objekte werden in der Regel mithilfe eines benutzerdefinierten **new**\-Operators zugeordnet, der ein Platzierungsargument akzeptiert.  Der **delete**\-Operator kann die Zuordnung dieses Speichers nicht aufheben, denn er wurde nicht vom frei verfügbaren Speicherplatz zugewiesen \(weitere Informationen finden Sie unter [Operatoren "new" und "delete"](../cpp/new-and-delete-operators.md)\).  Ein Aufruf des Destruktors kann jedoch eine geeignete Bereinigung ausführen.  Mit einer der folgenden Anweisungen können Sie den Destruktor für ein Objekt `s` der Klasse `String` explizit aufrufen:  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 Die Notation für explizite Aufrufe von Destruktoren \(zuvor gezeigt\) kann unabhängig davon verwendet werden, ob der Typ einen Destruktor definiert.  Dies ermöglicht Ihnen solche expliziten Aufrufe, ohne zu wissen, ob ein Destruktor für den Typ definiert ist.  Ein expliziter Aufruf von einem Destruktor, wenn keiner definiert ist, hat keine Auswirkungen.  
  
## Siehe auch  
 [Spezielle Memberfunktionen](../misc/special-member-functions-cpp.md)