---
title: Pragma (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pragma
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
ms.openlocfilehash: 159e1570c2bde07bb4df8fa904a519e8e0018a6a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041188"
---
# <a name="pragma"></a>pragma

Gibt die angegebene Zeichenfolge in der generierten IDL-Datei ohne die Verwendung von Anführungszeichen.

## <a name="syntax"></a>Syntax

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Parameter

*pragma_statement*<br/>
Das Pragma, das in der generierten IDL-Datei aufgenommen werden sollen.

## <a name="remarks"></a>Hinweise

Die **Pragma** C++-Attribut hat die gleiche Funktionalität wie die [Pragma](/windows/desktop/Midl/pragma) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)