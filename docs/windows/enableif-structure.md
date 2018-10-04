---
title: EnableIf-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
dev_langs:
- C++
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2512c9b8b552027f4a0b4d72788e19d77a35d92e
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789188"
---
# <a name="enableif-structure"></a>EnableIf-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <bool b, typename T = void>
struct EnableIf;

template <typename T>
struct EnableIf<true, T>;
```

### <a name="parameters"></a>Parameter

*T*<br/>
Ein Typ.

*b*<br/>
Ein boolescher Ausdruck.

## <a name="remarks"></a>Hinweise

Definiert einen Datenmember des Typs durch den zweiten Vorlagenparameter angegeben wird, wenn der erste Vorlagenparameter ergibt **"true"**.

## <a name="members"></a>Member

### <a name="public-typedefs"></a>Öffentliche Typedefs

|Name|Beschreibung|
|----------|-----------------|
|`type`|Wenn Vorlagenparameter *b* ergibt **"true"**, die teilweise Spezialisierung definiert Datenmember `type` Typ `T`.|

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`EnableIf`

## <a name="requirements"></a>Anforderungen

**Header:** internal.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)