---
title: "Deklaration eines CLR-Verweisklassenobjekts | Microsoft Docs"
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
  - "Verweistypen, CLR"
  - "Typen [C++], Verweistypen"
ms.assetid: 6d64f746-3715-4948-ada3-88859f4150e4
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Deklaration eines CLR-Verweisklassenobjekts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Syntax zum Deklarieren und Instanziieren eines Objekts vom Verweisklassentyp hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 In Managed Extensions wird ein Verweisklassenobjekt mit der ISO\-C\+\+\-Zeigersyntax deklariert, wahlweise unter Verwendung des `__gc`\-Schlüsselworts links vom Sternchen \(`*`\).  Es folgt eine Reihe von Beispielen für Deklarationen von Objekten vom Typ Verweisklasse in der Managed Extensions\-Syntax:  
  
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
  
 In der neuen Syntax wird ein Objekt vom Typ Verweisklasse mit einem neuen deklarativen Token \(`^`\) deklariert, das formell als *Trackinghandle* und informell als *Hut* bezeichnet wird. \(Tracking bedeutet, dass sich ein Referenztyp im CLR\-Heap befindet und deshalb bei der Komprimierung des Heaps während der Garbage Collection auf transparente Weise den Speicherplatz wechseln kann.\)  Ein Trackinghandle wird während der Laufzeit transparent aktualisiert.  Zwei ähnliche Konzepte, nämlich der *Nachverfolgungsverweis* \(`%`\) und der *innere Zeiger* \(`interior_ptr<>`\), werden unter [Werttypsemantik](../dotnet/value-type-semantics.md) erläutert.  
  
 Es gibt im Wesentlichen zwei Gründe, bei der deklarativen Syntax auf eine Wiederverwendung der ISO\-C\+\+\-Zeigersyntax zu verzichten:  
  
-   Die Verwendung der Zeigersyntax ließ eine direkte Anwendung überladener Operatoren auf ein Verweisobjekt nicht zu;  vielmehr musste der Operator über seinen internen Namen, z. B. `rV1->op_Addition(rV2)`, aufgerufen werden, statt über das intuitivere `rV1+rV2`.  
  
-   Es gibt eine Reihe von Zeigeroperationen, wie Umwandeln und Zeigerarithmetik, die unzulässig sind für Objekte, die auf einem Heap gespeichert sind, der der Garbage Collection unterliegt.  Das Konzept eines Trackinghandles wird der Natur eines CLR\-Referenztyps eher gerecht.  
  
 Die Anwendung eines `__gc`\-Modifizierers auf ein Trackinghandle ist unnötig und wird nicht unterstützt.  Die Verwendung des Objekts selbst wurde nicht geändert; es greift weiterhin durch den Zeigermember\-Auswahloperator \(`->`\) auf Member zu.  So sieht beispielsweise das vorherige Managed Extensions\-Codebeispiel übersetzt in die neue Syntax aus:  
  
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
  
## Dynamische Zuordnung eines Objekts auf dem CLR\-Heap  
 In Managed Extensions war das Vorhandensein von zwei verschiedenen `new`\-Ausdrücken für Zuordnungen zum unverwalteten und verwalteten Heap weitgehend transparent.  In nahezu allen Instanzen ist der Compiler in der Lage, aufgrund des Kontexts zu bestimmen, ob der unverwaltete oder der verwaltete Heap gemeint ist.  Beispiel:  
  
```  
Button *button1 = new Button; // OK: managed heap  
int *pi1 = new int;           // OK: native heap  
Int32 *pi2 = new Int32;       // OK: managed heap  
```  
  
 Wenn keine kontextbezogene Heapzuordnung gewünscht ist, kann der Compiler entweder mit dem `__gc`\-Schlüsselwort oder dem `__nogc`\-Schlüsselwort gesteuert werden.  In der neuen Syntax wird der separaten Natur der beiden neuen Ausdrücke durch die Einführung des `gcnew`\-Schlüsselworts explizit Rechnung getragen.  Zum Beispiel sehen die drei vorherigen Deklarationen in der neuen Syntax wie folgt aus:  
  
```  
Button^ button1 = gcnew Button;        // OK: managed heap  
int * pi1 = new int;                   // OK: native heap  
Int32^ pi2 = gcnew Int32; // OK: managed heap  
```  
  
 Hier ist die Managed Extensions\-Initialisierung der im vorherigen Abschnitt deklarierten `Form1`\-Member:  
  
```  
void InitializeComponent() {  
   components = new System::ComponentModel::Container();  
   button1 = new System::Windows::Forms::Button();  
   myDataGrid = new DataGrid();  
  
   button1->Click +=   
      new System::EventHandler(this, &Form1::button1_Click);  
}  
```  
  
 Hier die gleiche Initialisierung in der neuen Syntax.  Beachten Sie, dass der Hut für den Referenztyp nicht erforderlich ist, wenn es sich um das Ziel eines `gcnew`\-Ausdrucks handelt.  
  
```  
void InitializeComponent() {  
   components = gcnew System::ComponentModel::Container;  
   button1 = gcnew System::Windows::Forms::Button;  
   myDataGrid = gcnew DataGrid;  
  
   button1->Click +=   
      gcnew System::EventHandler( this, &Form1::button1_Click );  
}  
```  
  
## Ein Nachverfolgungsverweis auf kein Objekt  
 In der neuen Syntax stellt `0` nicht mehr eine NULL\-Adresse dar, sondern wird einfach wie eine ganze Zahl behandelt, genau wie `1`, `10` oder `100`.  Deshalb musste ein spezielles Token zur Darstellung eines NULL\-Werts für einen Nachverfolgungsverweis eingeführt werden.  Zum Beispiel initialisieren wir in Managed Extensions einen Referenztyp, der kein Objekt adressiert, wie folgt:  
  
```  
// OK: we set obj to refer to no object  
Object * obj = 0;  
  
// Error: no implicit boxing  
Object * obj2 = 1;  
```  
  
 In der neuen Syntax führt jede Initialisierung oder Zuweisung eines Werttyps zu einem `Object` zu implizitem Boxing dieses Werttyps.  In der neuen Syntax werden `obj` und `obj2` mit adressierten, geschachtelten Int32\-Objekten initialisiert, die den Wert 0 bzw. 1 haben.  Beispiel:  
  
```  
// causes the implicit boxing of both 0 and 1  
Object ^ obj = 0;  
Object ^ obj2 = 1;  
```  
  
 Um die explizite Initialisierung, Wertzuweisung und den Vergleich eines Trackinghandles mit NULL zu ermöglichen, ist das neue `nullptr`\-Schlüsselwort verfügbar.  Die korrekte Überarbeitung des ursprünglichen Beispiels sieht wie folgt aus:  
  
```  
// OK: we set obj to refer to no object  
Object ^ obj = nullptr;  
  
// OK: we initialize obj2 to a Int32^  
Object ^ obj2 = 1;  
```  
  
 Dies erschwert die Portierung von vorhandenem Code in die neue Syntax ein wenig.  Betrachten Sie z. B. die folgende Wertklassendeklaration:  
  
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
  
 Hier handelt es sich sowohl bei `args` als auch bei `env` um CLR\-Referenztypen.  Die Initialisierung dieser beiden Member mit `0` im Konstruktor kann nicht unverändert in die neue Syntax übernommen werden.  Vielmehr muss sie in `nullptr` geändert werden:  
  
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
  
 Ähnlich müssen Prüfungen, in denen diese Member mit `0` verglichen werden, so geändert werden, dass die Member mit `nullptr` verglichen werden.  Dies ist die Managed Extensions\-Syntax:  
  
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
  
 Und hier die Überarbeitung, in der jede `0`\-Instanz durch `nullptr` ersetzt wurde.  \(Das Übersetzungstool kann fast alle Instanzen automatisch transformieren, einschließlich der Verwendung des `NULL`\-Makros.\)  
  
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
  
 Der `nullptr` wird in einen beliebigen Zeiger\- oder Trackinghandletyp konvertiert, jedoch nicht zu einem ganzzahligen Typ erweitert.  Bei der folgenden Reihe von Initialisierungen beispielsweise ist `nullptr` nur als Anfangswert der ersten beiden zulässig.  
  
```  
// OK: we set obj and pstr to refer to no object  
Object^ obj = nullptr;  
char*   pstr = nullptr; // 0 would also work here  
  
// Error: no conversion of nullptr to 0 …  
int ival = nullptr;  
```  
  
 Ähnlich verhält es sich bei einer Reihe von überladenen Methoden:  
  
```  
void f( Object^ ); // (1)  
void f( char* );   // (2)  
void f( int );     // (3)  
```  
  
 Ein Aufruf mit `nullptr`\-Literal, wie der folgende  
  
```  
// Error: ambiguous: matches (1) and (2)  
f(  nullptr );  
```  
  
 ist mehrdeutig, weil `nullptr` sowohl mit einem Trackinghandle als auch mit einem Zeiger übereinstimmt und keiner der beiden Typen Vorrang gegenüber dem anderen hat. \(Diese Situation erfordert eine explizite Umwandlung, um Eindeutigkeit herzustellen.\)  
  
 Ein Aufruf mit `0` entspricht genau Instanz \(3\):  
  
```  
// OK: matches (3)  
f( 0 );  
```  
  
 Der Grund dafür ist, dass `0` eine ganze Zahl ist.  Wäre `f(int)` nicht vorhanden, würde der Aufruf durch eine Standardkonvertierung eindeutig mit `f(char*)` übereinstimmen.  Die Übereinstimmungsregeln räumen einer genauen Übereinstimmung Vorrang gegenüber einer Standardkonvertierung ein.  Wenn keine genaue Übereinstimmung gefunden wird, wird der Standardkonvertierung Vorrang gegenüber implizitem Boxing eines Werttyps eingeräumt.  Daher gibt es keine Mehrdeutigkeit.  
  
## Siehe auch  
 [Verwaltete Typen \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)   
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Handle für Objekt \(^\)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)   
 [nullptr](../windows/nullptr-cpp-component-extensions.md)