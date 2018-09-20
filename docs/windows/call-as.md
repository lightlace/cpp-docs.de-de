---
title: Call_as | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.call_as
dev_langs:
- C++
helpviewer_keywords:
- call_as attribute
ms.assetid: a09d7f1f-353b-4870-9b45-f0284161695d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 072c5b34d539e695f534dbafdf4afcd69a2272ab
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415680"
---
# <a name="callas"></a>call_as

Ermöglicht einem [lokalen](../windows/local-cpp.md) Funktion, um eine remote-Funktion, damit die lokale Funktion aufgerufen wird, wenn die remote-Funktion aufgerufen wird, zugeordnet werden.

## <a name="syntax"></a>Syntax

```cpp
[ call_as(
   function
) ]
```

### <a name="parameters"></a>Parameter

*function*<br/>
Die lokale Funktion, die aufgerufen werden, wenn eine remote-Funktion aufgerufen wird, werden sollen.

## <a name="remarks"></a>Hinweise

Die **Call_as** C++-Attribut hat die gleiche Funktionalität wie die [Call_as](/windows/desktop/Midl/call-as) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie verwenden können **Call_as** , eine Funktion nicht remotefähige zuzuordnen (`f1`) an eine remotefähige-Funktion (`Remf1`):

```cpp
// cpp_attr_ref_call_as.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[dual, uuid("00000000-0000-0000-0000-000000000001")]
__interface IMInterface {
   [local] HRESULT f1 ( int i );
   [call_as(f1)] HRESULT Remf1 ( int i );
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Methodenattribut](../windows/method-attributes.md)<br/>
[local](../windows/local-cpp.md)  