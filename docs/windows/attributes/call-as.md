---
title: Call_as (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 7ca6336a79b3e218e1e3a68112f1c12d7e4822a4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790596"
---
# <a name="callas"></a>call_as

Ermöglicht einem [lokalen](local-cpp.md) Funktion, um eine remote-Funktion, damit die lokale Funktion aufgerufen wird, wenn die remote-Funktion aufgerufen wird, zugeordnet werden.

## <a name="syntax"></a>Syntax

```cpp
[ call_as(function) ]
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

Weitere Informationen zu den attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[local](local-cpp.md)  