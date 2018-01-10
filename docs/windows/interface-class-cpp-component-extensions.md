---
title: "Schnittstellenklasse (Komponentenerweiterungen für C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: interface_CPP
dev_langs: C++
helpviewer_keywords:
- interface class keyword
- interface struct keyword
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: abe4173dabd20442b96c8e5536b040483df4f150
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="interface-class--c-component-extensions"></a>interface class (Komponentenerweiterungen für C++)
Deklariert eine Schnittstelle.  Informationen zu systemeigenen Schnittstellen finden Sie unter [__interface](../cpp/interface.md).  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 **Syntax**  
  
```  
  
interface_access  
interface class  
 name :  inherit_accessbase_interface{};interface_accessinterface structname :  inherit_accessbase_interface{};  
```  
  
 **Parameter**  
  
 *interface_access*  
 Der Zugriff auf eine Schnittstelle außerhalb der Assembly.  Mögliche Werte sind **öffentlichen** und `private`.  Standardmäßig ist `private` festgelegt.  Sind keine geschachtelten Schnittstellen ein *Interface_access* Spezifizierer.  
  
 *name*  
 Der Name der Schnittstelle.  
  
 *inherit_access*  
 Der Zugriff auf *Base_interface*.  Die einzige Eingabehilfen für zulässig ist eine Basisschnittstelle `public` (Standard).  
  
 *Base_interface* (optional)  
 Eine Basisschnittstelle für die Schnittstelle *Namen*.  
  
 **Hinweise**  
  
 **Struktur, Schnittstelle** entspricht **Schnittstellenklasse**.  
  
 Eine Schnittstelle kann Deklarationen für Funktionen, Ereignisse und Eigenschaften enthalten.  Alle Schnittstellenmember besitzen öffentliche zugreifbarkeit. Eine Schnittstelle kann auch statische Datenmember, Funktionen, Ereignisse und Eigenschaften enthalten, und diese statischen Member müssen in der Schnittstelle definiert werden.  
  
 Eine Schnittstelle definiert, wie eine Klasse implementiert werden kann. Eine Schnittstelle ist keine Klasse und Klassen können nur Schnittstellen implementieren. Wenn eine Funktion, die in einer Schnittstelle deklariert eine Klasse definiert wird, wird die Funktion implementiert, nicht außer Kraft gesetzt. Aus diesem Grund schließt Namenssuche Schnittstellenmember nicht.  
  
 Eine Klasse oder Struktur, die von einer Schnittstelle abgeleitet wird, muss alle Member der Schnittstelle implementieren. Bei der Implementierung der Schnittstelle *Namen* müssen Sie auch die Schnittstellen implementieren die `base_interface` Liste.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Statische Schnittstellenkonstruktoren](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Generische Schnittstellen (Visual C++)](../windows/generic-interfaces-visual-cpp.md)  
  
 Informationen zu anderen CLR-Typen finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Sie können zur Kompilierzeit erkennen, wenn ein Typ eine Schnittstelle mit ist `__is_interface_class(type)`. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 In der Entwicklungsumgebung können Sie F1-Hilfe zu dieser Schlüsselwörter abrufen, indem Sie das Schlüsselwort Hervorhebung (`interface class`, z. B.), und drücken F1.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows-Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Schnittstelle für das Verhalten der Clock-Funktion definieren kann.  
  
```  
// mcppv2_interface_class.cpp  
// compile with: /clr  
using namespace System;  
  
public delegate void ClickEventHandler(int, double);  
  
// define interface with nested interface  
public interface class Interface_A {  
   void Function_1();  
  
   interface class Interface_Nested_A {  
      void Function_2();  
   };  
};  
  
// interface with a base interface  
public interface class Interface_B : Interface_A {  
   property int Property_Block;  
   event ClickEventHandler^ OnClick;     
   static void Function_3() { Console::WriteLine("in Function_3"); }  
};  
  
// implement nested interface  
public ref class MyClass : public Interface_A::Interface_Nested_A {  
public:  
   virtual void Function_2() { Console::WriteLine("in Function_2"); }  
};  
  
// implement interface and base interface  
public ref class MyClass2 : public Interface_B {  
private:  
   int MyInt;  
  
public:  
   // implement non-static function  
   virtual void Function_1() { Console::WriteLine("in Function_1"); }  
  
   // implement property  
   property int Property_Block {  
      virtual int get() { return MyInt; }  
      virtual void set(int value) { MyInt = value; }  
   }  
   // implement event  
   virtual event ClickEventHandler^ OnClick;  
  
   void FireEvents() {  
      OnClick(7, 3.14159);  
   }  
};  
  
// class that defines method called when event occurs  
ref class EventReceiver {  
public:  
   void OnMyClick(int i, double d) {  
      Console::WriteLine("OnClick: {0}, {1}", i, d);  
   }  
};  
  
int main() {  
   // call static function in an interface  
   Interface_B::Function_3();  
  
   // instantiate class that implements nested interface  
   MyClass ^ x = gcnew MyClass;  
   x->Function_2();  
  
   // instantiate class that implements interface with base interface  
   MyClass2 ^ y = gcnew MyClass2;  
   y->Function_1();  
   y->Property_Block = 8;  
   Console::WriteLine(y->Property_Block);  
  
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();  
  
   // hook handler to event  
   y->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // invoke events  
   y->FireEvents();  
  
   // unhook handler to event  
   y->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);  
  
   // call implemented function via interface handle  
   Interface_A^ hi = gcnew MyClass2();  
   hi->Function_1();  
}  
```  
  
 **Ausgabe**  
  
```Output  
in Function_3  
  
in Function_2  
  
in Function_1  
  
8  
  
OnClick: 7, 3.14159  
  
in Function_1  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt zwei Möglichkeiten zum Implementieren von Funktionen die gleiche Signatur in mehreren Schnittstellen und die Verwendung dieser Schnittstellen durch eine Klasse deklariert.  
  
```  
// mcppv2_interface_class_2.cpp  
// compile with: /clr /c  
interface class I {  
   void Test();  
   void Test2();  
};  
  
interface class J : I {  
   void Test();  
   void Test2();  
};  
  
ref struct R : I, J {  
   // satisfies the requirement to implement Test in both interfaces  
   virtual void Test() {}  
  
   // implement both interface functions with explicit overrides  
   virtual void A() = I::Test2 {}  
   virtual void B() = J::Test2 {}  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)