---
title: Switch_type (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.switch_type
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
ms.openlocfilehash: b461769d3d988efae0be7380e1e0112e3f3cf801
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407119"
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

Die **Switch_type** C++ Attribut hat die gleiche Funktionalität wie die [Switch_type](/windows/desktop/Midl/switch-type) MIDL-Attribut.

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