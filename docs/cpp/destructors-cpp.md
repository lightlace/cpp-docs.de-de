---
title: Destruktoren (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- objects [C++], destroying
- Visual C++, destructors
- destroying objects, destructors
- ~ operator [C++], specifying destructors
- destructors, about destructors
- destructors, C++
ms.assetid: afa859b0-f3bc-4c4d-b250-c68b335b6004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae1ca6923bc7e67218e35c5a6c86b9f4ac112e59
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="destructors-c"></a>Destruktoren (C++)
Ein Destruktor ist eine Memberfunktion, die automatisch aufgerufen wird, wenn das Objekt den Gültigkeitsbereich verlässt oder ausdrücklich durch einen Aufruf von zerstört wird `delete`. Ein Destruktor hat den gleichen Namen wie die Klasse, die vorangestellten Tilde (`~`). Beispielsweise wird der Destruktor für die `String`-Klasse folgendermaßen deklariert: `~String()`. Wenn Sie keinen Destruktor definieren, wird der Compiler eine standardmäßige bereit; Dies ist für viele Klassen ausreichend. Müssen Sie nur einen benutzerdefinierten Destruktor definieren, wenn die Klasse Handles für Systemressourcen speichert, die freigegeben werden müssen, oder Zeiger, die den Speicher besitzen, die sie zu verweisen.

Betrachten Sie die folgende Deklaration einer `String`-Klasse.  
  
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
  
 Im vorangehenden Beispiel verwendet der `String::~String`-Destruktor den `delete`-Operator, um den Speicherplatz freizugeben, der dynamisch Textspeicher zugeordnet wird.  
  
## <a name="declaring-destructors"></a>Deklarieren von Destruktoren  
 Destruktoren sind Funktionen mit dem gleichen Namen wie die Klasse, jedoch mit einer vorangestellten Tilde (`~`).  
  
 Mehrere Regeln bestimmen die Deklaration von Destruktoren. Destruktoren:  
  
-   Akzeptieren keine Argumente.  
  
-   Lassen Sie einen Wert zurückgeben (oder `void`).  
  
-   Kann nicht deklariert werden, als **const**, `volatile`, oder **statische**. Allerdings aufgerufen werden, für die Zerstörung von Objekten als deklariert **const**, `volatile`, oder **statische**.  
  
-   Kann als deklariert werden **virtuellen**. Mithilfe von virtuellen Destruktoren können Sie Objekte zerstören, ohne ihren Typ zu kennen. Der richtige Destruktor für das Objekt wird mithilfe des Mechanismus der virtuellen Funktion aufgerufen. Destruktoren können auch als rein virtuelle Funktionen für abstrakte Klassen deklariert werden.  
  
## <a name="using-destructors"></a>Verwenden von Destruktoren  
 Destruktoren werden aufgerufen, wenn eines der folgenden Ereignisse eintritt:  

-   Ein lokales (automatisches) Objekt mit Blockbereich verlässt den Gültigkeitsbereich.  

-   Ein Objekt, das mithilfe von zugeordnet, die **neue** Operator wird explizit freigegeben mit **löschen**.   
  
-   Die Lebensdauer eines temporären Objekts endet.  
  
-   Ein Programm endet, und es sind globale oder statische Objekte vorhanden.  
  
-   Der Destruktor wird unter Verwendung des vollqualifizierten Namens der Funktion explizit aufgerufen.
  
 Destruktoren können beliebig Klassenmemberfunktionen aufrufen und auf Klassenmemberdaten zugreifen.
  
 Es gibt zwei Einschränkungen bei der Verwendung von Destruktoren aus:
 - Sie können nicht deren Adresse zu übernehmen.
-  abgeleitete Klassen erben nicht den Destruktor von ihrer Basisklasse.
  
## <a name="order-of-destruction"></a>Reihenfolge der Destruktion  
 Wenn ein Objekt den gültigen Bereich verlässt oder gelöscht wird, lautet die Reihenfolge der Ereignisse bei seiner vollständigen Zerstörung wie folgt:  
  
1.  Der Destruktor der Klasse wird aufgerufen, und der Text der Destruktorfunktion wird ausgeführt.  
  
2.  Destruktoren für nicht statische Memberobjekte werden in umgekehrter Reihenfolge aufgerufen, in der sie in der Klassendeklaration stehen. Die optionale Memberinitialisierungsliste Konstruktion dieser Member verwendet wirkt sich nicht auf die Reihenfolge der Konstruktion oder Zerstörung aus.   
  
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
  
### <a name="virtual-base-classes"></a>Virtuelle Basisklassen  
 Destruktoren für virtuelle Basisklassen werden in umgekehrter Reihenfolge ihrer Darstellung in einem gerichteten azyklischen Diagramm aufgerufen (Durchlauf vom tiefsten Punkt nach oben, von links nach rechts, Postorder-Durchlauf). Die folgende Abbildung stellt ein Vererbungsdiagramm dar.  
  
 ![Vererbungsdiagramm, die von virtuellen Basisklassen](../cpp/media/vc392j1.gif "vc392J1")  
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
  
1.  Durchlaufen Sie das Diagramm von links, und beginnen Sie mit dem tiefsten Punkt im Diagramm (in diesem Fall `E`).  
  
2.  Führen Sie Durchläufe von links aus, bis alle Knoten aufgerufen wurden. Notieren Sie den Namen des aktuellen Knotens.  
  
3.  Rufen Sie erneut den vorherigen Knoten auf (nach unten und rechts), um festzustellen, ob es sich bei dem gemerkten Knoten um eine virtuelle Basisklasse handelt.  
  
4.  Falls der gemerkte Knoten eine virtuelle Basisklasse ist, prüfen Sie anhand der Liste, ob diese bereits erfasst ist. Handelt es sich nicht um eine Basisklasse, können Sie dies ignorieren.  
  
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
  
 Dieser Prozess erzeugt eine sortierte Liste mit eindeutigen Einträgen. Kein Klassenname wird zweimal angezeigt. Sobald die Liste erstellt ist, wird sie in umgekehrter Reihenfolge durchlaufen, und der Destruktor wird für jede Klasse in der Liste (von der letzten bis zu ersten) aufgerufen.  
  
 In erster Linie ist die Reihenfolge zum Erstellen oder Löschen wichtig, wenn Konstruktoren oder Destruktoren einer Klasse darauf basieren, dass die andere Komponente erstellt wird oder länger vorhanden ist – beispielsweise wenn der Destruktor für `A` (in der obigen Abbildung) darauf basiert, dass `B` bei der Codeausführung noch vorhanden ist (oder umgekehrt).  
  
 Folglich sind diese gegenseitigen Abhängigkeiten zwischen den Klassen in einem Vererbungsdiagramm grundsätzlich gefährlich, da später abgeleitete Klassen den am weitesten links stehenden Pfad ändern und somit auch die Reihenfolge zum Erstellen und Löschen verändern können.  
  
### <a name="nonvirtual-base-classes"></a>Nicht virtuelle Basisklassen  
 Die Destruktoren für nicht virtuelle Basisklassen werden in umgekehrter Reihenfolge aufgerufen, als die Namen der Basisklassen deklariert werden. Betrachten Sie die folgende Klassendeklaration:  
  
```  
class MultInherit : public Base1, public Base2  
...  
```  
  
 Im vorherigen Beispiel wird der Destruktor für `Base2` vor dem Destruktor für `Base1` aufgerufen.  
  
## <a name="explicit-destructor-calls"></a>Explizite Destruktoraufrufe  
 Einen Destruktor explizit aufzurufen, ist selten notwendig. Allerdings kann es hilfreich sein, eine Bereinigung von Objekten auszuführen, die an den absoluten Adressen platziert werden. Diese Objekte häufig mithilfe einer benutzerdefinierten zugeordnet **neue** Operator, der ein platzierungsargument akzeptiert. Die **löschen** Operator kann nicht diesen Arbeitsspeicher freigeben, da es nicht aus dem freien Speicher reserviert wird (Weitere Informationen finden Sie unter [die neue "und" delete](../cpp/new-and-delete-operators.md)). Ein Aufruf des Destruktors kann jedoch eine geeignete Bereinigung ausführen. Mit einer der folgenden Anweisungen können Sie den Destruktor für ein Objekt `s` der Klasse `String` explizit aufrufen:  
  
```  
s.String::~String();     // Nonvirtual call  
ps->String::~String();   // Nonvirtual call  
  
s.~String();       // Virtual call  
ps->~String();     // Virtual call  
```  
  
 Die Notation für explizite Aufrufe von Destruktoren (zuvor gezeigt) kann unabhängig davon verwendet werden, ob der Typ einen Destruktor definiert. Dies ermöglicht Ihnen solche expliziten Aufrufe, ohne zu wissen, ob ein Destruktor für den Typ definiert ist. Ein expliziter Aufruf von einem Destruktor, wenn keiner definiert ist, hat keine Auswirkungen.  
