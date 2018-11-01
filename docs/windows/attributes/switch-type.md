---
title: Switch_type (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: e8827fe576282b86f1d3bc633ec7f9f954c015b7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448788"
---
# <a name="switchtype"></a>switch_type

Gibt den Typ der Variablen als die union Discriminant verwendet.

## <a name="syntax"></a>Syntax

```cpp
[switch_type(
type
}]
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
Der Switchtyp kann es sich um eine ganze Zahl "," Zeichen "," Boolesch "oder" Enumeration-Typ sein.

## <a name="remarks"></a>Hinweise

Die **Switch_type** C++-Attribut hat die gleiche Funktionalität wie die [Switch_type](/windows/desktop/Midl/switch-type) MIDL-Attribut.

C++-Attribute unterstützen keine [gekapselt Unions](/windows/desktop/Midl/encapsulated-unions). [Nonencapsulated Unions](/windows/desktop/Midl/nonencapsulated-unions) werden nur in der folgenden Form unterstützt:

```cpp
// cpp_attr_ref_switch_type.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLibrary")];
[ export ]
struct SizedValue2 {
   [switch_type("char"), switch_is(kind)] union {
      [case(1), string]
         wchar_t* wval;
      [default, string]
         char* val;
   };
   char kind;
};
```

## <a name="example"></a>Beispiel

Finden Sie unter den [Fall](case-cpp.md) Beispiel für ein Beispiel für die Verwendung von **Switch_type**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**typedef**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[export](export.md)