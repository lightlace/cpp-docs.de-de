---
title: Benutzerdefinierte Operatoren (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: cf80eb4c440c1308e8ea06a563c18569e4e4ddf2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774567"
---
# <a name="user-defined-operators-ccli"></a>Benutzerdefinierte Operatoren (C++/CLI)

Benutzerdefinierte Operatoren für verwaltete Typen sind als statische Member oder Instanzmember oder im globalen Gültigkeitsbereich zulässig. Es gibt jedoch nur statische Operatoren Zugriff über Metadaten-Clients, die in einer anderen Sprache als Visual C++ geschrieben sind.

In einem Referenztyp muss einer der Parameter eines statischen, benutzerdefinierten Operators eines der folgenden sein:

- Ein Handle (`type` ^) mit einer Instanz des einschließenden Typs.

- Ein Verweis Typ Dereferenzierung (`type`^ & oder ^ %) Um ein Handle für eine Instanz des einschließenden Typs.

In einen Werttyp handelt muss einer der Parameter eines statischen, benutzerdefinierten Operators eines der folgenden sein:

- Des gleichen Typs wie der einschließende Werttyp.

- Ein Typ Zeigerdereferenzierung (`type`^) in den einschließenden Typ.

- Ein Verweis Typ Dereferenzierung (`type`% oder `type`&) in den einschließenden Typ.

- Ein Verweis Typ Dereferenzierung (`type`^ % oder `type`^ &) an das Handle.

Sie können die folgenden Operatoren definieren:

|Operator|Der unäre/binäre Forms?|
|--------------|--------------------------|
|!|Unär|
|!=|Binär|
|%|Binär|
|&|Unär und binär|
|&&|Binär|
|*|Unär und binär|
|+|Unär und binär|
|++|Unär|
|,|Binär|
|-|Unär und binär|
|--|Unär|
|->|Unär|
|/|Binär|
|<|Binär|
|<<|Binär|
|\<=|Binär|
|=|Binär|
|==|Binär|
|>|Binär|
|>=|Binär|
|>>|Binär|
|^|Binär|
|False|Unär|
|true|Unär|
|&#124;|Binär|
|&#124;&#124;|Binär|
|~|Unär|

## <a name="example"></a>Beispiel

```cpp
// mcppv2_user-defined_operators.cpp
// compile with: /clr
using namespace System;
public ref struct X {
   X(int i) : m_i(i) {}
   X() {}

   int m_i;

   // static, binary, user-defined operator
   static X ^ operator + (X^ me, int i) {
      return (gcnew X(me -> m_i + i));
   }

   // instance, binary, user-defined operator
   X^ operator -( int i ) {
      return gcnew X(this->m_i - i);
   }

   // instance, unary, user-defined pre-increment operator
   X^ operator ++() {
      return gcnew X(this->m_i++);
   }

   // instance, unary, user-defined post-increment operator
   X^ operator ++(int i) {
      return gcnew X(this->m_i++);
   }

   // static, unary user-defined pre- and post-increment operator
   static X^ operator-- (X^ me) {
      return (gcnew X(me -> m_i - 1));
   }
};

int main() {
   X ^hX = gcnew X(-5);
   System::Console::WriteLine(hX -> m_i);

   hX = hX + 1;
   System::Console::WriteLine(hX -> m_i);

   hX = hX - (-1);
   System::Console::WriteLine(hX -> m_i);

   ++hX;
   System::Console::WriteLine(hX -> m_i);

   hX++;
   System::Console::WriteLine(hX -> m_i);

   hX--;
   System::Console::WriteLine(hX -> m_i);

   --hX;
   System::Console::WriteLine(hX -> m_i);
}
```

```Output
-5
-4
-3
-2
-1
-2
-3
```

## <a name="example"></a>Beispiel

Das folgende Beispiel veranschaulicht die Operatorsynthese, die nur verfügbar ist, bei der Verwendung **"/ CLR"** kompiliert. Operatorsynthese das Formular Zuweisung eines binären Operators erstellt, sofern nicht definiert, in der linken Seite des Zuweisungsoperators einen CLR-Typ hat.

```cpp
// mcppv2_user-defined_operators_2.cpp
// compile with: /clr
ref struct A {
   A(int n) : m_n(n) {};
   static A^ operator + (A^ r1, A^ r2) {
      return gcnew A( r1->m_n + r2->m_n);
   };
   int m_n;
};

int main() {
   A^ a1 = gcnew A(10);
   A^ a2 = gcnew A(20);

   a1 += a2;   // a1 = a1 + a2   += not defined in source
   System::Console::WriteLine(a1->m_n);
}
```

```Output
30
```

## <a name="see-also"></a>Siehe auch

[Klassen und Strukturen](../extensions/classes-and-structs-cpp-component-extensions.md)
