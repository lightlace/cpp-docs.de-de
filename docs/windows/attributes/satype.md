---
title: Satype (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.satype
helpviewer_keywords:
- satype attribute
ms.assetid: 1716590b-6bcb-4aba-b1bc-82f7335f02c3
ms.openlocfilehash: 3d2d921e750adad0089df0d00590f256b56c732e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517688"
---
# <a name="satype"></a>satype

Gibt den Datentyp, der die `SAFEARRAY` Struktur.

## <a name="syntax"></a>Syntax

```cpp
[ satype(data_type) ]
```

### <a name="parameters"></a>Parameter

*data_type*<br/>
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

[Compilerattribute](compiler-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[ID](id.md)