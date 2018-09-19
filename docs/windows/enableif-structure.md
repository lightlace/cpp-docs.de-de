---
title: EnableIf-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 2cc4e8f272838e5fa1de3eac8bd04a4ec3407dee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400667"
---
# <a name="enableif-structure"></a>EnableIf-Struktur

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template <
   bool b,
   typename T = void
>

struct EnableIf;
template <
   typename T
>
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