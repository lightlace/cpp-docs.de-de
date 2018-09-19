---
title: Satype | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.satype
dev_langs:
- C++
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 462dba3caaef53e49203eab6d006ea59d7b23c0e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42590372"
---
# <a name="satype"></a>satype

Gibt den Datentyp, der die `SAFEARRAY` Struktur.

## <a name="syntax"></a>Syntax

```cpp
[ satype(
   data_type
) ]
```

### <a name="parameters"></a>Parameter

*data_type*  
Der Datentyp für die `SAFEARRAY` -Datenstruktur, die für eine Schnittstellenmethode als Parameter übergeben wird.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter, für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

## <a name="remarks"></a>Hinweise

Die **Satype** C++-Attribut gibt den Datentyp, der die `SAFEARRAY`.

> [!NOTE]
> Eine Dereferenzierungsebene aus gelöscht wird die `SAFEARRAY` Zeiger in der generierten IDL-Datei aus, wie sie in der CPP-Datei deklariert ist.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_satype.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyModule")];
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A {
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[ID](../windows/id.md)  