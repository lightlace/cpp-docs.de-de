---
title: Iid_is (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.iid_is
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
ms.openlocfilehash: 176ab83bfae18ff7f43fe0860591f2d1ac50d7eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535329"
---
# <a name="iidis"></a>iid_is

Gibt die IID für die COM-Schnittstelle, die einen Schnittstellenzeiger einen verweist.

## <a name="syntax"></a>Syntax

```cpp
[ iid_is("expression") ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*<br/>
Ein Ausdruck der C-Sprache, der eine IID einer COM-Schnittstelle angibt, auf einen Schnittstellenzeiger zeigt.

## <a name="remarks"></a>Hinweise

Die **Iid_is** C++-Attribut hat die gleiche Funktionalität wie die [Iid_is](/windows/desktop/Midl/iid-is) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt die Verwendung von **Iid_is**:

```cpp
// cpp_attr_ref_iid_is.cpp
// compile with: /LD
#include "wtypes.h"
#include "unknwn.h"
[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface IFireTabCtrl : IDispatch
{
   [id(1)] HRESULT CreateInstance([in] REFIID riid,[out, iid_is("riid")]
   IUnknown ** ppvObject);
};

[module(name="ATLFIRELib")];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter,-Datenmember|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)