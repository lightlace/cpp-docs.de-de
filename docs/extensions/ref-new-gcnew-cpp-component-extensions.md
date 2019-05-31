---
title: ref new, gcnew (C++/CLI und C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
ms.openlocfilehash: f3dd0b73e300b44cb4f35e42683725813453d7de
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "65516645"
---
# <a name="ref-new-gcnew--ccli-and-ccx"></a>ref new, gcnew (C++/CLI und C++/CX)

Das **ref new**-Aggregatschlüsselwort ordnet eine Instanz eines Typs zu, der in der Garbage Collection erfasst wird, wenn auf das Objekt nicht mehr zugegriffen werden kann, wodurch ein Handle ([^](handle-to-object-operator-hat-cpp-component-extensions.md)) zum zugeordneten Objekt zurückgegeben wird.

## <a name="all-runtimes"></a>Alle Laufzeiten

Bei Arbeitsspeicher für eine Instanz eines per **ref new** zugeordneten Typs wird die Zuordnung automatisch aufgehoben.

Ein **ref new**-Vorgang löst `OutOfMemoryException` aus, wenn kein Arbeitsspeicher zugeordnet werden kann.

Weitere Informationen über die Zuordnung und Aufhebung der Zuordnung von Arbeitsspeicher für native C++-Typen finden Sie unter [Operatoren „new“ und „delete“](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Windows-Runtime

Verwenden Sie **ref new**, um Arbeitsspeicher für Windows-Runtime-Objekte zuzuordnen, deren Lebensdauer Sie automatisch verwalten möchten. Die Zuordnung des Objekts wird automatisch aufgehoben, wenn sein Verweiszähler bei 0 liegt. Dies ist der Fall, nachdem die letzte Kopie des Verweises den Gültigkeitsbereich verlassen hat. Weitere Informationen finden Sie unter [Referenzklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Der Arbeitsspeicher für einen verwalteten Typ (Verweis- oder Werttyp) wird durch **gcnew** zugeordnet, die Aufhebung der Zuordnung erfolgt über die Garbage Collection.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Das folgende Beispiel verwendet **gcnew** zum Zuordnen eines Message-Objekts.

```cpp
// mcppv2_gcnew_1.cpp
// compile with: /clr
ref struct Message {
   System::String^ sender;
   System::String^ receiver;
   System::String^ data;
};

int main() {
   Message^ h_Message  = gcnew Message;
  //...
}
```

Das folgende Beispiel verwendet **gcnew** zum Erstellen eines geschachtelten Werttyps, der wie ein Verweistyp verwendet werden soll.

```cpp
// example2.cpp : main project file.
// compile with /clr
using namespace System;
value class Boxed {
    public:
        int i;
};
int main()
{
    Boxed^ y = gcnew Boxed;
    y->i = 32;
    Console::WriteLine(y->i);
    return 0;
}
```

```Output
32
```

## <a name="see-also"></a>Siehe auch

[Komponentenerweiterungen für .NET und UWP](component-extensions-for-runtime-platforms.md)