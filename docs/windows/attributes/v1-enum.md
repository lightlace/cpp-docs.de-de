---
title: v1_enum (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 9771181399a1abaef2e273665e8b267a2065efea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632426"
---
# <a name="v1enum"></a>v1_enum

Wird angewiesen, der angegebene enumerierten Typ als eine 32-Bit-Entität statt der 16-Bit-Standard übertragen werden.

## <a name="syntax"></a>Syntax

```cpp
[v1_enum]
```

## <a name="remarks"></a>Hinweise

Die **v1_enum** C++-Attribut hat die gleiche Funktionalität wie die [v1_enum](/windows/desktop/Midl/v1-enum) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung der **v1_enum**:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Enumerationstyp|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)