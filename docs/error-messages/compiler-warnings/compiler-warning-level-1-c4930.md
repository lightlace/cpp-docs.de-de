---
title: Compilerwarnung (Stufe 1) C4930
ms.date: 11/04/2016
f1_keywords:
- C4930
helpviewer_keywords:
- C4930
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
ms.openlocfilehash: b21cc6364692eb2f3b1d56b03d175df1f2ad7ee8
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2019
ms.locfileid: "74050279"
---
# <a name="compiler-warning-level-1-c4930"></a>Compilerwarnung (Stufe 1) C4930

"Prototyp": eine prototypisierte Funktion wird nicht aufgerufen (war eine Variablen Definition beabsichtigt?)

Der Compiler hat einen nicht verwendeten Funktionsprototyp erkannt. Wenn der Prototyp als Variablen Deklaration gedacht war, entfernen Sie die Klammern öffnende/schließende Klammern.

Im folgenden Beispiel wird C4930 generiert:

```cpp
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

C4930 kann auch auftreten, wenn der Compiler nicht zwischen einer Funktions prototypdeklaration und einem Funktions aufrufzeichen unterscheiden kann.

Im folgenden Beispiel wird C4930 generiert:

```cpp
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

Im obigen Beispiel wird das Ergebnis einer Methode, die keine Argumente annimmt, als Argument an den Konstruktor einer unbenannten lokalen Klassen Variablen übergeben. Der-Befehl kann eindeutig sein, indem entweder die lokale Variable benannt oder der Methodenaufrufe mit einer Objektinstanz und dem entsprechenden Zeiger auf Member-Operator vorangestellt werden.