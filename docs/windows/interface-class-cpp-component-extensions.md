---
title: "interface class  (C++ Component Extensions)"
ms.custom: na
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "interface_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interface class keyword"
  - "interface struct keyword"
ms.assetid: 3ccea701-f50b-4da7-ad6b-f0ee1203e2b9
caps.latest.revision: 30
caps.handback.revision: "28"
ms.author: "mblome"
manager: "ghogen"
---
# interface class  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Deklariert eine Schnittstelle.  Weitere Informationen zu systemeigenen Schnittstellen, finden Sie unter ["](../cpp/interface.md).  
  
## Alle Laufzeiten  
 **Syntax**  
  
```  
  
        interface_access interface class  name :  inherit_access base_interface {};  
interface_access interface struct name :  inherit_access base_interface {};  
```  
  
 **Parameter**  
  
 *interface\_access*  
 Die Barrierefreiheit einer Schnittstelle außerhalb der Assembly.  Mögliche Werte sind **public** und `private`. `private` ist die Standardeinstellung.  Geschachtelte Schnittstellen können einen Bezeichner *interface\_access* aufweisen.  
  
 *name*  
 Der Name der Schnittstelle.  
  
 *inherit\_access*  
 Der Zugriff von *base\_interface*.  Die einzige sind empfängt Barrierefreiheit für eine Basisschnittstelle ist `public` \(Standard\).  
  
 *base\_interface* \(optional\)  
 Eine Schnittstelle Basisschnittstelle für *name*.  
  
 **Hinweise**  
  
 **interface struct** entspricht **interface class**.  
  
 Eine Schnittstelle kann Deklarationen für Funktionen, Ereignisse und Eigenschaften enthalten.  Alle Implementierungen verfügen über öffentliche Zugriffsmöglichkeiten.  Eine Schnittstelle kann Member, Funktionen, Ereignisse und Eigenschaften der statischen außerdem Daten enthalten, und diese statischen Member sollten in der Schnittstelle definiert sind.  
  
 Eine Schnittstelle definiert, wie eine Klasse verfügen implementiert wird.  Eine Schnittstelle ist keine Klasse und Klassen können Schnittstellen nur implementieren.  Wenn eine Klasse eine Funktion definiert, die in einer Schnittstelle deklariert wurde, wird die Funktion implementiert, nicht überschrieben.  Daher enthält Namenssuche nicht Schnittstellenmember.  
  
 Eine Klasse oder Struktur, die von einer Schnittstelle abgeleitet wird, müssen alle Member der Schnittstelle implementieren.  Wenn Sie Schnittstellennamen implementieren, müssen Sie die Schnittstellen in der Liste auch `base_interface` implementieren.  
  
 Weitere Informationen finden Sie unter:  
  
-   [Schnittstellen\-statischer Konstruktor](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md)  
  
-   [Generic Interfaces \(Visual C\+\+\)](../windows/generic-interfaces-visual-cpp.md)  
  
 Informationen zu anderen CLR\-Typen, finden Sie unter [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md).  
  
 Sie können zur Kompilierzeit erkennen, wenn ein Typ eine Schnittstelle mit `__is_interface_class(``type``)` ist.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 In der Entwicklungsumgebung können Sie F1\-Hilfe für diese Schlüsselwörtern abrufen, indem Sie das Schlüsselwort \(z. B. `interface class`\) markieren und F1 drücken.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Hinweise**  
  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Windows\-Runtime gelten.\)  
  
### Voraussetzungen  
 Compileroption: **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Hinweise**  
  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.\)  
  
### Voraussetzungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Schnittstelle das Verhalten einer Uhrfunktion definieren kann.  
  
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
  
  **in Function\_3**  
 **in Function\_2**  
 **in Function\_1**  
 **8**  
 **OnClick: 7, 3.14159**  
 **in Function\_1** **Beispiel**  
  
 Im folgenden Codebeispiel werden zwei Möglichkeiten gezeigt, Funktionen mit der gleichen Signatur zu implementieren, die in mehreren Schnittstellen deklariert und wo diese Schnittstellen durch eine Klasse verwendet werden.  
  
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
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)