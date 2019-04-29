---
title: CloakedIid-Struktur
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 10dc2af1897147045382e8463b6602fa015fc899
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398718"
---
# <a name="cloakediid-structure"></a>CloakedIid-Struktur

Gibt an, um die `RuntimeClass`, `Implements` und `ChainInterfaces` Vorlagen, dass die angegebene Schnittstelle nicht zugegriffen werden kann, in der IID-Liste ist.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
struct CloakedIid : T;
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Die Schnittstelle, die ausgeblendet ist (verdeckt).

## <a name="remarks"></a>Hinweise

Im folgenden ist ein Beispiel dafür, wie **CloakedIid** wird verwendet: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`T`

`CloakedIid`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](microsoft-wrl-namespace.md)