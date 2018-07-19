---
title: Generische Klassen (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [C++], generic
- generic classes [C++], about generic classes
- data types [C++], generic
- generic classes
- generics [C++], declaring generic classes
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07a5cb6abaca56901af26895b1304a9b7079ced9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881399"
---
# <a name="generic-classes-ccli"></a>Generische Klassen (C++/CLI)
Eine generische Klasse wird im folgenden Format deklariert:  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="remarks"></a>Hinweise  
 In der oben aufgeführten Syntax werden die folgenden Begriffe verwendet:  
  
 `attributes` (optional)  
 Zusätzliche deklarative Informationen. Weitere Informationen zu Attributen und Attributklassen finden Sie unter "Attribute".  
  
 *Klassenschlüssel*  
 Entweder `class` oder `typename`  
  
 *Type-Parameter-Bezeichner*,  
 Durch Trennzeichen getrennte Liste von Bezeichnern, die die Namen der Typparameter angeben.  
  
 *Einschränkungsklauseln*  
 Eine Liste (nicht durch Trennzeichen getrennt) der **, in denen** Klauseln, die die Einschränkungen für die Typparameter angeben. Hat das Format an:  
  
 `where`  *Typ der Parameterbezeichner*`:`*Einschränkungsliste*   `...`  
  
 *Liste der Einschränkung*  
 *Klasse oder Schnittstelle*[`,` *...* ]  
  
 *Zugriffsmodifizierer*  
 Der Zugriffsmodifizierer für die generische Klasse. Für die Windows-Runtime ist die einzige zulässige Modifizierer `private`. Für die common Language Runtime die zulässige Modifizierer sind `private` und `public`.  
  
 *identifier*  
 Der Name der generischen Klasse, eine beliebige gültige C++-Bezeichner.  
  
 *Modifizierer* (optional)  
 Zulässige Modifizierer sind `sealed` und **abstrakte**.  
  
 *Base-list*  
 Eine Liste mit einer Basisklasse und allen implementierten Schnittstellen, die alle durch Kommas getrennt.  
  
 *Klasse zum Textteil gehöriger*  
 Der Text der Klasse, die Felder, Memberfunktionen usw. enthält.  
  
 *Deklaratoren*  
 Deklarationen von Variablen dieses Typs. Zum Beispiel: `^` *Bezeichner*[`,` ...]  
  
 Sie können generische Klassen, wie diese deklarieren (Beachten Sie, dass das Schlüsselwort **Klasse** kann verwendet werden, anstelle von **Typename**). In diesem Beispiel `ItemType`, `KeyType` und `ValueType` sind die unbekannte Typen, die an dem Punkt angegeben sind, in denen der Typ. `HashTable<int, int>` wird von ein konstruierter Typ des generischen Typs `HashTable<KeyType, ValueType>`. Eine Anzahl von verschiedenen konstruierte Typen kann aus eines einzelnen generischen Typs erstellt werden. Konstruierte Typen, die von generischen Klassen erstellt werden wie andere Typ des Ref-Klasse behandelt.  
  
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
  
 Beide Werttypen (entweder integrierte Typen wie `int` oder `double`, oder eine benutzerdefinierte Werttypen) und Verweistypen als generisches Typargument verwendet werden können. Die Syntax in der generischen Methodendefinition entspricht dem unabhängig. Der unbekannte Typ ist syntaktisch, behandelt, als handele es sich um einen Referenztyp darstellt. Allerdings kann die Common Language Runtime zu bestimmen, wenn der tatsächlich verwendete Datentyp ein Werttyp ist, und ersetzen den entsprechenden generierten Code für den direkten Zugriff auf Member. Form von generischen Typargumenten verwendete Werttypen nicht geschachtelt sind und daher die Leistungseinbuße Boxing nicht beeinträchtigt. Muss innerhalb des Texts der generischen verwendete Syntax **T ^** und "**->**"anstelle von"**.**". Alle Verwendungen von [Ref neue Gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) für den Typ Parameter werden entsprechend interpretiert, von der Laufzeit als die einfache Erstellung eines Werttyps Wenn das Typargument ein Werttyp ist.  
  
 Sie können auch mit eine generische Klasse deklarieren [Einschränkungen für generische Typparameter (C + c++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) auf die Typen, die für den Typparameter verwendet werden können. Im folgenden Beispiel verwendet einen beliebigen Typ für `ItemType` implementieren müssen die `IItem` Schnittstelle. Bei dem Versuch, verwenden Sie `int`, z. B. die nicht implementiert `IItem`, wäre ein Kompilierzeitfehler, da das Typargument nicht der Einschränkung entspricht.  
  
```  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 Generische Klassen im selben Namespace können nicht überladen werden, indem Sie nur ändern, die Anzahl oder die Datentypen der Typparameter. Jedoch wenn jede Klasse in einem anderen Namespace befindet, können sie überladen werden. Angenommen, Sie haben die folgenden zwei Klassen `MyClass` und `MyClass<ItemType>`, in den Namespaces `A` und `B`. Die beiden Klassen können dann in einem dritten Namespace "c:" überladen werden  
  
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
  
 Die Basisklasse und Basisschnittstellen darf nicht Typparameter sein. Allerdings kann die Basisklasse den Typparameter als Argument, wie im folgenden Fall umfassen:  
  
```  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 Konstruktoren und Destruktoren werden einmal für jede Objektinstanz (wie gewohnt;) ausgeführt statische Konstruktoren werden einmal für jeden konstruierten Typ ausgeführt.  
  
## <a name="fields-in-generic-classes"></a>Felder im generische Klassen  
 Dieser Abschnitt zeigt die Verwendung der Instanz und statische Felder in generischen Klassen.  
  
### <a name="instance-variables"></a>Nachrichteninstanzvariablen  
 Nachrichteninstanzvariablen einer generischen Klasse möglich, Typen und Variable Initialisierer, die Typparameter von einschließenden Klasse enthalten.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die drei verschiedene Instanzen der generischen Klasse, MyClass\<ItemType >, werden mithilfe der entsprechenden Typargumente erstellt (`int`, **doppelte**, und **Zeichenfolge**).  
  
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
  
```Output  
Integer field = 123  
Double field = 1.23  
String field = ABC  
```  
  
## <a name="static-variables"></a>Statische Variablen  
 Bei der Erstellung eines neuen generischen Typs neue Instanzen von statischen Variablen werden erstellt, und für diesen Typ statischer Konstruktor ausgeführt wird.  
  
 Statische Variablen können die Typparameter von einschließenden Klasse.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird die Verwendung von statische Felder und ein statischer Konstruktor innerhalb einer generischen Klasse veranschaulicht.  
  
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
  
```Output  
Static constructor called.  
Static constructor called.  
Static constructor called.  
Test1  
```  
  
## <a name="methods-in-generic-classes"></a>Methoden in generische Klassen  
 Methoden in generischen Klassen können generisch sein selbst; nicht generische Methoden werden implizit durch die Klassentypparameter parametrisiert werden.  
  
 Die folgenden speziellen Regeln gelten für Methoden innerhalb von generischen Klassen:  
  
-   Methoden in generischen Klassen können als Parameter, lokale Variablen oder Rückgabetypen Typparameter verwenden.  
  
-   Methoden in generischen Klassen können offene oder geschlossene konstruierte Typen als Parameter, lokale Variablen oder Rückgabetypen.  
  
### <a name="non-generic-methods-in-generic-classes"></a>Nicht generische Methoden in generische Klassen  
 Methoden in generischen Klassen, die keine zusätzliche Typparameter werden in der Regel als nichtgenerischen bezeichnet, obwohl sie implizit von der einschließenden generischen Klasse parametrisiert werden.  
  
 Die Signatur einer nicht generischen Methode kann eine oder mehrere Typparameter von einschließenden Klasse entweder direkt oder indirekt in offenen konstruierte Typen enthalten. Zum Beispiel:  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 Der Text der solche Methoden kann auch diese Typparameter verwenden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine nicht generische Methode `ProtectData`, innerhalb einer generischen Klasse `MyClass<ItemType>`. Die Methode verwendet den Typparameter der Klasse `ItemType` in der Signatur in offenen konstruierten Typen.  
  
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
  
```Output  
Name: Jeff Smith  
Amount: $123.00**  
```  
  
## <a name="generic-methods-in-generic-classes"></a>Generische Methoden in generische Klassen  
 Sie können generische Methoden in generischen und nicht generischen Klassen deklarieren. Zum Beispiel:  
  
## <a name="example"></a>Beispiel  
  
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
  
 Die nicht generische Methode ist weiterhin generisch ist, in dem Sinne, dass es durch die Klasse Typparameter parametrisiert ist, verfügt aber über keine zusätzlichen Typparameter.  
  
 Alle Arten von Methoden in generischen Klassen können generische, einschließlich statischen, Instanz und virtuelle Methoden sein.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, deklarieren und Verwenden von generischen Methoden innerhalb von generischen Klassen:  
  
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
  
```Output  
MyMethod returned: 12  
MyMethod returned: Hello #1  
MyMethod returned: Hello World!  
```  
  
## <a name="using-nested-types-in-generic-classes"></a>Verwenden von geschachtelten Typen in generische Klassen  
 Ebenso wie bei normalen Klassen können Sie andere Typen innerhalb einer generischen Klasse deklarieren. Die Deklaration der geschachtelten Klasse wird implizit durch die Typparameter der Deklaration der äußeren Klasse parametrisiert. Daher wird eine unterschiedliche geschachtelte Klasse für jede äußere konstruierten Typ definiert. Beispielsweise ist in der Deklaration  
  
```  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 Der äußere Typ\<Int >:: innere ist nicht identisch mit der äußere Typ\<doppelte >:: inneren.  
  
 Wie bei generischen Methoden in generischen Klassen können weitere Typparameter für den geschachtelten Typ definiert werden. Wenn Sie die gleichen Typparameternamen in der inneren und äußeren Klasse verwenden, wird der innere Typparameter den Typparameter des äußeren ausblenden.  
  
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
  
 Da es keine Möglichkeit zum Verweisen auf den äußeren Typparameter angeben gibt, erzeugt der Compiler eine Warnung in dieser Situation.  
  
 Wenn konstruierte geschachtelte generische Typen identisch sind, ist der Typparameter des äußeren Typs, obwohl der innere Typ implizit durch die Typparameter des äußeren Typs parametrisiert ist nicht in der Typparameterliste für den inneren Typ enthalten. Im obigen Beispiel wäre ein Name eines konstruierten Typs Outer\<Int >:: innere\<Zeichenfolge >.  
  
 Im folgende Beispiel wird veranschaulicht, erstellen und lesen eine verknüpfte Liste mit geschachtelten Typen in generischen Klassen.  
  
## <a name="example"></a>Beispiel  
  
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
  
```Output  
Building the list:  
0.1  
0.2  
0.3  
0.4  
0.5  
Reading nodes:  
0.5  
0.4  
0.3  
0.2  
0.1  
```  
  
## <a name="properties-events-indexers-and-operators-in-generic-classes"></a>Eigenschaften, Ereignisse, Indexer und Operatoren in generische Klassen  
  
-   Eigenschaften, Ereignisse, Indexer und Operatoren können die Typparameter von einschließenden generischen Klasse als Rückgabewerte, Parameter oder lokalen Variablen, z. B. wenn `ItemType` ist ein Typparameter von einer Klasse:  
  
    ```  
    public ItemType MyProperty {}  
    ```  
  
-   Eigenschaften, Ereignisse, Indexer und Operatoren können nicht sich selbst nicht parametrisiert werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Deklarationen von einer Instanzeigenschaft innerhalb einer generischen Klasse.  
  
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
  
```Output  
John, 234  
```  
  
## <a name="example"></a>Beispiel  
 Das nächste Beispiel zeigt eine generische Klasse mit einem Ereignis.  
  
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
  
## <a name="generic-structs"></a>Generische Strukturen  
 Die Regeln zum Deklarieren und Verwenden von generischen Strukturen sind identisch für generische Klassen, mit Ausnahme der Unterschiede in der Visual C++-Sprachreferenz in notiert haben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine generische Struktur `MyGenStruct`, mit einem Feld `myField`, und weist die Werte verschiedener Typen (`int`, **doppelte**, **String ^**) auf dieses Feld.  
  
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
  
```Output  
The field is assigned the integer value: 123  
The field is assigned the double value: 0.123  
The field is assigned the string: Hello Generics!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Generika](../windows/generics-cpp-component-extensions.md)