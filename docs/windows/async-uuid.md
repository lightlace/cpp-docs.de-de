---
title: Async_uuid | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.async_uuid
dev_langs:
- C++
helpviewer_keywords:
- async_uuid attribute
ms.assetid: 235cb0d7-be58-4dd9-983c-e2a21bbc42c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 029528baabcc32c14fb6b35e4a13f4118602d5d5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417799"
---
# <a name="asyncuuid"></a>async_uuid

Gibt an, die UUID, die den MIDL-Compiler definiert synchrone und asynchrone Versionen einer COM-Schnittstelle weiterleitet.

## <a name="syntax"></a>Syntax

```cpp
[async_uuid (
   uuid
)]
```

### <a name="parameters"></a>Parameter

*uuid*<br/>
Eine UUID, die die Version der Schnittstelle angibt.

## <a name="remarks"></a>Hinweise

Die **Async_uuid** C++-Attribut hat die gleiche Funktionalität wie die [Async_uuid](/windows/desktop/Midl/async-uuid) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_async_uuid.cpp
// compile with: /LD
#include <Windows.h>
[module(name="Test")];
[object, uuid("9e66a290-4365-11d2-a997-00c04fa37ddb"),
async_uuid("e8583106-38fd-487e-912e-4fc8645c677e")]
__interface ICustom {
   HRESULT Custom([in] long l, [out, retval] long *pLong);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|`interface`|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|**Duale**, **Disp-Schnittstelle**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Schnittstellenattribut](../windows/interface-attributes.md)  