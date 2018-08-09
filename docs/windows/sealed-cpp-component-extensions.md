---
title: sealed (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- sealed_cpp
- sealed
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
ms.assetid: 3d0d688a-41aa-45f5-a25a-65c44206521e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe50fed4fd701ba171620d2c0cd0cde6e8da2bbc
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020225"
---
# <a name="sealed--c-component-extensions"></a>sealed (Komponentenerweiterungen für C++)
**versiegelte** ist ein kontextbezogenes Schlüsselwort für Verweisklassen, der angibt, dass ein virtueller Member nicht überschrieben werden kann, oder ein Typ kann nicht als Basistyp verwendet werden.  
  
> [!NOTE]
>  Der ISO C ++ 11-Standardsprache hat die [endgültige](../cpp/final-specifier.md) -Schlüsselwort, das in Visual Studio unterstützt wird. Verwendung **endgültige** für Standardklassen und **versiegelten** für Verweisklassen.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
  
## <a name="syntax"></a>Syntax
  
```cpp  
ref class identifier sealed {...};  
virtual return-type identifier() sealed {...};  
```  
  
### <a name="parameters"></a>Parameter  
 *identifier*  
 Der Name der Funktion oder Klasse.  
  
 *Rückgabetyp*  
 Der Typ, der von einer Funktion zurückgegeben wird.  
  
## <a name="remarks"></a>Hinweise  
  
 Im ersten Syntaxbeispiel wird eine Klasse versiegelt. Im zweiten Beispiel wird eine virtuelle Funktion versiegelt.  
  
 Die **versiegelten** Schlüsselwort ist gültig für systemeigene Ziele sowie für die Windows-Runtime und die common Language Runtime (CLR). Weitere Informationen finden Sie unter [Überschreibungsspezifizierer und Native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Sie können zur Kompilierzeit erkennen, ob ein Typ, mithilfe versiegelt ist der `__is_sealed(type)` Typeigenschaft. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 **versiegelte** ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/ZW`  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/clr`  
  
### <a name="examples"></a>Beispiele  
 Das folgende Codebeispiel zeigt die Auswirkungen der **versiegelten** auf ein virtuelles Element.  
  
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
  
```Output  
X::f override of I1::f  
X::f override of I1::g  
Y::f override of I1::f  
```  
  
 Das nächste Codebeispiel zeigt , wie eine Klasse als versiegelt markiert wird.  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)