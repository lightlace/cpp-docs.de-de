---
title: 'Gewusst wie: Deklarieren von Handles in systemeigenen Typen'
ms.custom: get-started-article
ms.date: 11/04/2016
f1_keywords:
- gcroot
helpviewer_keywords:
- handles, declaring
- gcroot keyword [C++]
- types [C++], declaring handles in
ms.assetid: b8c0eead-17e5-4003-b21f-b673f997d79f
ms.openlocfilehash: 4b5cd212589be04f5f9f3a5dd6d4496a8f5add2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464922"
---
# <a name="how-to-declare-handles-in-native-types"></a>Gewusst wie: Deklarieren von Handles in systemeigenen Typen

Sie können keinen Handletyp in einem systemeigenen Typ deklarieren. Vcclr.h bietet die Vorlage der typsicheren Wrapper `gcroot` zum Verweisen auf ein CLR-Objekt aus dem Heap. Mit dieser Vorlage können Sie betten Sie ein virtuelles Handle in einen systemeigenen Typ, und es behandeln, als handele es sich um den zugrunde liegenden Typ. In den meisten Fällen können Sie mithilfe der `gcroot` Objekt als eingebetteten Typ ohne eine Umwandlung. Allerdings können mit [für jedes in](../dotnet/for-each-in.md), müssen Sie mit `static_cast` um den zugrunde liegenden verwalteten Verweis abzurufen.

Die `gcroot` Vorlage wird unter Verwendung der Wertklasse System::Runtime::InteropServices::GCHandle, bietet "Handles" in den Heap der Garbage Collection implementiert. Beachten Sie, dass die Handles selbst keine Garbage Collection bereinigt werden und nicht mehr in Verwendung freigegeben werden, die durch den Destruktor der `gcroot` Klasse (der Destruktor kann nicht manuell aufgerufen werden). Wenn Sie instanziieren ein `gcroot` Objekt auf dem systemeigenen Heap, rufen Sie für die Ressource zu löschen.

Die Laufzeit behält eine Zuordnung zwischen dem Handle und dem CLR-Objekt, das es verweist. Wenn das CLR-Objekt mit dem Heap der Garbage Collection verschoben wird, gibt das Handle die neue Adresse des Objekts zurück. Eine Variable muss nicht fixiert werden, bevor sie zugewiesen ist eine `gcroot` Vorlage.

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie erstellen eine `gcroot` den systemeigenen Stapel-Objekt.

```
// mcpp_gcroot.cpp
// compile with: /clr
#include <vcclr.h>
using namespace System;

class CppClass {
public:
   gcroot<String^> str;   // can use str as if it were String^
   CppClass() {}
};

int main() {
   CppClass c;
   c.str = gcnew String("hello");
   Console::WriteLine( c.str );   // no cast required
}
```

```Output
hello
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie erstellen eine `gcroot` dem systemeigenen Heap-Objekt.

```
// mcpp_gcroot_2.cpp
// compile with: /clr
// compile with: /clr
#include <vcclr.h>
using namespace System;

struct CppClass {
   gcroot<String ^> * str;
   CppClass() : str(new gcroot<String ^>) {}

   ~CppClass() { delete str; }

};

int main() {
   CppClass c;
   *c.str = gcnew String("hello");
   Console::WriteLine( *c.str );
}
```

```Output
hello
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt, wie Sie mit `gcroot` für Verweise auf Werttypen (keine Verweistypen) in einem systemeigenen Typ mit `gcroot` auf den geschachtelten Typ.

```
// mcpp_gcroot_3.cpp
// compile with: /clr
#include < vcclr.h >
using namespace System;

public value struct V {
   String^ str;
};

class Native {
public:
   gcroot< V^ > v_handle;
};

int main() {
   Native native;
   V v;
   native.v_handle = v;
   native.v_handle->str = "Hello";
   Console::WriteLine("String in V: {0}", native.v_handle->str);
}
```

```Output
String in V: Hello
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)