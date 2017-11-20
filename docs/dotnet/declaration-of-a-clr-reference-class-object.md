---
title: Deklaration eines CLR-Klasse Verweisobjekt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- types [C++], reference types
- reference types, CLR
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 973500cc276d95e523859a5fcc1b9a5f7a707bb0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="declaration-of-a-clr-reference-class-object"></a>Deklaration eines CLR-Verweisklassenobjekts
Die Syntax zum Deklarieren und instanziieren Sie ein Objekt eines Verweistyps für die Klasse hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions wird einem Typ Referenzklassenobjekt deklariert wird, indem die ISO C++-Zeiger-Syntax mit einer optionalen Verwendungsmöglichkeit eines der `__gc` Schlüsselwort auf der linken Seite des Sterns (`*`). Hier sind beispielsweise eine Vielzahl von Verweis Klassendeklarationen Typ-Objekt in der Managed Extensions-Syntax:  
  
```  
public __gc class Form1 : public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container __gc *components;  
   Button __gc *button1;  
   DataGrid __gc *myDataGrid;     
   DataSet __gc *myDataSet;  
  
   void PrintValues( Array* myArr ) {  
      System::Collections::IEnumerator* myEnumerator =   
         myArr->GetEnumerator();  
  
      Array *localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);  
   }  
};  
```  
  
 In der neuen Syntax deklarieren Sie ein Objekt vom Typ Verweisklasse mit einem neuen deklarativen Token (`^`) formal als bezeichnet eine *Trackinghandle* und informell als eine *Hat*. (Tracking bedeutet, dass ein Verweistyp in dem CLR-Heap befindet, und daher während der Garbage Collection-Heapkomprimierung auf transparent verschieben kann. Ein Trackinghandle wird während der Laufzeit transparent aktualisiert. Zwei ähnliche Konzepte der *Nachverfolgungsverweis* (`%`), und die *innerer Zeiger* (`interior_ptr<>`), erläutert in [Werttypsemantik](../dotnet/value-type-semantics.md).  
  
 Die Hauptgründe für die deklarative Syntax eine Wiederverwendung der Syntax der ISO C++-Zeiger verschieben lauten wie folgt:  
  
-   Der Zeigersyntax überladene Operatoren direkt auf ein Verweis-Objekt angewendet werden soll nicht zulässig. Stattdessen eine den Operator aufrufen, indem Sie den internen Namen, z. B. mit musste `rV1->op_Addition(rV2)` anstelle der intuitiver `rV1+rV2`.  
  
-   Eine Anzahl von Zeiger-Vorgänge, z. B. die Umwandlung und Zeigerarithmetik, nicht zulässig für Objekte, die auf einen Garbage gespeichert gesammelten Heap. Der Begriff ein Trackinghandle besser erfasst das Wesen einen CLR-Referenztyp darstellt.  
  
 Die `__gc` ein Trackinghandle-Modifizierer ist nicht erforderlich und wird nicht unterstützt. Die Verwendung des Objekts selbst wird nicht geändert. immer noch auf Member zugreift, durch die Zeiger Memberauswahloperator (`->`). Hier wird beispielsweise im vorherigen Codebeispiel für Managed Extensions in der neuen Syntax übersetzt:  
  
```  
public ref class Form1: public System::Windows::Forms::Form {  
private:  
   System::ComponentModel::Container^ components;  
   Button^ button1;  
   DataGrid^ myDataGrid;  
   DataSet^ myDataSet;  
  
   void PrintValues( Array^ myArr ) {  
      System::Collections::IEnumerator^ myEnumerator =  
         myArr->GetEnumerator();  
  
      Array ^localArray;  
      myArr->Copy(myArr, localArray, myArr->Length);   }  
};  
```  
  
## <a name="dynamic-allocation-of-an-object-on-the-clr-heap"></a>Dynamische Zuweisung eines Objekts auf dem CLR-Heap  
 In Managed Extensions wird das Vorhandensein von zwei `new` Ausdrücke, die zwischen dem systemeigenen und verwalteten Heap zugeordnet war weitestgehend transparent. In fast allen Fällen kann der Compiler den Kontext verwenden, um zu ermitteln, ob aus dem systemeigenen oder verwalteten Heap belegt. Beispiel:  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Wenn Sie nicht die kontextbezogene Heapreservierung möchten, könnten Sie weitergeleitet werden den Compiler entweder mit der `__gc` oder `__nogc` Schlüsselwort. In der neuen Syntax wird der separaten Natur der beiden neuen Ausdrücke werden zu expliziten Informationen mit der Einführung der `gcnew` Schlüsselwort. Beispielsweise sehen die vorherigen drei Deklarationen wie folgt in der neuen Syntax:  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Hier ist die Initialisierung Managed Extensions die `Form1` Member deklariert hat, im vorherigen Abschnitt:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Hier ist die gleiche Initialisierung der neuen Syntax. Beachten Sie, dass die Hat nicht für den Verweistyp erforderlich ist, wenn es sich um das Ziel ist eine `gcnew` Ausdruck.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## <a name="a-tracking-reference-to-no-object"></a>Ein Nachverfolgungsverweis auf kein Objekt  
 In der neuen Syntax `0` nicht mehr eine null-Adresse entspricht im Gegensatz zu wird als eine ganze Zahl, die identisch behandelt `1`, `10`, oder `100`. Ein neues spezielles Token stellt einen null-Wert für ein Nachverfolgungsverweis dar. In Managed Extensions initialisieren wir z. B. einen Verweistyp um kein Objekt wie folgt beheben:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 In der neuen Syntax eine Initialisierung oder Zuweisung eines Werts geben Sie an einer `Object` bewirkt, dass ein implizites Boxing eines Werttyps. In der neuen Syntax beide `obj` und `obj2` behandelt geschachtelte Int32-Objekten, die die Werte 0 und 1, jeweils mit initialisiert werden. Zum Beispiel:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Aus diesem Grund um explizite Initialisierung, Zuweisung und ein Trackinghandle für null-Vergleich auszuführen, verwenden Sie ein neues Schlüsselwort `nullptr`.  Die richtige Version des im ursprünglichen Beispiel sieht wie folgt aus:  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Dadurch wird der etwas das Portieren von vorhandenem Code in der neuen Syntax komplizierter. Betrachten Sie beispielsweise die folgende Klassendeklaration für den Wert aus:  
  
```  
__value struct Holder {  
   Holder( Continuation* c, Sexpr* v ) {  
      cont = c;  
      value = v;  
      args = 0;  
      env = 0;  
   }  
  
private:  
   Continuation* cont;  
   Sexpr * value;  
   Environment* env;  
   Sexpr * args __gc [];  
};  
```  
  
 Hier wird sowohl `args` und `env` sind CLR-Referenztypen. Die Initialisierung des dieser beiden Member mit `0` im Konstruktor kann nicht unverändert in die Umstellung auf die neue Syntax. Sie müssen vielmehr geändert werden, um `nullptr`:  
  
```  
value struct Holder {  
   Holder( Continuation^ c, Sexpr^ v )  
   {  
      cont = c;  
      value = v;  
      args = nullptr;  
      env = nullptr;  
   }  
  
private:  
   Continuation^ cont;  
   Sexpr^ value;  
   Environment^ env;  
   array<Sexpr^>^ args;  
};  
```  
  
 Für diese Elemente, die sie zu vergleichen, die auf ähnliche Weise testet `0` muss ebenfalls geändert werden, um die Elemente zu vergleichen `nullptr`. Hier ist die Managed Extensions-Syntax:  
  
```  
Sexpr * Loop (Sexpr* input) {  
   value = 0;  
   Holder holder = Interpret(this, input, env);  
  
   while (holder.cont != 0) {  
      if (holder.env != 0) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != 0) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 Hier wird die Revision, ersetzen jede `0` -Instanz mit einem `nullptr`. Das Übersetzungstool hilfreich automatisieren viele, wenn nicht alle Vorkommen, einschließlich der Verwendung von der `NULL` Makro.  
  
```  
Sexpr ^ Loop (Sexpr^ input) {  
   value = nullptr;  
   Holder holder = Interpret(this, input, env);  
  
   while ( holder.cont != nullptr ) {  
      if ( holder.env != nullptr ) {  
         holder=Interpret(holder.cont,holder.value,holder.env);  
      }  
      else if (holder.args != nullptr ) {  
         holder =   
         holder.value->closure()->  
         apply(holder.cont,holder.args);  
      }  
   }  
  
   return value;  
}  
```  
  
 Die `nullptr` , die in ein beliebiges Handle Zeiger- oder konvertiert wird, aber nicht in einen ganzzahligen Typ heraufgestuft wird. In den folgenden Satz von Initialisierungen, beispielsweise die `nullptr` nur als einen Anfangswert für die ersten beiden gültig ist.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0  
int ival = nullptr;  
```  
  
 Auf ähnliche Weise betrachten einen überladenen Satz von Methoden wie z. B. Folgendes ein:  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 Ein Aufruf mit `nullptr` literal, z. B. Folgendes ein,  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 ist mehrdeutig, da die `nullptr` entspricht ein Trackinghandle und ein Zeiger ist, und es gibt keine Präferenz auf einen anderen. (Dies erfordert eine explizite Umwandlung, um eindeutig zu machen.)  
  
 Ein Aufruf mit `0` entspricht genau Instanz (3):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 Da `0` vom Typ Integer ist. Wurden `f(int)` nicht vorhanden ist, der Aufruf eindeutig entsprechen `f(char*)` über eine standardkonvertierung. Die Abgleichsregeln Vorrang eine genaue Übereinstimmung über eine standardkonvertierung. Eine genaue Übereinstimmung vorhanden ist wird eine standardkonvertierung Vorrang über ein implizites Boxing eines Werttyps zugewiesen. Aus diesem Grund ist es keine Mehrdeutigkeit.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltete Typen (C + c++ / CL)](../dotnet/managed-types-cpp-cl.md)   
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)