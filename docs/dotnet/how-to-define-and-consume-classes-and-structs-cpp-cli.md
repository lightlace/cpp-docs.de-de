---
title: 'Vorgehensweise: definieren und Verarbeiten von Klassen und Strukturen (C + c++ / CLI) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- structs [C++]
- classes [C++], instantiating
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a0a276854c9f2e27439c2c16e9299d4eaa9243d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-define-and-consume-classes-and-structs-ccli"></a>Gewusst wie: Definieren und Verarbeiten von Klassen und Strukturen (C++/CLI)
In diesem Artikel wird gezeigt, wie zum Definieren und Verarbeiten von benutzerdefinierten Verweistypen und Werttypen in C + c++ / CLI.  
  
##  <a name="BKMK_Contents"></a> Inhalt  
 [Objektinstanziierung](#BKMK_Object_instantiation)  
  
 [Implizit abstrakte Klassen](#BKMK_Implicitly_abstract_classes)  
  
 [Typsichtbarkeit](#BKMK_Type_visibility)  
  
 [Membersichtbarkeit](#BKMK_Member_visibility)  
  
 [Öffentliche und private systemeigene Klassen](#BKMK_Public_and_private_native_classes)  
  
 [Statische Konstruktoren](#BKMK_Static_constructors)  
  
 [Semantik dieses Zeigers](#BKMK_Semantics_of_the_this_pointer)  
  
 [Ausblenden nach Signatur verdeckte Funktionen](#BKMK_Hide_by_signature_functions)  
  
 [Kopierkonstruktoren](#BKMK_Copy_constructors)  
  
 [Destruktoren und Finalizer](#BKMK_Destructors_and_finalizers)  
  
##  <a name="BKMK_Object_instantiation"></a>Objektinstanziierung  
 Referenztypen (ref) und Werttypen können nur auf dem verwalteten Heap instanziiert werden, jedoch nicht auf dem Stapel oder auf dem nativen Heap.  
  
```  
// mcppv2_ref_class2.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
  
   // nested class  
   ref class MyClass2 {  
   public:  
      int i;  
   };  
  
   // nested interface  
   interface struct MyInterface {  
      void f();  
   };  
};  
  
ref class MyClass2 : public MyClass::MyInterface {  
public:  
   virtual void f() {  
      System::Console::WriteLine("test");  
   }  
};  
  
public value struct MyStruct {  
   void f() {  
      System::Console::WriteLine("test");  
   }     
};  
  
int main() {  
   // instantiate ref type on garbage-collected heap  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass -> i = 4;  
  
   // instantiate value type on garbage-collected heap  
   MyStruct ^ p_MyStruct = gcnew MyStruct;  
   p_MyStruct -> f();  
  
   // instantiate value type on the stack  
   MyStruct p_MyStruct2;  
   p_MyStruct2.f();  
  
   // instantiate nested ref type on garbage-collected heap  
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;  
   p_MyClass2 -> i = 5;  
}  
```  
  
##  <a name="BKMK_Implicitly_abstract_classes"></a>Implizit abstrakte Klassen  
 Ein *implizit abstrakte Klasse* kann nicht instanziiert werden. Eine Klasse ist implizit abstrakt, wenn der Basistyp der Klasse eine Schnittstelle ist und die Klasse nicht alle Memberfunktionen der Schnittstelle implementiert.  
  
 Wenn Objekte nicht aus einer Klasse erstellt werden können, die von einer Schnittstelle abgeleitet sind, könnte dies daran liegen, dass die Klasse implizit abstrakt ist. Weitere Informationen zu abstrakten Klassen finden Sie unter [abstrakte](../windows/abstract-cpp-component-extensions.md).  
  
 Das folgende Codebeispiel zeigt, dass die `MyClass`-Klasse nicht instanziiert werden kann, da die `MyClass::func2`-Funktion nicht implementiert ist. Damit das Beispiel kompiliert werden kann, heben Sie die Auskommentierung der `MyClass::func2`-Funktion auf.  
  
```  
// mcppv2_ref_class5.cpp  
// compile with: /clr  
interface struct MyInterface {  
   void func1();  
   void func2();  
};  
  
ref class MyClass : public MyInterface {  
public:  
   void func1(){}  
   // void func2(){}  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259   
                                          // To resolve, uncomment MyClass::func2.  
}  
```  
  
##  <a name="BKMK_Type_visibility"></a>Typsichtbarkeit  
 Sie können die Sichtbarkeit von CLR-Typen (Common Language Runtime) so steuern, dass bei Verweis auf eine Assembly die Typen in der Assembly sichtbar oder außerhalb der Assembly nicht sichtbar sein können.  
  
 `public`Gibt an, dass ein Typ für jede Quelldatei sichtbar ist, enthält eine `#using` Richtlinie für die Assembly, die den Typ enthält.  `private`Gibt an, dass ein Typ nicht für Quelldateien sichtbar ist, enthalten eine `#using` Richtlinie für die Assembly, die den Typ enthält. Allerdings sind private Typen in der gleichen Assembly sichtbar. Standardmäßig ist die Sichtbarkeit für eine Klasse auf `private` eingestellt.  
  
 Vor Visual C++ 2005 unterstützten systemeigene Typen außerhalb der Assembly standardmäßig öffentliche Zugriffe. Aktivieren Sie [Compilerwarnung (Stufe 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) können Sie sehen, in dem private systemeigene Typen nicht ordnungsgemäß verwendet werden. Verwenden der [Make_public](../preprocessor/make-public.md) Pragma zu öffentlichen Zugriff auf einen systemeigenen Typ in einer Quellcodedatei, die Sie nicht ändern können.  
  
 Weitere Informationen finden Sie unter [#using-Direktive](../preprocessor/hash-using-directive-cpp.md).  
  
 Das folgende Beispiel zeigt, wie Typen deklariert und ihr Zugriff angegeben werden können und wie dann in der Assembly auf diese Typen zugegriffen werden kann. Wenn auf eine Assembly, die private Typen enthält, mithilfe von `#using` verwiesen wird, sind nur öffentliche Typen in der Assembly sichtbar.  
  
```  
// type_visibility.cpp  
// compile with: /clr  
using namespace System;  
// public type, visible inside and outside assembly  
public ref struct Public_Class {  
   void Test(){Console::WriteLine("in Public_Class");}  
};  
  
// private type, visible inside but not outside assembly  
private ref struct Private_Class {  
   void Test(){Console::WriteLine("in Private_Class");}  
};  
  
// default accessibility is private  
ref class Private_Class_2 {  
public:  
   void Test(){Console::WriteLine("in Private_Class_2");}  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   a->Test();  
  
   Private_Class ^ b = gcnew Private_Class;  
   b->Test();  
  
   Private_Class_2 ^ c = gcnew Private_Class_2;  
   c->Test();  
}  
```  
  
 **Ausgabe**  
  
```Output  
in Public_Class  
in Private_Class  
in Private_Class_2  
```  
  
 Nun kann das vorherige Beispiel umgeschrieben werden, damit es als DLL erstellt wird.  
  
```  
// type_visibility_2.cpp  
// compile with: /clr /LD  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref struct Public_Class {  
   void Test(){Console::WriteLine("in Public_Class");}  
};  
  
// private type, visible inside but not outside the assembly  
private ref struct Private_Class {  
   void Test(){Console::WriteLine("in Private_Class");}  
};  
  
// by default, accessibility is private  
ref class Private_Class_2 {  
public:  
   void Test(){Console::WriteLine("in Private_Class_2");}  
};  
```  
  
 Im folgenden Beispiel wird der Zugriff auf Typen außerhalb der Assembly veranschaulicht. In diesem Beispiel verwendet der Client die Komponente, die im vorherigen Beispiel erstellt wurde.  
  
```  
// type_visibility_3.cpp  
// compile with: /clr  
#using "type_visibility_2.dll"  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   a->Test();  
  
   // private types not accessible outside the assembly  
   // Private_Class ^ b = gcnew Private_Class;  
   // Private_Class_2 ^ c = gcnew Private_Class_2;  
}  
```  
  
 **Ausgabe**  
  
```Output  
in Public_Class  
```  
  
##  <a name="BKMK_Member_visibility"></a>Membersichtbarkeit  
 Sie können den Zugriff auf einen Member einer öffentlichen Klasse aus derselben Assembly unterschiedlich gestalten als den Zugriff darauf von außerhalb der Assembly. Verwenden Sie hierzu Paare der `public`-, `protected`- und `private`-Zugriffsspezifizierer.  
  
 In dieser Tabelle werden die Auswirkungen der unterschiedlichen Zugriffsspezifizierer zusammengefasst:  
  
|Bezeichner|Effekt|  
|---------------|------------|  
|public|Auf den Member kann innerhalb und außerhalb der Assembly leicht zugegriffen werden.  Finden Sie unter [öffentlichen](../cpp/public-cpp.md) für Weitere Informationen.|  
|private|Auf den Member kann weder innerhalb noch außerhalb der Assembly zugegriffen werden.  Finden Sie unter [private](../cpp/private-cpp.md) für Weitere Informationen.|  
|protected|Auf den Member kann innerhalb und außerhalb der Assembly zugegriffen werden. Dies gilt jedoch nur für abgeleitete Typen.  Finden Sie unter [geschützt](../cpp/protected-cpp.md) für Weitere Informationen.|  
|internal|Der Member ist öffentlich innerhalb der Assembly und privat außerhalb der Assembly.  `internal` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).|  
|Öffentliche geschützten- +/-geschützten öffentlichen|Der Member ist öffentlich innerhalb der Assembly und geschützt außerhalb der Assembly.|  
|Private geschützte- +/-geschützten privaten|Der Member ist geschützt innerhalb der Assembly und privat außerhalb der Assembly.|  
  
 Das folgende Beispiel zeigt einen öffentlichen Typ, der Member enthält, die mit verschiedenen Barrierefreiheiten deklariert wurden, und veranschaulicht dann den Zugriff auf diese Member aus der Assembly heraus.  
  
```  
  
// compile with: /clr  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref class Public_Class {  
public:  
   void Public_Function(){System::Console::WriteLine("in Public_Function");}  
  
private:  
   void Private_Function(){System::Console::WriteLine("in Private_Function");}  
  
protected:  
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}  
  
internal:  
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}  
  
protected public:  
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}  
  
public protected:  
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}  
  
private protected:  
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}  
  
protected private:  
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}  
};  
  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Private_Function();  
      Private_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   MyClass ^ b = gcnew MyClass;  
   a->Public_Function();  
   a->Protected_Public_Function();  
   a->Public_Protected_Function();  
  
   // accessible inside but not outside the assembly  
   a->Internal_Function();  
  
   // call protected functions  
   b->Test();  
  
   // not accessible inside or outside the assembly  
   // a->Private_Function();  
}  
```  
  
 **Ausgabe**  
  
```Output  
in Public_Function  
in Protected_Public_Function  
in Public_Protected_Function  
in Internal_Function  
=======================  
in function of derived class  
in Protected_Function  
in Protected_Private_Function  
in Private_Protected_Function  
exiting function of derived class  
=======================  
```  
  
 Nun kann das vorherige Beispiel als DLL erstellt werden.  
  
```  
  
// compile with: /clr /LD  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref class Public_Class {  
public:  
   void Public_Function(){System::Console::WriteLine("in Public_Function");}  
  
private:  
   void Private_Function(){System::Console::WriteLine("in Private_Function");}  
  
protected:  
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}  
  
internal:  
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}  
  
protected public:  
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}  
  
public protected:  
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}  
  
private protected:  
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}  
  
protected private:  
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}  
};  
  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Private_Function();  
      Private_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
```  
  
 Im folgenden Beispiel wird die im vorherigen Beispiel erstellte Komponente verwendet und dadurch der Zugriff auf Member von außerhalb der Assembly veranschaulicht.  
  
```  
  
// compile with: /clr  
#using "type_member_visibility_2.dll"  
using namespace System;  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Public_Function();  
      Public_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   MyClass ^ b = gcnew MyClass;  
   a->Public_Function();  
  
   // call protected functions  
   b->Test();  
  
   // can't be called outside the assembly  
   // a->Private_Function();  
   // a->Internal_Function();     
   // a->Protected_Private_Function();  
   // a->Private_Protected_Function();  
}  
```  
  
 **Ausgabe**  
  
```Output  
in Public_Function  
=======================  
in function of derived class  
in Protected_Function  
in Protected_Public_Function  
in Public_Protected_Function  
exiting function of derived class  
=======================  
```  
  
##  <a name="BKMK_Public_and_private_native_classes"></a>Öffentliche und private systemeigene Klassen  
 Ein systemeigener Typ kann von einem verwalteten Typ referenziert werden.  Beispielsweise kann eine Funktion in einem verwalteten Typ einen Parameter aufnehmen, dessen Typ eine systemeigene Struktur ist.  Wenn der verwaltete Typ und die verwaltete Funktion in einer Assembly öffentlich sind, muss der systemeigene Typ ebenfalls öffentlich sein.  
  
```  
  
// native type  
public struct N {  
   N(){}  
   int i;  
};  
```  
  
 Anschließend erstellen Sie die Quellcodedatei, die den systemeigenen Typ verwendet:  
  
```  
  
// compile with: /clr /LD  
#include "mcppv2_ref_class3.h"  
// public managed type  
public ref struct R {  
   // public function that takes a native type  
   void f(N nn) {}  
};  
```  
  
 Kompilieren Sie nun einen Client:  
  
```  
  
// compile with: /clr  
#using "mcppv2_ref_class3.dll"  
  
#include "mcppv2_ref_class3.h"  
  
int main() {  
   R ^r = gcnew R;  
   N n;  
   r->f(n);  
}  
```  
  
##  <a name="BKMK_Static_constructors"></a> Statische Konstruktoren  
 Ein CLR-Typ, z. B. eine Klasse oder Struktur, kann einen statischen Konstruktor enthalten, der zum Initialisieren von statischen Datenmembern verwendet werden kann.  Ein statischer Konstruktor wird höchstens einmal aufgerufen. Der Aufruf erfolgt, bevor auf einen statischen Member des Typs zum ersten Mal zugegriffen wird.  
  
 Ein Instanzkonstruktor wird immer nach einen statischen Konstruktor ausgeführt.  
  
 Der Compiler kann einen Aufruf nicht an einen Konstruktor leiten, wenn die Klasse über einen statischen Konstruktor verfügt.  Der Compiler kann einen Aufruf nicht an eine Memberfunktion leiten, wenn die Klasse ein Werttyp ist, über einen statischen Konstruktor verfügt und keine Instanzkonstruktor hat.  Die CLR-Funktion kann den Aufruf leiten, der Compiler jedoch nicht.  
  
 Definieren Sie einen statischen Konstruktor als private Memberfunktion, da er nur von der CLR-Funktion aufgerufen werden soll.  
  
 Weitere Informationen zu statischen Konstruktoren finden Sie unter [wie: Definieren eines statischen Schnittstellenkonstruktors (C + c++ / CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .  
  
```  
  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
private:  
   static int i = 0;  
  
   static MyClass() {  
      Console::WriteLine("in static constructor");  
      i = 9;  
   }  
  
public:  
   static void Test() {  
      i++;  
      Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass::Test();  
   MyClass::Test();  
}  
```  
  
 **Ausgabe**  
  
```Output  
in static constructor  
10  
11  
```  
  
##  <a name="BKMK_Semantics_of_the_this_pointer"></a>Semantik dieses Zeigers  
 Wenn Sie Visual C++ zum Definieren von Typen verwenden, ist der `this`-Zeiger in einem Referenztyp vom Typ "Handle". Der `this`-Zeiger in einen Werttyp ist vom Typ "innerer Zeiger".  
  
 Diese unterschiedliche Semantik des `this`-Zeigers kann beim Aufrufen eines Standardindexers ein unerwartetes Verhalten verursachen. Im folgenden Beispiel wird die korrekte Methode zum Zugriff auf einen Standardindexer in einem Referenz- und in einem Werttyp veranschaulicht.  
  
 Weitere Informationen finden Sie unter  
  
-   [Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)  
  
-   [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)  
  
```  
  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      // accessing default indexer  
      Console::WriteLine("{0}", this[3.3]);  
   }  
};  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      // accessing default indexer  
      Console::WriteLine("{0}", this->default[3.3]);  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```  
  
 **Ausgabe**  
  
```Output  
10.89  
10.89  
```  
  
##  <a name="BKMK_Hide_by_signature_functions"></a>Ausblenden nach Signatur verdeckte Funktionen  
 In Standard-C++ wird eine Funktion in einer Basisklasse durch eine Funktion ausgeblendet, die den gleichen Namen in einer abgeleiteten Klasse hat, auch wenn die abgeleitete Klassenfunktion nicht dieselbe Anzahl bzw. Art von Parametern aufweist. Dies wird als bezeichnet *nach Namen verdeckte* Semantik. In einem Referenztyp kann eine Funktion in einer Basisklasse nur durch eine Funktion in einer abgeleiteten Klasse ausgeblendet werden, wenn sowohl der Name als auch die Parameterliste identisch sind. Dies bezeichnet man *Ausblenden nach Signatur verdeckte* Semantik.  
  
 Eine Klasse gilt als nach Signatur verdeckte Klasse, wenn alle zugehörigen Funktionen in den Metadaten als `hidebysig` gekennzeichnet sind. Standardmäßig werden alle Klassen, die unter erstellt werden **"/ CLR"** haben `hidebysig` Funktionen. Wenn eine Klasse über `hidebysig`-Funktionen verfügt, blendet der Compiler keine Funktionen in den direkten Basisklassen nach Namen aus. Wenn der Compiler jedoch eine nach Namen verdeckte Klasse in einer Vererbungskette erkennt, wird dieses nach Namen verdeckte Verhalten fortgesetzt.  
  
 Wenn eine Funktion unter der nach Signatur verdeckten Semantik für ein Objekt aufgerufen wird, identifiziert der Compiler die am meisten abgeleitete Klasse, die eine Funktion enthält, die den Funktionsaufruf erfüllen kann. Wenn es nur eine Funktion in der Klasse gibt, die den Aufruf erfüllen kann, ruft der Compiler diese Funktion auf. Wenn es mehr als eine Funktion in der Klasse gibt, die den Aufruf erfüllen kann, verwendet der Compiler die Überladungsauflösungsregeln zum Ermitteln, welche Funktion aufgerufen werden soll. Weitere Informationen zu Überladung Regeln finden Sie unter [Funktionsüberladung](../cpp/function-overloading.md).  
  
 Für einen angegebenen Funktionsaufruf kann eine Funktion in einer Basisklasse eine Signatur haben, mit der sie etwas besser übereinstimmt als eine Funktion in einer abgeleiteten Klasse. Wenn die Funktion jedoch explizit für ein Objekt der abgeleiteten Klasse aufgerufen wurde, wird die Funktion in der abgeleiteten Klasse aufgerufen.  
  
 Da der Rückgabewert nicht als Teil einer Signatur der Funktion gilt, wird eine Basisklassenfunktion ausgeblendet, wenn sie denselben Namen hat und über die dieselbe Anzahl und Art von Argumenten wie eine abgeleitete Klassenfunktion verfügt, auch wenn sie sich vom Typ des Rückgabewerts unterscheidet.  
  
 Das folgende Beispiel zeigt, dass eine Funktion in einer Basisklasse nicht von einer Funktion in einer abgeleiteten Klasse ausgeblendet wird.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   void Test() {   
      Console::WriteLine("Base::Test");   
   }  
};  
  
ref struct Derived : public Base {  
   void Test(int i) {   
      Console::WriteLine("Derived::Test");   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   // Test() in the base class will not be hidden  
   t->Test();  
}  
```  
  
 **Ausgabe**  
  
```Output  
Base::Test  
```  
  
 Das folgende Beispiel zeigt, dass der Visual C++-Compiler eine Funktion in der am meisten abgeleiteteten Klasse aufruft, auch wenn eine Konvertierung erforderlich ist, um einen oder mehrere Parameter anzugleichen. Er ruft keine Funktion in einer Basisklasse auf, die mit dem Funktionsaufruf besser übereinstimmt.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   void Test2(Single d) {   
      Console::WriteLine("Base::Test2");   
   }  
};  
  
ref struct Derived : public Base {  
   void Test2(Double f) {   
      Console::WriteLine("Derived::Test2");   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   // Base::Test2 is a better match, but the compiler  
   // calls a function in the derived class if possible  
   t->Test2(3.14f);  
}  
```  
  
 **Ausgabe**  
  
```Output  
Derived::Test2  
```  
  
 Das folgende Beispiel zeigt, dass eine Funktion ausgeblendet werden kann, auch wenn die Basisklasse die gleiche Signatur wie die abgeleitete Klasse hat.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   int Test4() {   
      Console::WriteLine("Base::Test4");   
      return 9;   
   }  
};  
  
ref struct Derived : public Base {  
   char Test4() {   
      Console::WriteLine("Derived::Test4");   
      return 'a';   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
  
   // Base::Test4 is hidden  
   int i = t->Test4();  
   Console::WriteLine(i);  
}  
```  
  
 **Ausgabe**  
  
```Output  
Derived::Test4  
97  
```  
  
##  <a name="BKMK_Copy_constructors"></a>Kopierkonstruktoren  
 Der C++-Standard besagt, dass ein Kopierkonstruktor aufgerufen wird, wenn ein Objekt so verschoben wird, dass ein Objekt an derselben Adresse erstellt und zerstört wird.  
  
 Jedoch wenn **"/ CLR"** wird verwendet, um die Kompilierung und eine Funktion, die kompiliert wird, um MSIL-Aufrufe, die eine systemeigene Funktion, bei der eine – oder mehrere – übergebener Wert und hat die native Klasse einen Kopierkonstruktor und/oder der Destruktor, der keine Kopie Konstruktor wird aufgerufen, und das Objekt wird an eine andere Adresse als der Erstellung zerstört. Dies kann Probleme verursachen, wenn die Klasse einen Zeiger zu sich selbst hat oder wenn der Code Objekte nach Adresse erfasst.  
  
 Weitere Informationen finden Sie unter [/clr (Common Language Runtime-Kompilierung)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Das folgende Beispiel veranschaulicht, was passiert, wenn ein Kopierkonstruktor nicht generiert wird.  
  
```  
  
// compile with: /clr  
#include<stdio.h>  
  
struct S {  
   int i;  
   static int n;  
  
   S() : i(n++) {   
      printf_s("S object %d being constructed, this=%p\n", i, this);   
   }  
  
   S(S const& rhs) : i(n++) {   
      printf_s("S object %d being copy constructed from S object "  
               "%d, this=%p\n", i, rhs.i, this);   
   }  
  
   ~S() {  
      printf_s("S object %d being destroyed, this=%p\n", i, this);   
   }  
};  
  
int S::n = 0;  
  
#pragma managed(push,off)  
void f(S s1, S s2) {  
   printf_s("in function f\n");  
}  
#pragma managed(pop)  
  
int main() {  
   S s;  
   S t;  
   f(s,t);  
}  
```  
  
 **Ausgabe**  
  
```Output  
S object 0 being constructed, this=0018F378  
S object 1 being constructed, this=0018F37C  
S object 2 being copy constructed from S object 1, this=0018F380  
S object 3 being copy constructed from S object 0, this=0018F384  
S object 4 being copy constructed from S object 2, this=0018F2E4  
S object 2 being destroyed, this=0018F380  
S object 5 being copy constructed from S object 3, this=0018F2E0  
S object 3 being destroyed, this=0018F384  
in function f  
S object 5 being destroyed, this=0018F2E0  
S object 4 being destroyed, this=0018F2E4  
S object 1 being destroyed, this=0018F37C  
S object 0 being destroyed, this=0018F378  
```  
  
##  <a name="BKMK_Destructors_and_finalizers"></a>Destruktoren und Finalizer  
 Destruktoren in einem Referenztyp führen eine deterministische Bereinigung von Ressourcen aus. Finalizer bereinigen nicht verwaltete Ressourcen und können deterministisch vom Destruktor oder nicht deterministisch vom Garbage Collector aufgerufen werden. Informationen über Destruktoren in standardmäßigem C++ finden Sie unter [Destruktoren](../cpp/destructors-cpp.md).  
  
```  
class classname {  
   ~classname() {}   // destructor  
   ! classname() {}   // finalizer  
};  
```  
  
 Das Verhalten von Destruktoren in einer verwalteten Visual C++-Klasse unterscheidet sich von Managed Extensions für C++. Weitere Informationen zu dieser Änderung finden Sie unter [Änderungen in der Destruktorsemantik](../dotnet/changes-in-destructor-semantics.md).  
  
 Der CLR-Garbage Collector löscht nicht verwendete verwaltete Objekte und gibt ihren Speicher frei, wenn sie nicht mehr benötigt werden. Allerdings verwendet ein Typ möglicherweise Ressourcen, die der Garbage Collector nicht freigeben kann. Diese Ressourcen werden als nicht verwaltete Ressourcen bezeichnet (z. B. systemeigene Dateihandles). Es wird empfohlen, dass Sie alle nicht verwalteten Ressourcen im Finalizer freigeben. Da verwaltete Ressourcen nicht deterministisch vom Garbage Collector freigegeben werden, ist es nicht sicher, in einem Finalizer auf verwaltete Ressourcen zu verweisen, da der Garbage Collector diese verwaltete Ressource möglicherweise bereits bereinigt hat.  
  
 Ein Visual C++-Finalizer ist nicht mit der <xref:System.Object.Finalize%2A>-Methode identisch. (In der CLR-Dokumentation werden Finalizer und die <xref:System.Object.Finalize%2A>-Methode synonym verwendet). Die <xref:System.Object.Finalize%2A>-Methode wird vom Garbage Collector aufgerufen, der jeden Finalizer in einer Klassenvererbungskette aufruft. Im Gegensatz zu Visual C++-Destruktoren führt ein Aufruf des abgeleiteten Klassenfinalizer nicht dazu, dass der Compiler den Finalizer in allen Basisklassen aufruft.  
  
 Da der Visual C++-Compiler die deterministische Freigabe von Ressourcen unterstützt, implementieren Sie nicht die <xref:System.IDisposable.Dispose%2A>- oder <xref:System.Object.Finalize%2A>-Methode. Wenn Sie jedoch mit diesen Methoden vertraut sind, finden Sie hier ein Beispiel, wie ein Visual C++-Finalizer und ein Destruktor, der den Finalizer aufruft, zum <xref:System.IDisposable.Dispose%2A>-Muster zugeordnet werden:  
  
```  
// Visual C++ code  
ref class T {  
   ~T() { this->!T(); }   // destructor calls finalizer  
   !T() {}   // finalizer  
};  
  
// equivalent to the Dispose pattern  
void Dispose(bool disposing) {  
   if (disposing) {  
      ~T();  
   } else {  
      !T();  
   }  
}  
```  
  
 Ein verwalteter Typ verwendet möglicherweise auch verwaltete Ressourcen, die Sie lieber deterministisch freigeben möchten, anstatt sie zu einem bestimmten Zeitpunkt, nachdem das Objekt nicht mehr benötigt wird, vom Garbage Collector nicht deterministisch freigeben zu lassen. Durch die deterministische Freigabe von Ressourcen kann die Leistung erheblich gesteigert werden.  
  
 Der Visual C++-Compiler ermöglicht die Definition eines Destruktors, um Objekte deterministisch zu bereinigen. Verwenden Sie den Destruktor, um alle Ressourcen freizugeben, die Sie deterministisch freigeben möchten.  Wenn ein Finalizer vorhanden ist, rufen Sie ihn im Destruktor auf, um Codeduplikate zu vermeiden.  
  
```  
  
// compile with: /clr /c  
ref struct A {  
   // destructor cleans up all resources  
   ~A() {  
      // clean up code to release managed resource  
      // ...  
      // to avoid code duplication,   
      // call finalizer to release unmanaged resources  
      this->!A();  
   }  
  
   // finalizer cleans up unmanaged resources  
   // destructor or garbage collector will  
   // clean up managed resources  
   !A() {  
      // clean up code to release unmanaged resources  
      // ...  
   }  
};  
```  
  
 Wenn der Code, der den Typ verwendet, nicht den Destruktor aufruft, gibt der Garbage Collector schließlich alle verwalteten Ressourcen frei.  
  
 Das Vorhandensein eines Destruktors bedeutet nicht, dass ein Finalizer vorhanden ist. Allerdings bedeutet das Vorhandensein eines Finalizers, dass Sie einen Destruktor definieren und den Finalizer von diesem Destruktor aufrufen müssen. Dies berücksichtigt die deterministische Freigabe von nicht verwalteten Ressourcen.  
  
 Durch Aufrufen des Destruktors wird der Abschluss des Objekts mithilfe von <xref:System.GC.SuppressFinalize%2A> unterdrückt. Wenn der Destruktor nicht aufgerufen wird, wird der Finalizer des Typs schließlich vom Garbage Collector aufgerufen.  
  
 Die deterministische Bereinigung der Objektressourcen durch Aufrufen des Destruktors kann zur Leistungssteigerung beitragen im Gegensatz zum nicht deterministischen Abschluss des Objekts durch die CLR.  
  
 Code, der in Visual C++ geschrieben und mithilfe von kompiliert hat **"/ CLR"** Destruktor des Typs ausgeführt wird, wenn:  
  
-   Ein Objekt, das mithilfe von Stapelsemantik erstellt wird, liegt außerhalb des gültigen Bereichs. Weitere Informationen finden Sie unter [C++-Stapelsemantik für Referenztypen](../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
-   Während der Erstellung des Objekts wird eine Ausnahme ausgelöst.  
  
-   Das Objekt ist ein Member in einem Objekt, dessen Destruktor ausgeführt wird.  
  
-   Rufen Sie die [löschen](../cpp/delete-operator-cpp.md) Operator auf ein Handle ([Handle für Objekt (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).  
  
-   Sie rufen den Destruktor explizit auf.  
  
 Wenn der Typ von einem Client verwendet wird, der in einer anderen Sprache geschrieben wurde, wird der Destruktor wie folgt aufgerufen:  
  
-   Bei einem Aufruf von <xref:System.IDisposable.Dispose%2A>.  
  
-   Bei einem Aufruf von `Dispose(void)` für den Typ.  
  
-   Wenn der Typ in einer C#-`using`-Anweisung außerhalb des gültigen Bereichs liegt.  
  
 Wenn Sie ein Objekt eines Referenztyps auf dem verwalteten Heap (nicht mit Stapelsemantik für Referenztypen) erstellen, verwenden Sie [Try-finally-](../cpp/try-finally-statement.md) Syntax, um sicherzustellen, dass eine Ausnahme den Destruktor ausgeführt wird nicht verhindert.  
  
```  
  
// compile with: /clr  
ref struct A {  
   ~A() {}  
};  
  
int main() {  
   A ^ MyA = gcnew A;  
   try {  
      // use MyA  
   }  
   finally {  
      delete MyA;  
   }  
}  
```  
  
 Wenn der Typ einen Destruktor enthält, generiert der Compiler eine `Dispose`-Methode, die <xref:System.IDisposable> implementiert. Wenn ein Typ, der in Visual C++ geschrieben wurde, einen Destruktor enthält, der von einer anderen Sprache verwendet wird, führt der Aufruf von `IDisposable::Dispose` für diesen Typ dazu, dass der Destruktor des Typs aufgerufen wird. Wenn der Typ in einem Visual C++-Client genutzt wird, können Sie `Dispose` nicht direkt aufrufen. Rufen Sie stattdessen den Destruktor mithilfe des `delete`-Operators auf.  
  
 Wenn der Typ einen Finalizer enthält, generiert der Compiler eine `Finalize(void)`-Methode, die <xref:System.Object.Finalize%2A> überschreibt.  
  
 Wenn ein Typ entweder einen Finalizer oder einen Destruktor enthält, generiert der Compiler entsprechend dem Entwurfsmuster eine `Dispose(bool)`-Methode. (Informationen finden Sie unter [Dispose-Muster](/dotnet/standard/design-guidelines/dispose-pattern)). Sie können `Dispose(bool)` in Visual C++ nicht explizit erstellen oder aufrufen.  
  
 Wenn ein Typ über eine Basisklasse verfügt, die dem Entwurfsmuster entspricht, werden die Destruktoren für alle Basisklassen aufgerufen, wenn der Destruktor für die abgeleitete Klasse aufgerufen wird. (Wenn der Typ in Visual C++ geschrieben wurde, stellt der Compiler sicher, dass die Typen dieses Muster implementieren.) Dies bedeutet, dass der Destruktor einer Referenzklasse mit seinen Basisklassen und Membern verknüpft wird, wie im C++-Standard festgelegt ist. Zuerst wird der Destruktor der Klasse ausgeführt und dann werden die Destruktoren für die Member in der umgekehrten Reihenfolge ausgeführt, in der sie erstellt wurden. Als Letztes werden die Destruktoren für die Basisklassen in der umgekehrten Reihenfolge ausgeführt, in der sie erstellt wurden.  
  
 Destruktoren und Finalizer sind in Werttypen oder Schnittstellen nicht zulässig.  
  
 Ein Finalizer kann nur in einem Referenztyp definiert oder deklariert werden. Wie ein Konstruktor und Destruktor hat ein Finalizer keinen Rückgabetyp.  
  
 Nachdem der Finalizer eines Objekts ausgeführt wird, werden die Finalizer in den Basisklassen, beginnend mit dem am wenigsten abgeleiteten Typ, ebenfalls aufgerufen. Finalizer für Datenmember werden nicht automatisch durch den Finalizer einer Klasse verkettet.  
  
 Wenn ein Finalizer einen systemeigenen Zeiger in einem verwalteten Typ löscht, müssen Sie sicherstellen, dass Verweise auf oder durch den systemeigenen Zeiger nicht vorzeitig erfasst werden. Rufen Sie den Destruktor auf dem verwalteten Typ auf, anstatt <xref:System.GC.KeepAlive%2A> zu verwenden.  
  
 Zur Kompilierzeit können Sie erkennen, ob ein Typ einen Finalizer oder einen Destruktor enthält. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Im folgenden Beispiel werden zwei Typen verdeutlicht: ein Typ, der nicht verwaltete Ressourcen hat, und ein Typ mit verwalteten Ressourcen, die deterministisch freigegeben werden.  
  
```  
  
// compile with: /clr  
#include <vcclr.h>  
#include <stdio.h>  
using namespace System;  
using namespace System::IO;  
  
ref class SystemFileWriter {  
   FileStream ^ file;  
   array<Byte> ^ arr;  
   int bufLen;  
  
public:  
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),   
                                     arr(gcnew array<Byte>(1024)) {}  
  
   void Flush() {  
      file->Write(arr, 0, bufLen);  
      bufLen = 0;  
   }  
  
   ~SystemFileWriter() {  
      Flush();  
      delete file;  
   }  
};  
  
ref class CRTFileWriter {  
   FILE * file;  
   array<Byte> ^ arr;  
   int bufLen;  
  
   static FILE * getFile(String ^ n) {  
      pin_ptr<const wchar_t> name = PtrToStringChars(n);  
      FILE * ret = 0;  
      _wfopen_s(&ret, name, L"ab");  
      return ret;  
   }  
  
public:  
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}  
  
   void Flush() {  
      pin_ptr<Byte> buf = &arr[0];  
      fwrite(buf, 1, bufLen, file);  
      bufLen = 0;  
   }  
  
   ~CRTFileWriter() {  
      this->!CRTFileWriter();  
   }  
  
   !CRTFileWriter() {  
      Flush();  
      fclose(file);  
   }  
};  
  
int main() {  
   SystemFileWriter w("systest.txt");  
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)