---
title: Transmit_as (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.transmit_as
helpviewer_keywords:
- transmit_as attribute
ms.assetid: 53d0b8ab-5b06-423e-83eb-3d01a10424b2
ms.openlocfilehash: e432d1a8f39cbc5e12f192ed7b07c29421bc403e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59032101"
---
# <a name="transmitas"></a>transmit_as

Weist den Compiler einen dargestellten Typ, den Client- und serveranwendungen bearbeiten zu können, müssen, mit einem übertragenen Typ zuordnen.

## <a name="syntax"></a>Syntax

```cpp
[ transmit_as(type) ]
```

### <a name="parameters"></a>Parameter

*Typ*<br/>
Gibt den Datentyp, der zwischen Client und Server übertragen werden.

## <a name="remarks"></a>Hinweise

Die **Transmit_as** C++ Attribut hat die gleiche Funktionalität wie die [Transmit_as](/windows/desktop/Midl/transmit-as) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code veranschaulicht die Verwendung der der **Transmit_as** Attribut:

```cpp
// cpp_attr_ref_transmit_as.cpp
// compile with: /LD
#include "windows.h"
[module(name="MyLibrary")];

[export] typedef struct _TREE_NODE_TYPE {
unsigned short data;
struct _TREE_NODE_TYPE * left;
struct _TREE_NODE_TYPE * right;
} TREE_NODE_TYPE;

[export] struct PACKED_NODE {
   unsigned short data;   // same as normal node
   int index;   // array index of parent
};

// A left node recursive built array of
// the nodes in the tree.  Can be unpacked with
// that knowledge
[export] typedef struct _TREE_XMIT_TYPE {
   int count;
   [size_is(count)] PACKED_NODE node[];
} TREE_XMIT_TYPE;

[transmit_as(TREE_XMIT_TYPE)] typedef TREE_NODE_TYPE * TREE_TYPE;
```

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