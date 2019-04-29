---
title: EnableIf-Struktur
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::EnableIf
helpviewer_keywords:
- EnableIf structure
ms.assetid: 7825b283-e6b2-4f39-a4b9-c03bcd431b8e
ms.openlocfilehash: daaba919acaa35615af56831f9458831c3d35427
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398523"
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

[Microsoft::WRL::Details-Namespace](microsoft-wrl-details-namespace.md)