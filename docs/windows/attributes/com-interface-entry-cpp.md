---
title: COM_INTERFACE_ENTRY (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 06377d9fc3f0eff1487c5d920d257d68bece46b2
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791363"
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)

Fügt einen Eintrag Schnittstelle in der COM-Zuordnung der Zielklasse.

## <a name="syntax"></a>Syntax

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>Parameter

*COM_INTERFACE_ENTRY*<br/>
Eine Zeichenfolge mit den tatsächlichen Text des Eintrags. Eine Liste der möglichen Werte, finden Sie unter [COM_INTERFACE_ENTRY-Makros](../../atl/reference/com-interface-entry-macros.md).

## <a name="remarks"></a>Hinweise

Die **Com_interface_entry** fügt C++-Attribut den ungekürzt Inhalt einer Zeichenfolge in die Zuordnung des COM-Schnittstelle des Zielobjekts. Wenn das Attribut angewendet wird, sobald auf das Zielobjekt, der Eintrag in den Anfang der vorhandenen schnittstellenzuordnung eingefügt wird. Wenn das Attribut auf dem gleichen Zielobjekt wiederholt angewendet wird, werden die Einträge am Anfang die schnittstellenzuordnung in der Reihenfolge eingefügt, die sie empfangen werden.

Dieses Attribut erfordert, dass die [Co-Klasse](coclass.md), [progid](progid.md), oder [Vi_progid](vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch angewendet werden mit dem gleichen Element. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Z. B. wenn `progid` angewendet wird, `vi_progid` und `coclass` werden ebenfalls angewendet.

Da die erste Verwendung von **Com_interface_entry** bewirkt, dass die neue Schnittstelle, am Anfang der schnittstellenzuordnung eingefügt werden soll es muss eine der folgenden COM_INTERFACE_ENTRY Typen sein:

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

Zusätzliche Verwendungen der **Com_interface_entry** Attribut kann alle unterstützte COM_INTERFACE_ENTRY-Typen verwenden.

Diese Einschränkung ist notwendig, da den ersten Eintrag in die schnittstellenzuordnung von ATL als Identität verwendet `IUnknown`; aus diesem Grund der Eintrag muss eine gültige Schnittstelle sein. Das folgende Codebeispiel ist beispielsweise ungültig, da der erste Eintrag in die schnittstellenzuordnung eine tatsächliche COM-Schnittstelle nicht angegeben ist.

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>Beispiel

Der folgende Code fügt zwei Einträge der vorhandenen COM-Schnittstelle Zuordnung von `CMyBaseClass`. Die erste ist eine Standardschnittstelle, und die zweite Blendet die `IDebugTest` Schnittstelle.

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")  
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

Der resultierende COM-Objekt-Zuordnung für `CMyBaseClass` lautet wie folgt:

```cpp
BEGIN_COM_MAP(CMyClass)  
    COM_INTERFACE_ENTRY (IMyClass)  
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)  
    COM_INTERFACE_ENTRY(IMyClass)  
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)  
    COM_INTERFACE_ENTRY(IDebugTest)  
    COM_INTERFACE_ENTRY(IProvideClassInfo)  
END_COM_MAP()  
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)  