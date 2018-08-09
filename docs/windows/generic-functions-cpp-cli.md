---
title: Generische Funktionen (C++ / CLI) | Microsoft-Dokumentation
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
ms.openlocfilehash: 2429b86ad872ea310d690187c7283b8498ece3f5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645125"
---
# <a name="generic-functions-ccli"></a>Generische Funktionen (C++/CLI)
Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird. Wenn aufgerufen, werden die tatsächliche Typen anstelle der Type-Parameter verwendet.  
  
## <a name="all-platforms"></a>Alle Plattformen  
### <a name="remarks"></a>Hinweise
  
 Diese Funktion gilt nicht für alle Plattformen.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
### <a name="remarks"></a>Hinweise
  
 Dieses Feature wird in der Windows-Runtime nicht unterstützt.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/ZW`  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 Eine generische Funktion ist eine Funktion, die mit den beiden Typparametern deklariert wird. Wenn aufgerufen, werden die tatsächliche Typen anstelle der Type-Parameter verwendet.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
[attributes] [modifiers]  
return-type identifier<type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{function-body}  
```  
  
### <a name="parameters"></a>Parameter 
  
 *Attribute* (Optional)  
 Zusätzliche deklarative Informationen. Weitere Informationen zu Attributen und Attributklassen finden Sie unter "Attribute".  
  
 *Modifizierer* (Optional)  
 Ein Modifizierer für die Funktion, wie z. B. statische.  **virtuelle** ist nicht zulässig, da virtuelle Methoden nicht generisch sein können.  
  
 *Rückgabetyp*  
 Der Typ, der von der Methode zurückgegeben wird. Wenn der Rückgabetyp "void" ist, muss keinen Wert zurückgibt.  
  
 *identifier*  
 Der Funktionsname.  
  
 *Typparameter Bezeichner*  
 Liste der durch Trennzeichen getrennte IDs.  
  
 *Formal-Parameters* (Optional)  
 Parameterliste.  
  
 *Type-Parameter-Einschränkungen-Klauseln*  
 Dies gibt die Einschränkungen für die Typen, die als Typargumente verwendet werden können, und nimmt die Form, die im angegebenen [Einschränkungen für generische Typparameter (C++ / CLI)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *Funktionsrumpf*  
 Der Text der Methode, die auf die Typ-Parameter-IDs verweisen kann.  
  
### <a name="remarks"></a>Hinweise  
  
 Generische Funktionen sind Funktionen, die mit einem generischen Typparameter deklariert. Sie können Methoden in einer Klasse oder Struktur oder eigenständige Funktionen sein. Eine einzelne generische Deklaration deklariert implizit eine Gruppe von Funktionen, die nur in der Ersetzung von einem anderen tatsächlichen Typ für den generischen Typparameter zu unterscheiden.  
  
 In Visual C++ können die Klasse oder Struktur Konstruktoren nicht mit generischen Typparametern deklariert werden.  
  
 Wenn aufgerufen, wird der generische Typparameter durch einen tatsächlichen Typ ersetzt. Der tatsächliche Typ kann explizit in spitzen Klammern, die mithilfe der Syntax ähnlich auf ein Funktionsaufruf Vorlage angegeben werden. Ohne die Type-Parameter aufgerufen wird, versucht der Compiler, den tatsächlichen Typ aus den Parametern, die im Funktionsaufruf angegeben abzuleiten. Wenn das geplante Typargument nicht von den verwendeten Parametern abgeleitet werden kann, meldet der Compiler einen Fehler.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/clr`  
  
### <a name="examples"></a>Beispiele  
  
 Im folgenden Codebeispiel wird veranschaulicht, eine generische Funktion.  
  
```cpp  
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
  
 Generische Funktionen können basierend auf der Signatur "oder" Arity "," die Anzahl der Typparameter für eine Funktion überladen werden. Darüber hinaus können generische Funktionen mit nicht generischen Funktionen mit dem gleichen Namen, überladen werden, solange die Funktionen in einigen Typparametern unterscheiden sich. Die folgenden Funktionen können zum Beispiel können überladen werden:  
  
```cpp  
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
  
 Im folgenden Beispiel wird eine generische Funktion, um das erste Element in einem Array zu finden. Deklariert `MyClass`, die von der Basisklasse erbt `MyBaseClass`. `MyClass` enthält eine generische Funktion `MyFunction`, ruft eine weitere generische Funktion `MyBaseClassFunction`, innerhalb der Basisklasse. In `main`, die generische Funktion `MyFunction`, wird mit verschiedenen Typargumenten aufgerufen.  
  
```cpp  
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
  
```Output  
My function returned an int: 2003  
My function returned a string: Hello generic functions!  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)   
 [Generika](../windows/generics-cpp-component-extensions.md)