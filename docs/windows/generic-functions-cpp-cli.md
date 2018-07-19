---
title: Generische Funktionen (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], generic
- generic methods
- generics [C++], functions
- methods [C++], generic
- generic functions
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66eb27b28a1b18942c0a8a9a77a877a2f0b2ef8c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878833"
---
# <a name="generic-functions-ccli"></a>Generische Funktionen (C++/CLI)
Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird. Beim Aufruf werden die tatsächliche Typen anstelle der Type-Parameter verwendet.  
  
## <a name="all-platforms"></a>Alle Plattformen  
 **Hinweise**  
  
 Diese Funktion gilt nicht für alle Plattformen.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 **Hinweise**  
  
 Diese Funktion ist in Windows-Runtime nicht unterstützt.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird. Beim Aufruf werden die tatsächliche Typen anstelle der Type-Parameter verwendet.  
  
 **Syntax**  
  
```  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
 **Parameter**  
  
 *Attribute* (Optional)  
 Zusätzliche deklarative Informationen. Weitere Informationen zu Attributen und Attributklassen finden Sie unter "Attribute".  
  
 *Modifizierer* (Optional)  
 Ein Modifizierer für die Funktion, z. B. statische.  `virtual` ist nicht zulässig, da virtuelle Methoden können nicht generisch sein.  
  
 *Rückgabetyp*  
 Der Typ, der von der Methode zurückgegeben wird. Wenn der Rückgabetyp "void" ist, muss keinen Wert zurückgibt.  
  
 *identifier*  
 Der Funktionsname.  
  
 *Typparameter Bezeichner*  
 IDs durch Kommas getrennte Liste.  
  
 *formaler Parameter* (Optional)  
 Parameterliste.  
  
 *Type-Parameter-Einschränkungen-Klauseln*  
 Dies gibt die Einschränkungen für die Typen, die als Typargumente verwendet werden können, und nimmt die Form, die im angegebenen [Einschränkungen für generische Typparameter (C + c++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *Hauptteil der Funktion*  
 Der Text der Methode, die auf den Parameter-Typenbezeichnern verweisen kann.  
  
 **Hinweise**  
  
 Generische Funktionen sind Funktionen, die mit einem generischen Typparameter deklariert. Sie können Methoden in einer Klasse oder Struktur oder eigenständige Funktionen sein. Eine einzelne generische Deklaration deklariert implizit eine Familie von Funktionen, die nur in der Ersetzung von einer anderen tatsächlichen Typ für den generischen Typparameter zu unterscheiden.  
  
 In Visual C++ können die Klasse oder Struktur Konstruktoren nicht mit generischen Typparameter deklariert werden.  
  
 Wenn aufgerufen wird, wird der generische Typparameter durch einen tatsächlichen Typ ersetzt. Der tatsächliche Typ kann explizit in spitzen Klammern Syntax ähnelt einem Funktionsaufruf Vorlage angegeben werden. Ohne die Type-Parameter aufgerufen wird, versucht der Compiler wird den tatsächlichen Typ der Parameter im Funktionsaufruf angegeben hergeleitet werden. Das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann, meldet der Compiler einen Fehler.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Codebeispiel wird eine generische Funktion veranschaulicht.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **Beispiel**  
  
 Generische Funktionen können auf der Grundlage Signatur oder Stelligkeit und die Anzahl der Typparameter in einer Funktion überladen werden. Darüber hinaus können generische Funktionen mit nicht-generische Funktionen mit dem gleichen Namen überladen werden, solange die Funktionen in einige Parameter unterscheiden. Beispielsweise können die folgenden Funktionen überladen werden:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **Beispiel**  
  
 Im folgenden Beispiel wird eine generische Funktion Suche nach dem ersten Element in einem Array. Mit ihr wird deklariert `MyClass`, die von der Basisklasse erbt `MyBaseClass`. `MyClass` enthält eine generische Funktion `MyFunction`, die einer anderen generischen Funktion aufruft, `MyBaseClassFunction`, in der Basisklasse. In **main**, die generische Funktion `MyFunction`, wird mit unterschiedlichen Typargumenten aufgerufen.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Ausgabe**  
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)   
 [Generika](../windows/generics-cpp-component-extensions.md)