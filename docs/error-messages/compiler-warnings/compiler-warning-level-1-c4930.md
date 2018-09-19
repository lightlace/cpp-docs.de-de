---
title: Compilerwarnung (Stufe 1) C4930 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4930
dev_langs:
- C++
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33c202cc6f062ac13bef3a73e4509e4ba870e2d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090190"
---
# <a name="compiler-warning-level-1-c4930"></a>Compilerwarnung (Stufe 1) C4930

'Prototyp': Funktion mit Prototyp nicht aufgerufen (war eine Variablendefinition gemeint?)

Der Compiler hat einen nicht verwendeten Funktionsprototyp. Wenn der Prototyp als Deklaration einer Variablen, entfernen Sie die Klammern öffnen/schließen.

Im folgende Beispiel wird die C4930 generiert:

```
// C4930.cpp
// compile with: /W1
class Lock {
public:
   int i;
};

void f() {
   Lock theLock();   // C4930
   // try the following line instead
   // Lock theLock;
}

int main() {
}
```

C4930 kann auch auftreten, wenn der Compiler zwischen der Deklaration einer Funktion Prototyp und eines Funktionsaufrufs unterscheiden kann.

Im folgende Beispiel wird die C4930 generiert:

```
// C4930b.cpp
// compile with: /EHsc /W1

class BooleanException
{
   bool _result;

public:
   BooleanException(bool result)
      : _result(result)
   {
   }

   bool GetResult() const
   {
      return _result;
   }
};

template<class T = BooleanException>
class IfFailedThrow
{
public:
   IfFailedThrow(bool result)
   {
      if (!result)
      {
         throw T(result);
      }
   }
};

class MyClass
{
public:
   bool MyFunc()
   {
      try
      {
         IfFailedThrow<>(MyMethod()); // C4930

         // try one of the following lines instead
         // IfFailedThrow<> ift(MyMethod());
         // IfFailedThrow<>(this->MyMethod());
         // IfFailedThrow<>((*this).MyMethod());

         return true;
      }
      catch (BooleanException e)
      {
         return e.GetResult();
      }
   }

private:
   bool MyMethod()
   {
      return true;
   }
};

int main()
{
   MyClass myClass;
   myClass.MyFunc();
}
```

Im obigen Beispiel ist das Ergebnis einer Methode, die keine Argumente annimmt an den Konstruktor einer unbenannten lokale Klasse-Variable als Argument übergeben. Der Aufruf kann eindeutig bestimmt werden, durch die lokale Variable erhält oder wenn der Aufruf der Methode mit einer Objektinstanz zusammen mit den entsprechenden Pointer-to-Member-Operator mit einem Präfix.