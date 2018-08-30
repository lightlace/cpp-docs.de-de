---
title: aggregierbaren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.aggregatable
dev_langs:
- C++
helpviewer_keywords:
- aggregatable attribute
ms.assetid: 9253a46a-cd76-41f2-b3b6-86f709bb069c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9d65f77126ceb4268d41610c6d5fe3a07968d02
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200567"
---
# <a name="aggregatable"></a>aggregatable

Gibt an, dass die Klasse Aggregation unterstützt.

## <a name="syntax"></a>Syntax

```cpp
[ aggregatable(
   value
) ]
```

### <a name="parameters"></a>Parameter

*Wert* (optional)  
Ein Parameter, um anzugeben, wenn das COM-Objekt aggregiert werden können:

- `never` Das COM-Objekt kann nicht aggregiert werden.

- `allowed` Das COM-Objekt kann direkt erstellt werden, oder es aggregiert werden kann. Dies ist die Standardeinstellung.

- `always` Das COM-Objekt kann nicht direkt erstellt werden und nur aggregiert werden kann. Beim Aufruf `CoCreateInstance` für dieses Objekt müssen Sie angeben, des aggregieren Objekts `IUnknown` Schnittstelle (das steuernde `IUnknown`).

## <a name="remarks"></a>Hinweise

Die **aggregierbaren** C++-Attribut hat die gleiche Funktionalität wie die [aggregierbaren](/windows/desktop/Midl/aggregatable) MIDL-Attribut. Dies bedeutet, dass der Compiler übergibt die **aggregierbaren** Attribut mithilfe der generierten IDL-Datei.

Dieses Attribut erfordert, dass die Attribute [coclass](../windows/coclass.md), [progid](../windows/progid.md), oder [vi_progid](../windows/vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Z. B. wenn `progid` angewendet wird, `vi_progid` und `coclass` werden ebenfalls angewendet.

### <a name="atl-projects"></a>ATL-Projekte

Wenn dieses Attribut in einem Projekt verwendet wird, das ATL verwendet, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebenen Verhalten fügt das Attribut auch eine der folgenden Makros hinzu Zielklasse:

|Parameterwert|Eingefügte-Makro|
|---------------------|--------------------|
|`Never`|[DECLARE_NOT_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_not_aggregatable)|
|`Allowed`|[DECLARE_POLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_poly_aggregatable)|
|`Always`|[DECLARE_ONLY_AGGREGATABLE](../atl/reference/aggregation-and-class-factory-macros.md#declare_only_aggregatable)|

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_aggregatable.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyModule")];

[ coclass, aggregatable(allowed),
  uuid("1a8369cc-1c91-42c4-befa-5a5d8c9d2529")]
class CMyClass {};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[Aggregation](/windows/desktop/com/aggregation)  