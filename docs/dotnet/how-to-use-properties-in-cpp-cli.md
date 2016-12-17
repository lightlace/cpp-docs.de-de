---
title: "Gewusst wie: Verwenden von Eigenschaften in C++/CLI"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eigenschaften [C++], Einfach"
  - "Einfache Eigenschaften"
ms.assetid: f5d82547-e214-4f05-9e1b-ddb6d0dc5e4c
caps.latest.revision: 10
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Verwenden von Eigenschaften in C++/CLI
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird wie auf die Eigenschaften in C\+\+\/CLI an.  
  
## Grundlegende Eigenschaften  
 Grundlegende Eigenschaft\-jene, die lediglich private Daten zuweisen und abrufen, müssen Member\-Sie explizit die get\-Accessormethode und set\-Accessor\-Funktionen nicht definieren, da der Compiler sie automatisch bereitgestellt wird, wenn er nur den Datentyp der Eigenschaft angegeben wird.  Dieser Code zeigt eine grundlegende Eigenschaft:  
  
```  
// SimpleProperties.cpp  
// compile with: /clr  
using namespace System;  
  
ref class C {  
public:  
   property int Size;  
};  
  
int main() {  
   C^ c = gcnew C;  
   c->Size = 111;  
   Console::WriteLine("c->Size = {0}", c->Size);  
}  
```  
  
 **Ausgabe**  
  
  **CGröße \>\= 111**   
## Statische Eigenschaften  
 Dieses Codebeispiel zeigt, wie eine statische Eigenschaft deklariert und verwendet.  Eine statische Eigenschaft kann statische Member seiner Klasse nur zugreifen.  
  
```  
// mcppv2_property_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class StaticProperties {  
   static int MyInt;  
   static int MyInt2;  
  
public:  
   static property int Static_Data_Member_Property;  
  
   static property int Static_Block_Property {  
      int get() {  
         return MyInt;  
      }  
  
      void set(int value) {  
         MyInt = value;  
      }        
   }  
};  
  
int main() {  
   StaticProperties::Static_Data_Member_Property = 96;  
   Console::WriteLine(StaticProperties::Static_Data_Member_Property);  
  
   StaticProperties::Static_Block_Property = 47;  
   Console::WriteLine(StaticProperties::Static_Block_Property);  
}  
```  
  
 **Ausgabe**  
  
  **96**  
**47**   
## Indizierte Eigenschaften  
 Eine indizierte Eigenschaft macht normalerweise eine Datenstruktur verfügbar auf die zugegriffen wird, indem einen Feldindex Operator verwendet.  
  
 Wenn Sie eine indizierte Standardeigenschaft verwenden, können Sie auf die Datenstruktur derzeit zugreifen, indem Sie den Klassennamen zugreifen, kann aber, wenn Sie eine benutzerdefinierte indizierte Eigenschaft verwenden, müssen Sie dem Eigenschaftennamen angeben, um auf die Datenstruktur zuzugreifen.  
  
 Informationen dazu, wie Sie auf einen Standardindexer, indem Sie den `this` Zeiger verwenden, finden Sie unter [Semantik des this\-Zeigers in Wert\- und Referenztypen](../misc/semantics-of-the-this-pointer-in-value-and-reference-types.md).  
  
 Informationen dazu, wie Sie einen Indexer, der in C\# geschrieben wurde, finden Sie unter [Gewusst wie: Verwenden eines C\#\-Indexers](../dotnet/how-to-consume-a-csharp-indexer-cpp-cli.md).  
  
 Dieses Codebeispiel zeigt, wie standardmäßige und benutzerdefinierte indizierte Eigenschaften verwendet:  
  
```  
// mcppv2_property_2.cpp  
// compile with: /clr  
using namespace System;  
public ref class C {  
   array<int>^ MyArr;  
  
public:  
   C() {  
      MyArr = gcnew array<int>(5);  
   }  
  
   // default indexer  
   property int default[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
  
   // user-defined indexer  
   property int indexer1[int] {  
      int get(int index) {  
         return MyArr[index];  
      }  
      void set(int index, int value) {  
         MyArr[index] = value;  
      }  
   }  
};  
  
int main() {  
   C ^ MyC = gcnew C();  
  
   // use the default indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC[i] = i;  
      Console::Write("{0} ", MyC[i]);  
   }  
  
   Console::WriteLine("]");  
  
   // use the user-defined indexer  
   Console::Write("[ ");  
   for (int i = 0 ; i < 5 ; i++) {  
      MyC->indexer1[i] = i * 2;  
      Console::Write("{0} ", MyC->indexer1[i]);  
   }  
  
   Console::WriteLine("]");  
}  
```  
  
 **Ausgabe**  
  
  **\[ 0 1 2 3 4 \]**  
**\[ 0 2 4 6 8 \]** Das folgende Beispiel zeigt, wie den Standardindexer aufgerufen wird, indem den `this` Zeiger verwendet.  
  
```  
// call_default_indexer_through_this_pointer.cpp  
// compile with: /clr /c  
value class Position {  
public:  
   Position(int x, int y) : position(gcnew array<int, 2>(100, 100)) {  
      this->default[x, y] = 1;  
   }  
  
   property int default[int, int] {  
      int get(int x, int y) {  
         return position[x, y];  
      }  
  
      void set(int x, int y, int value) {}  
   }  
  
private:  
   array<int, 2> ^ position;  
};  
```  
  
 Dieses Beispiel zeigt, wie <xref:System.Reflection.DefaultMemberAttribute> verwendet, um den Standardindexer anzugeben:  
  
```  
// specify_default_indexer.cpp  
// compile with: /LD /clr  
using namespace System;  
[Reflection::DefaultMember("XXX")]  
public ref struct Squares {  
   property Double XXX[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
};  
```  
  
 Im folgenden Beispiel verwendet die Metadaten, das im vorherigen Beispiel erstellt wird.  
  
```  
// consume_default_indexer.cpp  
// compile with: /clr  
#using "specify_default_indexer.dll"  
int main() {  
   Squares ^ square = gcnew Squares();  
   System::Console::WriteLine("{0}", square[3]);  
}  
```  
  
 **Ausgabe**  
  
 **9**   
## Virtuelle Eigenschaften  
 Dieses Codebeispiel zeigt, wie virtuelle Eigenschaften deklariert und verwendet:  
  
```  
// mcppv2_property_4.cpp  
// compile with: /clr  
using namespace System;  
interface struct IEFace {  
public:  
   property int VirtualProperty1;  
   property int VirtualProperty2 {  
      int get();  
      void set(int i);  
   }  
};  
  
// implement virtual events  
ref class PropImpl : public IEFace {  
   int MyInt;  
public:  
   virtual property int VirtualProperty1;  
  
   virtual property int VirtualProperty2 {  
      int get() {  
         return MyInt;  
      }  
      void set(int i) {  
         MyInt = i;  
      }  
   }  
};  
  
int main() {  
   PropImpl ^ MyPI = gcnew PropImpl();  
   MyPI->VirtualProperty1 = 93;  
   Console::WriteLine(MyPI->VirtualProperty1);  
  
   MyPI->VirtualProperty2 = 43;  
   Console::WriteLine(MyPI->VirtualProperty2);  
}  
```  
  
 **Ausgabe**  
  
  **93**  
**43**   
## Abstrakte versiegelte und Eigenschaften  
 Obwohl die Schlüsselwörter [abstract](../windows/abstract-cpp-component-extensions.md) und [sealed](../windows/sealed-cpp-component-extensions.md) angegeben werden, z gültig der Spezifikationen ECMA C\+\+\/CLI, für den Visual C\+\+\-Compiler, können Sie sie auf trivialen Eigenschaften noch auf die Eigenschaftendeklaration einer nicht trivialen Eigenschaft nicht angeben.  
  
 Um eine versiegelte oder abstrakte Eigenschaft deklarieren, müssen Sie eine nicht\-triviale Eigenschaft definieren und dem `abstract` oder `sealed`\-Schlüsselwort in den get\- und set\-Accessor\-Funktionen dann angeben.  
  
```  
// properties_abstract_sealed.cpp  
// compile with: /clr  
ref struct A {  
protected:  
   int m_i;  
  
public:  
   A() { m_i = 87; }  
  
   // define abstract property  
   property int Prop_1 {  
      virtual int get() abstract;  
      virtual void set(int i) abstract;  
   }  
};  
  
ref struct B : A {  
private:  
   int m_i;  
  
public:  
   B() { m_i = 86; }  
  
   // implement abstract property  
   property int Prop_1 {  
      virtual int get() override { return m_i; }  
      virtual void set(int i) override { m_i = i; }  
   }  
};  
  
ref struct C {  
private:  
   int m_i;  
  
public:  
   C() { m_i = 87; }  
  
   // define sealed property  
   property int Prop_2 {  
      virtual int get() sealed { return m_i; }  
      virtual void set(int i) sealed { m_i = i; };  
   }  
};  
  
int main() {  
   B b1;  
   // call implementation of abstract property  
   System::Console::WriteLine(b1.Prop_1);  
  
   C c1;  
   // call sealed property  
   System::Console::WriteLine(c1.Prop_2);  
}  
```  
  
 **Ausgabe**  
  
  **86**  
**87**   
## Mehrdimensionale Eigenschaften  
 Sie können auch mehrdimensionale Accessormethoden von Eigenschaften verwenden, um zu definieren, die eine nichtstandardisierte Anzahl von Parametern verwenden.  
  
```  
// mcppv2_property_5.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0) {}  
   property double MultiDimProp[int, int, int] {  
      double get(int, int, int) {  
         return d;  
      }  
      void set(int i, int j, int k, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
   property double MultiDimProp2[int] {  
      double get(int) {  
         return d;  
      }  
      void set(int i, double l) {  
         // do something with those ints  
         d = l;  
      }  
   }  
  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MultiDimProp[0,0,0] = 1.1;  
   System::Console::WriteLine(MyX->MultiDimProp[0, 0, 0]);  
}  
```  
  
 **Ausgabe**  
  
  **1.1**   
## Überladeneigenschaftenaccessoren  
 Das folgende Beispiel zeigt, wie indizierte Eigenschaften überladen werden.  
  
```  
// mcppv2_property_6.cpp  
// compile with: /clr  
ref class X {  
   double d;  
public:  
   X() : d(0.0) {}  
   property double MyProp[int] {  
      double get(int i) {  
         return d;  
      }  
  
      double get(System::String ^ i) {  
         return 2*d;  
      }  
  
      void set(int i, double l) {  
         d = i * l;  
      }  
   }   // end MyProp definition  
};  
  
int main() {  
   X ^ MyX = gcnew X();  
   MyX->MyProp[2] = 1.7;  
   System::Console::WriteLine(MyX->MyProp[1]);  
   System::Console::WriteLine(MyX->MyProp["test"]);  
}  
```  
  
 **Ausgabe**  
  
  **3.4**  
**6.8**   
## Siehe auch  
 [property](../windows/property-cpp-component-extensions.md)