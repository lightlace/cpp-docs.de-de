---
title: Noncreatable (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.noncreatable
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
ms.openlocfilehash: 716cc741de92be73fc2fcdda6b019de736387efd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578359"
---
# <a name="noncreatable"></a>noncreatable

Definiert ein Objekt, das allein nicht instanziiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
[noncreatable]
```

## <a name="remarks"></a>Hinweise

Die **Noncreatable** C++-Attribut hat die gleiche Funktionalität wie die [Noncreatable](/windows/desktop/Midl/noncreatable) MIDL-Attribut, und wird automatisch auf die generierte übergeben. IDL-Datei durch den Compiler.

Wenn dieses Attribut in einem Projekt, das ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebenen Verhalten fügt das Attribut auch die [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro. Dieses Makro gibt ATL, dass das Objekt kann nicht extern erstellt werden.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_noncreatable.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLib")];

[object, uuid("11111111-1111-1111-1111-111111111111")]
__interface A
{
};

[coclass, uuid("11111111-1111-1111-1111-111111111112"), noncreatable]
class CMyClass : public A
{
   HRESULT xx();
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**coclass**|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)
