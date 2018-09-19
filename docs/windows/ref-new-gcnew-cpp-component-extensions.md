---
title: REF neu, Gcnew (Komponentenerweiterungen für C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- gcnew
- ref new
- gcnew_cpp
dev_langs:
- C++
helpviewer_keywords:
- ref new keyword (C++)
- gcnew keyword [C++]
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c31cda7c074b06025051661d27f00d2624721d0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596157"
---
# <a name="ref-new-gcnew--c-component-extensions"></a>ref new, gcnew (Komponentenerweiterungen für C++)

Die **Ref neue** -aggregatschlüsselwort ordnet eine Instanz eines Typs, der die Garbage Collection, die ein Handle zurückgibt, wenn das Objekt wird nicht zugegriffen werden kann ([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)) auf das zugeordnete Objekt.

## <a name="all-runtimes"></a>Alle Laufzeiten

Arbeitsspeicher für eine Instanz eines Typs, die von zugeordnet ist **Ref neue** wird die Zuordnung automatisch aufgehoben.

Ein **Ref neue** -Vorgang löst `OutOfMemoryException` es kann kein Arbeitsspeicher belegt ist.

Weitere Informationen darüber, wie der Arbeitsspeicher für systemeigene C++-Typen zugeordnet und freigegeben wird, finden Sie unter [der neuen "und" delete](../cpp/new-and-delete-operators.md).

## <a name="windows-runtime"></a>Windows-Runtime

Verwendung **Ref neue** Zuweisen von Arbeitsspeicher für die Windows-Runtime-Objekte, deren Lebensdauer automatisch verwaltet werden soll. Die Zuordnung des Objekts wird automatisch aufgehoben, wenn sein Verweiszähler bei 0 liegt. Dies ist der Fall, nachdem die letzte Kopie des Verweises den Gültigkeitsbereich verlassen hat. Weitere Informationen finden Sie unter [Verweisklassen und Strukturen](../cppcx/ref-classes-and-structs-c-cx.md).

### <a name="requirements"></a>Anforderungen

Compileroption: `/ZW`

## <a name="common-language-runtime"></a>Common Language Runtime

Arbeitsspeicher für einen verwalteten Typ (Typ: Verweis- oder Werttyp) wird zugewiesen, indem Sie **Gcnew**, und mithilfe der Garbagecollection freigegeben.

### <a name="requirements"></a>Anforderungen

Compileroption: `/clr`

### <a name="examples"></a>Beispiele

Im folgenden Beispiel wird **Gcnew** ein Message-Objekt zugewiesen werden.

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

Im folgenden Beispiel wird **Gcnew** einen geschachtelter Werttyp für die Verwendung, wie einem Verweistyp erstellen.

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

[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)