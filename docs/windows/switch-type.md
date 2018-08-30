---
title: Switch_type | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.switch_type
dev_langs:
- C++
helpviewer_keywords:
- switch_type attribute
ms.assetid: e24544dc-b3bc-48ae-b249-f967db49271e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: faa2a3be7260eecb16599db967336bcb7b774c99
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200125"
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

*Typ*  
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

Finden Sie unter den [Fall](../windows/case-cpp.md) Beispiel für ein Beispiel für die Verwendung von **Switch_type**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**typedef**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[export](../windows/export.md)  