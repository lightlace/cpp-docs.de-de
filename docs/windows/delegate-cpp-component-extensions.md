---
title: Delegate (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- delegate_cpp
- delegate
dev_langs:
- C++
helpviewer_keywords:
- delegate keyword [C++]
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73d40bb33509f89273b37f7704cd1922a8d5adc2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="delegate--c-component-extensions"></a>delegate (Komponentenerweiterungen für C++)
Deklariert einen Typ, der einen Funktionszeiger darstellt.  
  
## <a name="all-runtimes"></a>Alle Laufzeiten  
 Die Windows-Runtime und die common Language Runtime unterstützen Delegaten.  
  
### <a name="remarks"></a>Hinweise  
 `delegate` ist ein kontextbezogenes Schlüsselwort. Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Um zum Zeitpunkt der Kompilierung festzustellen, ob ein Typ ein Delegat ist, verwenden die `__is_delegate()` Merkmal "Typ". Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## <a name="windows-runtime"></a>Windows-Runtime  
 C + c++ / CX unterstützt Delegaten mit der folgenden Syntax.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
access  
delegate  
return-type  
delegate-type-identifier  
(  
[ parameters ]  
)  
  
```  
  
### <a name="parameters"></a>Parameter  
 *Zugriff*  
 (optional) Der Zugriff auf den Delegaten kann u. `public` (Standard) oder `private`. Der Funktionsprototyp kann auch mit qualifiziert werden die `const` oder `volatile` Schlüsselwörter.  
  
 *Rückgabetyp*  
 Der Rückgabetyp der Funktionsprototypen.  
  
 *Delegaten Typbezeichner*  
 Der Name des deklarierten Delegattyps.  
  
 *Parameter*  
 (Optional) Die Typen und Bezeichner der Funktionsprototypen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der *Delegaten Typbezeichner* deklariert ein Ereignis mit den gleichen Prototyp wie der Delegat. Weitere Informationen finden Sie unter [Delegaten (C + c++ / CX)](../cppcx/delegates-c-cx.md).  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
## <a name="common-language-runtime"></a>Common Language Runtime  
 Die common Language Runtime unterstützt Delegaten mit der folgenden Syntax an.  
  
### <a name="syntax"></a>Syntax  
  
```cpp  
access  
delegate  
function_declaration  
  
```  
  
### <a name="parameters"></a>Parameter  
 *Zugriff*  
 (optional) Der Zugriff auf den Delegaten außerhalb der Assembly kann öffentlich oder privat sein.  Die Standardeinstellung ist privat.  Innerhalb einer Klasse kann ein Delegat beliebigem Zugriff verfügen.  
  
 *function_declaration*  
 Die Signatur der Funktion, die an den Delegaten gebunden werden kann. Der Rückgabetyp eines Delegaten kann verwalteten Typ sein. Aus Gründen der Interoperabilität wird empfohlen, dass der Rückgabetyp eines Delegaten ein CLS-Typ sein.  
  
 Definieren Sie einen ungebundenen Delegaten, der erste Parameter im *Function_declaration* muss der Typ des der `this` Zeiger für das Objekt. 
  
### <a name="remarks"></a>Hinweise  
 Delegaten sind multicast: "" Funktionszeiger auf eine oder mehrere Methoden innerhalb einer verwalteten Klasse gebunden werden kann. Die **Delegieren** -Schlüsselwort definiert ein multicast-Delegat mit einer bestimmten Methodensignatur.  
  
 Ein Delegat kann auch an eine Methode, eine Wertklasse, z. B. eine statische Methode gebunden werden.  
  
 Ein Delegat weist folgende Merkmale auf:  
  
-   Es erbt von **System:: MulticastDelegate**.  
  
-   Er verfügt über einen Konstruktor, der zwei Argumente akzeptiert: einen Zeiger auf eine verwaltete Klasse oder **NULL** (im Fall der Bindung an eine statische Methode) und eine vollständig qualifizierte Methode des angegebenen Typs.  
  
-   Er verfügt über eine Methode mit dem Namen `Invoke`, deren Signatur der deklarierten Signatur des Delegaten entspricht.  
  
 Wenn ein Delegat aufgerufen wird, dessen ausgeschlossener heißen in der Reihenfolge, das sie angefügt wurden.  
  
 Der Rückgabewert eines Delegaten ist der Rückgabewert der letzte angefügte Member-Funktion.  
  
 Delegaten können nicht überladen werden.  
  
 Delegaten können gebunden oder ungebunden sein.  
  
 Wenn Sie einen gebundenen Delegaten instanziieren, wird das erste Argument ein Objektverweis sein.  Das zweite Argument der einen Delegaten-Instanziierung ist entweder die Adresse einer Methode eines Objekts verwaltete Klasse oder ein Zeiger auf eine Methode eines Werttyps sein.   Das zweite Argument der einen Delegaten Instanziierung muss benennen Sie die Methode mit der vollständigen Klasse Scope-Syntax und Anwenden der Address-of-Operators.  
  
 Wenn Sie einen ungebundenen Delegaten instanziieren, wird das erste Argument entweder die Adresse einer Methode eines Objekts verwaltete Klasse oder ein Zeiger auf eine Methode ein Werttyp sein.   Das Argument muss benennen Sie die Methode mit der vollständigen Klasse Scope-Syntax und den Address-of-Operator angewendet.  
  
 Bei der Erstellung eines Delegaten an eine globale oder statische Funktion ist nur ein Parameter erforderlich: die Funktion (optional, die Adresse der Funktion).  
  
 Weitere Informationen zu Delegaten finden Sie unter  
  
-   [Vorgehensweise: Definieren und Verwenden von Delegaten (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [Generische Delegaten (Visual C++)](../windows/generic-delegates-visual-cpp.md)  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Das folgende Beispiel zeigt, wie zu deklarieren, initialisieren und Aufrufen von Delegaten.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **Ausgabe**  
  
```Output  
in func1 8  
  
in func1 9  
  
in func2 9  
  
in func2 10  
  
in static func3 11  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)