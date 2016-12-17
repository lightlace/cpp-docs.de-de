---
title: "sealed  (C++ Component Extensions)"
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
  - "sealed_cpp"
  - "sealed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sealed keyword [C++]"
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
caps.latest.revision: 26
caps.handback.revision: "24"
ms.author: "mblome"
manager: "ghogen"
---
# sealed  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`sealed` ist ein kontextbezogenes Schlüsselwort für Verweisklassen, das anzeigt, dass ein virtuelles Element nicht außer Kraft gesetzt werden kann oder ein bestimmter Typ nicht als Basistyp verwendet werden kann.  
  
> [!NOTE]
>  Die Standardsprache gemäß ISO C\+\+11 weist das Schlüsselwort [final](../cpp/final-specifier.md) auf, das in Visual Studio unterstützt wird.  Verwenden Sie `final` für Standardklassen und `sealed` für Verweisklassen.  
  
## Alle Laufzeiten  
 **Syntax**  
  
```  
  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
  
```  
  
 **Parameter**  
  
 *Bezeichner*  
 Der Name der Funktion oder Klasse.  
  
 *Rückgabetyp*  
 Der Typ, der von einer Funktion zurückgegeben wird.  
  
 **Hinweise**  
  
 Im ersten Syntaxbeispiel wird eine Klasse versiegelt.  Im zweiten Beispiel wird eine virtuelle Funktion versiegelt.  
  
 Das Schlüsselwort `sealed` ist für systemeigene Ziele und ebenso für die [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] und die CLR \(Common Language Runtime\) gültig.  Weitere Informationen finden Sie unter [Überschreibungsspezifizierer und systemeigene Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Sie können zur Kompilierzeit erkennen, ob ein Typ "sealed" ist, indem Sie das Typmerkmal `__is_sealed (``type``)` verwenden.  Weitere Informationen finden Sie unter [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Siehe dazu [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Anforderungen  
 Compileroption: **\/ZW**  
  
## Common Language Runtime  
 \(Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.\)  
  
### Anforderungen  
 Compileroption: **\/clr**  
  
### Beispiele  
 Das folgende Codebeispiel zeigt die Wirkung von `sealed` auf ein virtuelles Element.  
  
```cpp  
// sealed_keyword.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
   virtual void g();  
};  
  
ref class X : I1 {  
public:  
   virtual void f() {  
      System::Console::WriteLine("X::f override of I1::f");  
   }  
  
   virtual void g() sealed {  
      System::Console::WriteLine("X::f override of I1::g");  
   }  
};  
  
ref class Y : public X {  
public:  
   virtual void f() override {  
      System::Console::WriteLine("Y::f override of I1::f");  
   }  
  
   /*  
   // the following override generates a compiler error  
   virtual void g() override {  
      System::Console::WriteLine("Y::g override of I1::g");  
   }    
   */  
};  
  
int main() {  
   I1 ^ MyI = gcnew X;  
   MyI -> f();  
   MyI -> g();  
  
   I1 ^ MyI2 = gcnew Y;  
   MyI2 -> f();  
}  
```  
  
 **Ausgabe**  
  
  **X::f Überschreibung von I1::f**  
 **X::f Überschreibung von I1::g**  
 **Y::f Überschreibung von I1::f** Das nächste Codebeispiel zeigt , wie eine Klasse als versiegelt markiert wird.  
  
```cpp  
// sealed_keyword_2.cpp  
// compile with: /clr  
interface struct I1 {  
   virtual void f();  
};  
  
ref class X sealed : I1 {  
public:  
   virtual void f() override {}  
};  
  
ref class Y : public X {   // C3246 base class X is sealed  
public:  
   virtual void f() override {}  
};  
```  
  
## Siehe auch  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)