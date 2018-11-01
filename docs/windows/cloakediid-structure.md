---
title: CloakedIid-Struktur
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
ms.openlocfilehash: 7340032e91a9b30b72099477b55b88740b3eb68f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535303"
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

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)