---
title: sealed (Komponentenerweiterungen für C++) | Microsoft Docs
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
ms.openlocfilehash: 05c75aef047e914086aaf4ae2c0d0d3bdd04e8c7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890862"
---
# <a name="sealed--c-component-extensions"></a>sealed (Komponentenerweiterungen für C++)
`sealed` ist ein kontextbezogenes Schlüsselwort für Verweisklassen, das anzeigt, dass ein virtuelles Element nicht außer Kraft gesetzt werden kann oder ein bestimmter Typ nicht als Basistyp verwendet werden kann.  
  
> [!NOTE]
>  Die ISO C ++ 11 Standard Language besteht aus den [endgültigen](../cpp/final-specifier.md) Schlüsselwort, das in Visual Studio unterstützt wird. Verwenden Sie `final` für Standardklassen und `sealed` für Verweisklassen.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
  
## <a name="syntax"></a>Syntax
  
```  
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
  
 Die `sealed` Schlüsselwort ist gültig für systemeigene Ziele sowie für die Windows-Runtime und die common Language Runtime (CLR). Weitere Informationen finden Sie unter [Überschreibungsspezifizierer und Native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Sie zur Kompilierzeit erkennen können, ob ein Typ, mithilfe versiegelt ist der `__is_sealed(type)` Merkmal "Typ". Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 `sealed` ist ein kontextbezogenes Schlüsselwort.  Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 Finden Sie unter [Verweisklassen und Strukturen](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 (Es gibt keine Hinweise für diese Sprachfunktion, die nur für Common Language Runtime gelten.)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
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