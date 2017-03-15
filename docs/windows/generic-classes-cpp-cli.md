---
title: "Generic Classes (C++/CLI)"
ms.custom: na
ms.date: "12/16/2016"
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
  - "classes [C++], generic"
  - "generic classes [C++], about generic classes"
  - "data types [C++], generic"
  - "generic classes"
  - "generics [C++], declaring generic classes"
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
caps.latest.revision: 33
caps.handback.revision: "31"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Classes (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine generische Klasse wird mithilfe der folgenden Form deklariert:  
  
## Syntax  
  
```  
[attributes]  
generic <class-key type-parameter-identifier(s)>  
[constraint-clauses]  
[accessibility-modifiers] ref class identifier  [modifiers]  
[: base-list]   
{  
   class-body  
} [declarators] [;]  
```  
  
## Hinweise  
 In der oben erwähnten Syntax werden die folgenden Begriffe verwendet:  
  
 `attributes` \(optional\)  
 Zusätzliche deklarative Informationen.  Weitere Informationen zu Attributen und Attributklassen, finden Sie Attribute.  
  
 *class\-key*  
 entweder `class` oder `typename`  
  
 *Typparameterbezeichner*,  
 Durch Kommas getrennte Liste von Bezeichnern, die den Namen der Typparameter angeben.  
  
 *EinschränkungKlauseln*  
 Eine Liste \(nicht durch Trennzeichen getrennt\) **where** von Klauseln, die die Einschränkungen für die Typparameter angeben.  Nimmt die Form:  
  
 `where`  *type\-parameter\-identifier*  `:`  *constraint\-list*  `...`  
  
 *EinschränkungListe*  
 *Klasse\-oderSchnittstelle*\[`,`\] *...*  
  
 *BarrierefreiheitModifizierer*  
 Zugriffsmodifizierer für die generische Klasse.  Für [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ist der einzige zulässigen Modifizierer `private`.  Während der Common Language Runtime sind die zulässigen Modifizierer `private` und `public`.  
  
 *Bezeichner \(identifier\)*  
 Der Name der generischen Klasse, jedoch gültigen C\+\+\-Bezeichner.  
  
 *Modifizierer* \(optional\)  
 Zulässige Modifizierereinschließung `sealed` und **abstract**.  
  
 *BasisListe*  
 Eine Liste, die eine Basisklasse und alle implementierten Schnittstellen enthält, so durch Kommas getrennt.  
  
 *KlasseText*  
 Der Text der Klasse, Felder, Memberfunktionen enthalten, z.  
  
 *Deklaratoren*  
 Deklarationen von Variablen dieses Typs.  Zum Beispiel:*Bezeichner*... `^`\[`,` \]  
  
 Sie können generische Klassen wie diese deklarieren \(Beachten Sie, dass das Schlüsselwort **Klasse** möglicherweise anstelle von **typename** verwendet wird\).  In diesem Beispiel sind  `ItemType`, `KeyType` und `ValueType`, die unbekannte Typen am Punkt in dem der Typ angegeben werden.  `HashTable<int, int>` ist ein konstruierter Typ generische Typ `HashTable<KeyType, ValueType>`.  Mehrere verschiedene konstruierten Typen können von einem einzelnen generischen Typ erstellt werden.  Die generischen Typen, die von generischen Klassen erstellt werden, werden wie jedes andere Verweisklassentyp behandelt.  
  
```  
// generic_classes_1.cpp  
// compile with: /clr  
using namespace System;  
generic <typename ItemType>  
ref struct Stack {  
   // ItemType may be used as a type here  
   void Add(ItemType item) {}  
};  
  
generic <typename KeyType, typename ValueType>  
ref class HashTable {};  
  
// The keyword class may be used instead of typename:  
generic <class ListItem>  
ref class List {};  
  
int main() {  
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();  
}  
```  
  
 werden Werttypen \(integrierte Datentypen \(wie `int` oder `double` bzw. benutzerdefinierte Werttypen und Referenztypen\) als generisches Typargument verwendet werden.  Die Syntax in der generischen Definition ist genauso unabhängig.  Syntaktisch wird der unbekannten Typ behandelt, als ob es ein Verweistyp ist.  Es ist die Laufzeit in der Lage zu bestimmen, dass der tatsächlich verwendete Typ ein Werttyp ist und die entsprechenden generierten Code für Zugriff auf den Member zu ersetzen.  Die Werttypen, die als generische Typargumente verwendet werden, werden nicht geschachtelt und deshalb nicht die Leistungseinbußen sind, die mit Boxing zugeordnet ist.  Die Syntax, die im Text von den generischen verwendet, sollte **T^** und '**\-\>**' anstelle von '**.**' sein.  Jede Verwendung von [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) für den Typparameter wird entsprechend von der Laufzeit als die einfache Erstellung eines Werttyps interpretiert, wenn das Typargument ein Werttyp ist.  
  
 Sie können eine generische Klasse mit [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) auf Typen auch deklarieren, die für den Typparameter verwendet werden können.  Im folgenden Beispiel muss jeder Typ, der für `ItemType` verwendet wird, die `IItem`\-Schnittstelle implementieren.  Beim Versuch, eine `int` zu verwenden beispielsweise das `IItem` nicht implementiert, würde einen Kompilierungsfehler verursachen, da das Typargument die Einschränkung nicht erfüllt.  
  
```  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 Generische Klassen im gleichen Namespace nicht überladen werden können, indem nur die Anzahl bzw. Typen über Typparameter ändert.  Wenn jede Klasse in einem anderen Namespace lebt, können sie überladen werden.  Betrachten Sie beispielsweise die folgenden beiden Klassen, `MyClass` und `MyClass<ItemType>`, in den Namespaces `A` und `B`.  Die beiden Klassen können in einem dritten Namespace dann C überladen werden:  
  
```  
// generic_classes_3.cpp  
// compile with: /clr /c  
namespace A {  
   ref class MyClass {};  
}  
  
namespace B {  
   generic <typename ItemType>   
   ref class MyClass2 { };  
}  
  
namespace C {  
   using namespace A;  
   using namespace B;  
  
   ref class Test {  
      static void F() {  
         MyClass^ m1 = gcnew MyClass();   // OK  
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK  
      }  
   };  
}  
```  
  
 Die Basisklasse und die Basisschnittstellen können nicht Typparameter sein.  Basisklasse kann jedoch den Typparameter als Argument, wie in den folgenden Fall einbeziehen:  
  
```  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 Konstruktoren und Destruktoren werden einmal pro Objektinstanz ausgeführt \(wie üblich\); statische Konstruktoren werden einmal für jeden konstruierten Typ ausgeführt.  
  
## Felder in generischen Klassen  
 Dieser Abschnitt wird die Verwendung der Instanz und statischen Feldern in generischen Klassen.  
  
### Instanz\-Variablen  
 Instanzvariablen einer generischen Klasse können Typen und Variableninitialisierung haben, die alle Typparameter aus dem einschließenden Klasse enthalten.  
  
## Beispiel  
 Im folgenden Beispiel werden drei unterschiedliche Instanzen der generischen Klasse, MyClassItemType \<\>, erstellt, indem die entsprechenden Typargumente verwendet \(`int`, **double** und **Zeichenfolge**\).  
  
```  
// generics_instance_fields1.cpp  
// compile with: /clr  
// Instance fields on generic classes  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
// Field of the type ItemType:  
public :  
   ItemType field1;  
   // Constructor using a parameter of the type ItemType:  
   MyClass(ItemType p) {  
     field1 = p;   
   }  
};  
  
int main() {  
   // Instantiate an instance with an integer field:  
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);  
   Console::WriteLine("Integer field = {0}", myObj1->field1);  
  
   // Instantiate an instance with a double field:  
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);  
   Console::WriteLine("Double field = {0}", myObj2->field1);  
  
   // Instantiate an instance with a String field:  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");  
   Console::WriteLine("String field = {0}", myObj3->field1);  
   }  
```  
  
  **Ganzzahliges Feld \= 123**  
**Doppeltes Feld \= 1,23**  
**Zeichenfolge Feld ABC \=**   
## Statische Variablen  
 Auf der Erstellung eines neuen generischen Typs, werden neue Instanzen aller statischen Variablen erstellt und ein statischer Konstruktor für diesen Typ durchgeführt.  
  
 Statische Variablen können alle Typparameter aus dem einschließenden Klasse verwenden.  
  
## Beispiel  
 Im folgenden Beispiel wird mit statischen Feldern und einen statischen Konstruktor innerhalb einer generischen Klasse.  
  
```  
// generics_static2.cpp  
// compile with: /clr  
using namespace System;  
  
interface class ILog {  
   void Write(String^ s);  
};  
  
ref class DateTimeLog : ILog {  
public:  
   virtual void Write(String^ s) {  
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);  
   }  
};  
  
ref class PlainLog : ILog {  
public:  
   virtual void Write(String^ s) { Console::WriteLine(s); }  
};  
  
generic <typename LogType>  
where LogType : ILog  
ref class G {  
   static LogType s_log;  
  
public:  
   G(){}  
   void SetLog(LogType log) { s_log = log; }  
   void F() { s_log->Write("Test1"); }  
   static G() { Console::WriteLine("Static constructor called."); }     
};  
  
int main() {  
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();  
   g1->SetLog(gcnew PlainLog());  
   g1->F();  
  
   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();  
   g2->SetLog(gcnew DateTimeLog());  
  
   // prints date  
   // g2->F();  
}  
```  
  
  **Statischer Konstruktor aufgerufen.**  
**Statischer Konstruktor aufgerufen.**  
**Statischer Konstruktor aufgerufen.**  
**Test1**   
## Methoden in generischen Klassen  
 Methoden in generischen Klassen können generisch sein selbst; nicht generische Methoden werden implizit durch den Klassentypparameter parametrisiert.  
  
 Die folgenden Sonderregelungen gelten auf Methoden in der generischen Klassen zu:  
  
-   Methoden in generischen Klassen können auch Typparameter als Rückgabetypen oder Parameter, lokale Variablen verwenden.  
  
-   Methoden in generischen Klassen können die offenen oder geschlossenen konstruierten Typen als Parameter, Rückgabetypen oder lokale Variablen verwenden.  
  
### Nicht generische Methoden in generischen Klassen  
 Methoden in generischen Klassen, die keine zusätzlichen Typparametern, wird normalerweise, als nicht generisch, obwohl sie implizit von der einschließende generische Klasse parametrisiert werden.  
  
 Die Signatur eine nicht generische Methode kann einen oder mehrere Typparameter der einschließenden Klasse, oder in einem geöffneten konstruierten Typ direkt enthalten.  Beispiel:  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 Der Text solche Methoden kann diese Typparameter auch verwenden.  
  
## Beispiel  
 Das folgende Beispiel deklariert eine nicht generische Methode, `ProtectData`, innerhalb einer generischen Klasse, `MyClass<ItemType>`.  Die Methode verwendet den Klassentypparameter `ItemType` in ihrer Signatur in einem geöffneten konstruierten Typ.  
  
```  
// generics_non_generic_methods1.cpp  
// compile with: /clr  
// Non-generic methods within a generic class.  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
public:  
   String^ name;  
   ItemType data;  
  
   MyClass(ItemType x) {  
      data = x;  
   }  
  
   // Non-generic method using the type parameter:  
   virtual void ProtectData(MyClass<ItemType>^ x) {  
      data = x->data;  
   }  
};  
  
// ItemType defined as String^  
ref class MyMainClass: MyClass<String^> {  
public:  
   // Passing "123.00" to the constructor:  
   MyMainClass(): MyClass<String^>("123.00") {  
      name = "Jeff Smith";   
   }   
  
   virtual void ProtectData(MyClass<String^>^ x) override {  
      x->data = String::Format("${0}**", x->data);  
   }  
  
   static void Main() {  
      MyMainClass^ x1 = gcnew MyMainClass();  
  
      x1->ProtectData(x1);  
      Console::WriteLine("Name: {0}", x1->name);  
      Console::WriteLine("Amount: {0}", x1->data);  
   }  
};  
  
int main() {  
   MyMainClass::Main();  
}  
```  
  
  **Name: Jeff Smith**  
**Menge: $123,00 \*\***   
## Generische Methoden in generischen Klassen  
 Sie können generische Methoden in generischen und nicht generischen Klassen deklarieren.  Beispiel:  
  
## Beispiel  
  
```  
// generics_method2.cpp  
// compile with: /clr /c  
generic <typename Type1>  
ref class G {  
public:  
   // Generic method having a type parameter  
   // from the class, Type1, and its own type  
   // parameter, Type2  
   generic <typename Type2>  
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }  
  
   // Non-generic method:  
   // Can use the class type param, Type1, but not Type2.  
   void Method2(Type1 t1) { F(t1, t1); }  
  
   void F(Object^ o1, Object^ o2) {}  
};  
```  
  
 Die nicht generische Methode ist insofern noch generisch, dass sie durch den Typparameter der Klasse parametrisiert ist, enthält jedoch keine zusätzlichen Typparameter.  
  
 Alle Typen Methoden in generischen Klassen können generisch sein, u, statisches Instanz und virtuelle Methoden.  
  
## Beispiel  
 Im folgenden Beispiel wird das Deklarieren und Verwenden von generischen Methoden in der generischen Klassen:  
  
```  
// generics_generic_method2.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class MyClass {  
public:  
   // Declare a generic method member.  
   generic <class Type1>  
   String^ MyMethod(ItemType item, Type1 t) {  
      return String::Concat(item->ToString(), t->ToString());  
   }  
};  
  
int main() {  
   // Create instances using different types.  
   MyClass<int>^ myObj1 = gcnew MyClass<int>();  
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();  
  
   // Calling MyMethod using two integers.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj1->MyMethod<int>(1, 2));  
  
   // Calling MyMethod using an integer and a string.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj2->MyMethod<int>("Hello #", 1));  
  
   // Calling MyMethod using two strings.  
   Console::WriteLine("MyMethod returned: {0}",  
       myObj3->MyMethod<String^>("Hello ", "World!"));  
  
   // generic methods can be called without specifying type arguments  
   myObj1->MyMethod<int>(1, 2);  
   myObj2->MyMethod<int>("Hello #", 1);  
   myObj3->MyMethod<String^>("Hello ", "World!");  
}  
```  
  
  **MyMethod DataGridView\-Elements zurück: 12**  
**MyMethod DataGridView\-Elements zurück: Hello Nr.**  
**MyMethod DataGridView\-Elements zurück: Hallo Welt\!**   
## Verwenden geschachtelter Typen in generischen Klassen  
 Wie mit gewöhnlichen Klassen können Sie andere Typen innerhalb einer generischen Klasse deklarieren.  Die Deklaration der geschachtelten Klasse wird implizit von der Typparameter der äußeren Klassendeklaration parametrisiert.  Folglich wird eine bestimmte geschachtelte Klasse für jeden erstellten äußeren Typ definiert.  In der Deklaration,  
  
```  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 Der Typ \<\>Outerint::Inner ist nicht der gleiche wie der Typ\<\>Outerdouble::Inner.  
  
 Wie mit generischen Methoden in generischen Klassen, können zusätzliche Typparameter für den geschachtelten Typ definiert sind.  Wenn Sie dieselben Typparameternamen in der inneren und äußeren Klasse verwenden, wird der innere Typparameter den äußeren Typparameter aus.  
  
```  
// generic_classes_6.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref class Outer {  
   ItemType outer_item;   // refers to outer ItemType  
  
   generic <typename ItemType>  
   ref class Inner {  
      ItemType inner_item;   // refers to Inner ItemType  
   };  
};  
```  
  
 Da es keine Möglichkeit gibt, den äußeren Typparameter zuzugreifen, generiert der Compiler eine Warnung in dieser Situation.  
  
 Wenn geschachtelte erstellte generische Typen verfügt, wird der Typparameter für den äußeren Typ nicht in der Typparameterliste für den internen Typ enthalten, obwohl der innere Typ implizit durch den Typparameter des äußeren Typs parametrisiert wird.  Im obigen Fall würde ein Name eines generischen Typs Outerint::Innerstring \<\>sein\<\>.  
  
 Im folgenden Beispiel wird das Erstellen und Lesen einer verknüpften Liste mit geschachtelten Typen in generischen Klassen.  
  
## Beispiel  
  
```  
// generics_linked_list.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class LinkedList {  
// The node class:  
public:  
   ref class Node {  
   // The link field:  
   public:  
      Node^ next;  
      // The data field:  
      ItemType item;   
   } ^first, ^current;  
};  
  
ref class ListBuilder {  
public:  
   void BuildIt(LinkedList<double>^ list) {  
      /* Build the list */  
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};  
      Console::WriteLine("Building the list:");  
  
      for (int n=0; n<=4; n++) {  
         // Create a new node:  
         list->current = gcnew LinkedList<double>::Node();  
  
         // Assign a value to the data field:  
         list->current->item = m[n];  
  
         // Set the link field "next" to be the same as   
         // the "first" field:  
         list->current->next = list->first;  
  
         // Redirect "first" to the new node:  
         list->first = list->current;  
  
         // Display node's data as it builds:  
         Console::WriteLine(list->current->item);  
      }  
   }  
  
   void ReadIt(LinkedList<double>^ list) {  
      // Read the list  
      // Make "first" the "current" link field:  
      list->current = list->first;  
      Console::WriteLine("Reading nodes:");  
  
      // Read nodes until current == null:  
      while (list->current != nullptr) {  
         // Display the node's data field:  
         Console::WriteLine(list->current->item);  
  
         // Move to the next node:  
         list->current = list->current->next;  
      }  
   }  
};  
  
int main() {  
   // Create a list:  
   LinkedList<double>^ aList = gcnew LinkedList<double>();  
  
   // Initialize first node:  
   aList->first = nullptr;  
  
   // Instantiate the class, build, and read the list:   
   ListBuilder^ myListBuilder = gcnew ListBuilder();  
   myListBuilder->BuildIt(aList);  
   myListBuilder->ReadIt(aList);  
}  
```  
  
  **Erstellen der Liste:**  
**0.1**  
**0.2**  
**0.3**  
**0.4**  
**0.5**  
**Lesenknoten:**  
**0.5**  
**0.4**  
**0.3**  
**0.2**  
**0.1**   
## Eigenschaften, Indexer und Ereignisse, Operatoren in generischen Klassen  
  
-   Eigenschaften, Indexer und Ereignisse, Operatoren können die Typparameter der einschließenden generischen Klasse als Rückgabewerte, Parameter oder lokalen Variablen, wie verwenden, wenn `ItemType` ein Typparameter einer Klasse ist:  
  
    ```  
    public ItemType MyProperty {}  
    ```  
  
-   Eigenschaften, Indexer und Ereignisse, Operatoren können nicht selbst parametrisiert werden.  
  
## Beispiel  
 Dieses Beispiel zeigt Deklarationen eine Instanzeigenschaft innerhalb einer generischen Klasse veranschaulicht.  
  
```  
// generics_generic_properties1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
private:  
   property ItemType myField;  
  
public:  
   property ItemType MyProperty {  
      ItemType get() {  
         return myField;   
      }  
      void set(ItemType value) {  
         myField = value;  
      }  
   }  
};  
  
int main() {  
   MyClass<String^>^ c = gcnew MyClass<String^>();  
   MyClass<int>^ c1 = gcnew MyClass<int>();  
  
   c->MyProperty = "John";  
   c1->MyProperty = 234;  
  
   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);  
}  
```  
  
  **John, 234**   
## Beispiel  
 Im folgenden Beispiel wird eine generische Klasse mit einem Ereignis.  
  
```  
// generics_generic_with_event.cpp  
// compile with: /clr  
// Declare a generic class with an event and  
// invoke events.  
using namespace System;  
  
// declare delegates  
generic <typename ItemType>  
delegate void ClickEventHandler(ItemType);  
  
// generic class that defines events  
generic <typename ItemType>  
ref class EventSource {  
public:  
   // declare the event OnClick  
   event ClickEventHandler<ItemType>^ OnClick;   
   void FireEvents(ItemType item) {  
      // raises events  
      OnClick(item);  
   }  
};  
  
// generic class that defines methods that will called when  
// event occurs  
generic <typename ItemType>  
ref class EventReceiver {  
public:  
   void OnMyClick(ItemType item) {  
     Console::WriteLine("OnClick: {0}", item);  
   }  
};  
  
int main() {  
   EventSource<String^>^ MyEventSourceString =  
                   gcnew EventSource<String^>();  
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();  
   EventReceiver<String^>^ MyEventReceiverString =  
                   gcnew EventReceiver<String^>();  
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();  
  
   // hook handler to event  
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(  
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(  
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
  
   // invoke events  
   MyEventSourceString->FireEvents("Hello");  
   MyEventSourceInt->FireEvents(112);  
  
   // unhook handler to event  
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(  
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(  
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
}  
```  
  
## Generische Strukturen  
 Die Regeln für das Deklarieren und Verwenden von generischen Strukturen sind identisch mit denen für generische Klassen, abgesehen von den Unterschieden, die in der Visual C\+\+\-Sprachreferenz erwähnt werden.  
  
## Beispiel  
 Das folgende Beispiel deklariert eine generische Struktur, `MyGenStruct`, mit einem Feld, `myField` und weist Werte verschiedener Typen \(`int`, **double**, **String^**\) für dieses Feld zu.  
  
```  
// generics_generic_struct1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref struct MyGenStruct {  
public:  
   ItemType myField;  
  
   ItemType AssignValue(ItemType item) {  
      myField = item;  
      return myField;  
   }  
};  
  
int main() {  
   int myInt = 123;  
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();  
   myIntObj->AssignValue(myInt);  
   Console::WriteLine("The field is assigned the integer value: {0}",  
            myIntObj->myField);  
  
   double myDouble = 0.123;  
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();  
   myDoubleObj->AssignValue(myDouble);  
   Console::WriteLine("The field is assigned the double value: {0}",  
            myDoubleObj->myField);  
  
   String^ myString = "Hello Generics!";  
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();  
   myStringObj->AssignValue(myString);  
   Console::WriteLine("The field is assigned the string: {0}",  
            myStringObj->myField);  
}  
```  
  
  **Das Feld wird der Ganzzahlwert zugewiesen: 123**  
**Das Feld wird den double\-Wert zugewiesen: 0,123**  
**Das Feld wird die Zeichenfolge zugewiesen: Hello\! Generika**   
## Siehe auch  
 [Generics](../windows/generics-cpp-component-extensions.md)