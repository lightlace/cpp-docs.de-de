---
title: Delegaten (C++ / CLI und C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/12/2018
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
ms.openlocfilehash: 2281dfb6648f9c4756800a0693f184ccaa7435d7
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2018
ms.locfileid: "49327959"
---
# <a name="delegate--ccli-and-ccx"></a>Delegaten (C++ / CLI und C++ / CX)

Deklariert einen Typ, der einen Funktionszeiger darstellt.

## <a name="all-runtimes"></a>Alle Laufzeiten

Die Windows-Runtime und die common Language Runtime unterstützen Delegaten.

### <a name="remarks"></a>Hinweise

**Delegieren** ist ein kontextbezogenes Schlüsselwort. Weitere Informationen finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).

Verwenden Sie zum Zeitpunkt der Kompilierung erkennen, wenn ein Typ eines Delegaten ist der `__is_delegate()` Typeigenschaft. Weitere Informationen finden Sie unter [Compilerunterstützung für Typmerkmale](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Windows-Runtime

C++ / CX unterstützt Delegaten mit der folgenden Syntax.

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

*Zugriff*<br/>
(optional) Der Zugriff auf den Delegaten, der sein kann **öffentliche** (Standard) oder **private**. Der Funktionsprototyp kann auch qualifiziert werden, mit der **const** oder **flüchtige** Schlüsselwörter.

*Rückgabetyp*<br/>
Der Rückgabetyp von den Funktionsprototyp.

*Delegate-Type-identifier*<br/>
Der Name des der deklarierten Delegattyp.

*Parameter*<br/>
(Optional) Die Typen und Bezeichner, der den Funktionsprototyp.

### <a name="remarks"></a>Hinweise

Verwenden der *Delegate-Type-Identifier* um ein Ereignis mit den gleichen Prototyp wie den Delegaten zu deklarieren. Weitere Informationen finden Sie unter [Delegaten (C++ / CX)](../cppcx/delegates-c-cx.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Die common Language Runtime unterstützt Delegaten mit der folgenden Syntax an.

### <a name="syntax"></a>Syntax

```cpp
access
delegate
function_declaration
```

### <a name="parameters"></a>Parameter

*Zugriff*<br/>
(optional) Der Zugriff auf den Delegaten außerhalb der Assembly kann öffentlich oder privat sein.  Der Standardwert ist privat.  Innerhalb einer Klasse kann ein Delegat aller Zugriffsebenen verfügen.

*function_declaration*<br/>
Die Signatur der Funktion, die an den Delegaten gebunden werden kann. Der Rückgabetyp eines Delegaten kann es sich um einen verwalteten Typ sein. Aus Gründen der Interoperabilität empfiehlt es sich, dass der Rückgabetyp eines Delegaten ein CLS-Typ sein.

Definieren Sie einen ungebundenen Delegaten, der erste Parameter im *Function_declaration* muss der Typ des der **dies** Zeiger für das Objekt.

### <a name="remarks"></a>Hinweise

Delegaten sind multicast: "" Funktionszeiger auf eine oder mehrere Methoden in einer verwalteten Klasse gebunden werden kann. Die **Delegieren** -Schlüsselwort definiert einen multicast-Delegat mit einer bestimmten Methodensignatur.

Ein Delegat kann auch an eine Methode einer Wertklasse, z. B. eine statische Methode gebunden werden.

Ein Delegat weist folgende Merkmale auf:

- Sie erbt von `System::MulticastDelegate`.

- Es hat einen Konstruktor, der zwei Argumente akzeptiert: einen Zeiger auf eine verwaltete Klasse oder NULL (im Fall von der Bindung an eine statische Methode) und eine vollständig qualifizierte Methode des angegebenen Typs.

- Er verfügt über eine Methode mit dem Namen `Invoke`, deren Signatur der deklarierten Signatur des Delegaten entspricht.

Wenn ein Delegat aufgerufen wird, werden die Funktion(en) aufgerufen, in der Reihenfolge, in der sie zugeordnet wurden.

Der Rückgabewert eines Delegaten ist der Rückgabewert die letzte angefügte Member-Funktion.

Delegaten können nicht überladen werden.

Delegaten können gebunden oder ungebunden sein.

Wenn Sie einen gebundenen Delegaten instanziieren, muss das erste Argument ein Objektverweis sein. Das zweite Argument der eine Instanziierung von Delegaten muss entweder die Adresse einer Methode ein Objekt der verwalteten Klasse oder ein Zeiger auf eine Methode eines Werttyps sein. Das zweite Argument der eine Instanziierung von Delegaten muss benennen Sie die Methode mit der vollständigen Klasse Scope-Syntax und die Address-of-Operator angewendet.

Wenn Sie einen ungebundenen Delegaten instanziieren, muss das erste Argument entweder die Adresse einer Methode ein Objekt der verwalteten Klasse oder ein Zeiger auf eine Methode einen Werttyp sein. Das Argument muss benennen Sie die Methode mit der vollständigen Klasse Scope-Syntax und die Address-of-Operator angewendet.

Beim Erstellen eines Delegaten an eine globale oder statische Funktion ist nur ein Parameter erforderlich: die Funktion (optional die Adresse der Funktion).

Weitere Informationen zu Delegaten finden Sie unter

- [Vorgehensweise: Definieren und Verwenden von Delegaten (C++/CLI)](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)

- [Generische Delegaten (C++ / CLI)](../windows/generic-delegates-visual-cpp.md)

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Beispiel zeigt, wie Sie deklarieren, initialisieren und Aufrufen von Delegaten.

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

```Output
in func1 8

in func1 9

in func2 9

in func2 10

in static func3 11
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET- und UWP](../windows/component-extensions-for-runtime-platforms.md)