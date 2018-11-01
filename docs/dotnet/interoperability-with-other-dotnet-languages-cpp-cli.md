---
title: Interoperabilität mit anderen .NET-Sprachen (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- C++, indexers
- indexers, consuming C#
- as C# keyword [C++]
- is C# keyword [C++]
- lock statement
- lock C# keyword [C++]
ms.assetid: a5902cf8-a14d-4559-aefb-c178615d45bb
ms.openlocfilehash: bfc220852563d8c8f96108e05344c507b63875ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581394"
---
# <a name="interoperability-with-other-net-languages-ccli"></a>Interoperabilität mit anderen .NET-Sprachen (C++/CLI)

Die Themen in diesem Abschnitt zeigen, wie zum Erstellen von Assemblys in Visual C++, die Nutzung aus oder bieten Funktionen für Assemblys, die in c# oder Visual Basic geschrieben wird.

## <a name="consume_indexer"></a> Verwenden eines c#-Indexers

Visual C++ sind keine Indexer enthalten. Er verfügt über Eigenschaften indiziert. Um eine c#-Indexers nutzen zu können, Zugriff auf den Indexer, als handele es sich um eine indizierte Eigenschaft.

Weitere Informationen zu Indexern finden Sie unter:

- [Indexer](/dotnet/csharp/programming-guide/indexers/index)

### <a name="example"></a>Beispiel

Das folgende C#-Programm definiert einen Indexer.

```csharp
// consume_cs_indexers.cs
// compile with: /target:library
using System;
public class IndexerClass {
   private int [] myArray = new int[100];
   public int this [int index] {   // Indexer declaration
      get {
         // Check the index limits.
         if (index < 0 || index >= 100)
            return 0;
         else
            return myArray[index];
      }
      set {
         if (!(index < 0 || index >= 100))
            myArray[index] = value;
      }
   }
}
/*
// code to consume the indexer
public class MainClass {
   public static void Main() {
      IndexerClass b = new IndexerClass();

      // Call indexer to initialize elements 3 and 5
      b[3] = 256;
      b[5] = 1024;
      for (int i = 0 ; i <= 10 ; i++)
         Console.WriteLine("Element #{0} = {1}", i, b[i]);
   }
}
*/
```

### <a name="example"></a>Beispiel

Dieses Visual C++-Programm verwendet den Indexer.

```cpp
// consume_cs_indexers_2.cpp
// compile with: /clr
#using "consume_cs_indexers.dll"
using namespace System;

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->default[0] = 21;
   for (int i = 0 ; i <= 10 ; i++)
      Console::WriteLine("Element #{0} = {1}", i, ic->default[i]);
}
```

```Output
Element #0 = 21
Element #1 = 0
Element #2 = 0
Element #3 = 0
Element #4 = 0
Element #5 = 0
Element #6 = 0
Element #7 = 0
Element #8 = 0
Element #9 = 0
Element #10 = 0
```

## <a name="implement_isas"></a> Implementieren von wird auch als c#-Schlüsselwörter

In diesem Thema wird gezeigt, wie zum Implementieren der Funktionen des die `is` und `as` C#-Schlüsselwörter in Visual C++.

### <a name="example"></a>Beispiel

```cpp
// CS_is_as.cpp
// compile with: /clr
using namespace System;

interface class I {
public:
   void F();
};

ref struct C : public I {
   virtual void F( void ) { }
};

template < class T, class U >
Boolean isinst(U u) {
   return dynamic_cast< T >(u) != nullptr;
}

int main() {
   C ^ c = gcnew C();
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)

   // simulate 'as':
   Object ^ o = "f";
   if ( isinst< String ^ >(o) )
      Console::WriteLine("o is a string");
}
```

```Output
o is a string
```

## <a name="implement_locak"></a> Implementieren der C#-Schlüsselworts "Lock"

In diesem Thema wird gezeigt, wie der C#-Implementierung `lock` -Schlüsselwort in Visual C++.

Sie können auch die `lock` Klasse in der C++-Unterstützungsbibliothek. Finden Sie unter [Synchronisierung (Lock-Klasse)](../dotnet/synchronization-lock-class.md) für Weitere Informationen.

### <a name="example"></a>Beispiel

```cpp
// CS_lock_in_CPP.cpp
// compile with: /clr
using namespace System::Threading;
ref class Lock {
   Object^ m_pObject;
public:
   Lock( Object ^ pObject ) : m_pObject( pObject ) {
      Monitor::Enter( m_pObject );
   }
   ~Lock() {
      Monitor::Exit( m_pObject );
   }
};

ref struct LockHelper {
   void DoSomething();
};

void LockHelper::DoSomething() {
   // Note: Reference type with stack allocation semantics to provide
   // deterministic finalization

   Lock lock( this );
   // LockHelper instance is locked
}

int main()
{
   LockHelper lockHelper;
   lockHelper.DoSomething();
   return 0;
}
```

## <a name="see-also"></a>Siehe auch

[.NET-Programmierung mit C++/CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
