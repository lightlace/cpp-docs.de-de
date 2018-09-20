---
title: Noncreatable | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.noncreatable
dev_langs:
- C++
helpviewer_keywords:
- noncreatable attribute
ms.assetid: 4d17937b-0bff-41af-ba57-53e18b7ab5a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 559d461a996789986dcc445d6ef510c7b179542c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46381295"
---
# <a name="noncreatable"></a>noncreatable

Definiert ein Objekt, das allein nicht instanziiert werden kann.

## <a name="syntax"></a>Syntax

```cpp
[noncreatable]
```

## <a name="remarks"></a>Hinweise

Die **Noncreatable** C++-Attribut hat die gleiche Funktionalität wie die [Noncreatable](/windows/desktop/Midl/noncreatable) MIDL-Attribut, und wird automatisch auf die generierte übergeben. IDL-Datei durch den Compiler.

Wenn dieses Attribut in einem Projekt, das ATL verwendet verwendet wird, ändert sich das Verhalten des Attributs. Zusätzlich zu den oben beschriebenen Verhalten fügt das Attribut auch die [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](../atl/reference/object-map-macros.md#object_entry_non_createable_ex_auto) Makro. Dieses Makro gibt ATL, dass das Objekt kann nicht extern erstellt werden.

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

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Klassenattribute](../windows/class-attributes.md)  
