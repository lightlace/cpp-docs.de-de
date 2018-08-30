---
title: Iid_is | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.iid_is
dev_langs:
- C++
helpviewer_keywords:
- iid_is attribute
ms.assetid: 2f9b42a9-7130-4b08-9b1e-0d5d360e10ff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 597d4c2e6fa9904906c2971c3c442a9f26779834
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43215077"
---
# <a name="iidis"></a>iid_is

Gibt die IID für die COM-Schnittstelle, die einen Schnittstellenzeiger einen verweist.

## <a name="syntax"></a>Syntax

```cpp
[ iid_is(
   "expression"
) ]
```

### <a name="parameters"></a>Parameter

*Ausdruck*  
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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  