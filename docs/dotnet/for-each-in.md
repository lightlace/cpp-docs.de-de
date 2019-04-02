---
title: for each, in
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::foreach
- for
- each
- in
helpviewer_keywords:
- for each keyword [C++]
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
ms.openlocfilehash: b1dfe3a32f88c0e9456e3d73c31c533911f8d3ac
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58770690"
---
# <a name="for-each-in"></a>for each, in

Durchläuft ein Array oder eine Auflistung. Dieses nicht standardmäßige Schlüsselwort ist sowohl in C++/CLI und nativen C++-Projekten verfügbar. Seine Verwendung wird jedoch nicht empfohlen. Beachten Sie, mithilfe eines Standarddialogfelds [bereichsbasiert für Anweisung (C++)](../cpp/range-based-for-statement-cpp.md) stattdessen.

## <a name="all-runtimes"></a>Alle Laufzeiten

### <a name="syntax"></a>Syntax

> **für jede (** *Typ* *Bezeichner* **in** *Ausdruck* **) {}**<br/>
> &nbsp;&nbsp;&nbsp;&nbsp;*Anweisungen*<br/>
> **}**

### <a name="parameters"></a>Parameter

*Typ*<br/>
Der `identifier`-Typ.

*identifier*<br/>
Die Iterationsvariable, die das Auflistungselement darstellt.  Wenn `identifier` ist eine [Verweisoperator nachverfolgung](../extensions/tracking-reference-operator-cpp-component-extensions.md), können Sie das Element ändern.

*expression*<br/>
Ein Arrayausdruck oder eine Auflistung. Das Auflistungselement muss zulassen, dass der Compiler es in den Typ `identifier` konvertieren kann.

*statements*<br/>
Eine oder mehrere auszuführende Anweisungen.

### <a name="remarks"></a>Hinweise

Die `for each`-Anweisung wird zum Durchlaufen einer Auflistung verwendet. Sie können Elemente in einer Auflistung ändern, aber keine Elemente hinzufügen oder löschen.

Die *Anweisungen* für jedes Element in das Array oder einer Auflistung ausgeführt werden. Nachdem die Iteration alle Elemente in der Auflistung durchlaufen hat, wird die Steuerung an die nächste Anweisung, die auf den `for each`-Block folgt, übergeben.

`for each` und `in` sind [kontextbezogenen Schlüsselwörtern](../extensions/context-sensitive-keywords-cpp-component-extensions.md).

Weitere Informationen finden Sie unter: 

- [Eine C++-Standardbibliotheksauflistung mit der for-each-Klausel durchlaufen](../dotnet/iterating-over-stl-collection-by-using-for-each.md)

- [Vorgehensweise: Durchlaufen von Arrays mit für die einzelnen](../dotnet/how-to-iterate-over-arrays-with-for-each.md)

- [Vorgehensweise: Durchlaufen einer generischen Auflistung mit für die einzelnen](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)

- [Vorgehensweise: Durchlaufen einer benutzerdefinierten Sammlung mit für die einzelnen](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)

## <a name="windows-runtime"></a>Windows-Runtime

### <a name="requirements"></a>Anforderungen

Compileroption: **/ZW**

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie `for each` zum Durchlaufen einer Zeichenfolge verwendet wird.

```cpp
// for_each_string1.cpp
// compile with: /ZW
#include <stdio.h>
using namespace Platform;

ref struct MyClass {
   property String^ MyStringProperty;
};

int main() {
   String^ MyString = ref new String("abcd");

   for each ( char c in MyString )
      wprintf("%c", c);

   wprintf("/n");

   MyClass^ x = ref new MyClass();
   x->MyStringProperty = "Testing";

   for each( char c in x->MyStringProperty )
      wprintf("%c", c);
}
```

**Ausgabe**

```Output
abcd

Testing
```

## <a name="common-language-runtime"></a>Common Language Runtime

**Hinweise**

Die CLR-Syntax ist identisch mit der **alle Laufzeiten** Syntax, mit Ausnahme der wie folgt.

*expression*<br/>
Ein verwalteter Arrayausdruck oder eine Auflistung. Das Auflistungselement muss zulassen, so, dass der Compiler von konvertieren kann <xref:System.Object> auf die *Bezeichner* Typ.

*Ausdruck* ergibt ein Typ, der implementiert <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, oder ein Typ, definiert ein `GetEnumerator` Methode, die entweder einen Typ zurückgibt, implementiert <xref:System.Collections.IEnumerator> oder alle Methoden, die in definiertendeklariert`IEnumerator`.

### <a name="requirements"></a>Anforderungen

Compileroption: **/clr**

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie `for each` zum Durchlaufen einer Zeichenfolge verwendet wird.

```cpp
// for_each_string2.cpp
// compile with: /clr
using namespace System;

ref struct MyClass {
   property String ^ MyStringProperty;
};

int main() {
   String ^ MyString = gcnew String("abcd");

   for each ( Char c in MyString )
      Console::Write(c);

   Console::WriteLine();

   MyClass ^ x = gcnew MyClass();
   x->MyStringProperty = "Testing";

   for each( Char c in x->MyStringProperty )
      Console::Write(c);
}
```

**Ausgabe**

```Output
abcd

Testing
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für Laufzeitplattformen](../extensions/component-extensions-for-runtime-platforms.md)
