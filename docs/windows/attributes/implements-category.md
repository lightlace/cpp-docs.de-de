---
title: Implements_category (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.implements_category
dev_langs:
- C++
helpviewer_keywords:
- implements_category attribute
ms.assetid: fb162df3-1ebe-43dc-a084-668d7ef8c03f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3f56562621d217e577abcf694fccb7de14fc4b56
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059173"
---
# <a name="implementscategory"></a>implements_category

Gibt die Komponentenkategorien, die von der Zielklasse implementiert.

## <a name="syntax"></a>Syntax

```cpp
[ implements_category(implements_category="uuid") ]
```

### <a name="parameters"></a>Parameter

*implements_category*<br/>
Die ID der Kategorie implementiert.

## <a name="remarks"></a>Hinweise

Die **Implements_category** C++-Attribut gibt die Komponentenkategorien, die von der Zielklasse implementiert. Dies erfolgt durch Erstellen einer Kategorie-Zuordnung und Hinzufügen von separate Einträge, die gemäß der **Implements_category** Attribut. Weitere Informationen finden Sie unter [was Komponentenkategorien und wie werden diese Aufgaben sind?](https://msdn.microsoft.com/library/windows/desktop/ms694322).

Dieses Attribut erfordert, dass die Attribute [coclass](coclass.md), [progid](progid.md), oder [vi_progid](vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden. Wenn ein einzelnes Attribut verwendet wird, werden die anderen beiden automatisch angewendet. Z. B. wenn `progid` angewendet wird, `vi_progid` und `coclass` werden ebenfalls angewendet.

## <a name="example"></a>Beispiel

Der folgende Code gibt an, dass die folgenden-implementiert Objekt die `Control` Kategorie.

```cpp
// cpp_attr_ref_implements_category.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="MyLib")];
[ coclass, implements_category("CATID_Control"),
  uuid("20a0d0cc-5172-40f5-99ae-5e032f3205ae")]
class CMyClass {};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|Eine der folgenden: `coclass`, `progid`, oder `vi_progid`|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[IMPLEMENTED_CATEGORY](../../atl/reference/category-macros.md#implemented_category)