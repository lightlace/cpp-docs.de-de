---
title: MixIn-Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::MixIn
dev_langs:
- C++
helpviewer_keywords:
- MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ccea9a053f47ae206cbe5c8412c387f07bd5b52
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603426"
---
# <a name="mixin-structure"></a>MixIn-Struktur

Stellt sicher, dass eine Runtime-Klasse aus Windows-Runtime-Schnittstellen (sofern vorhanden) und dann aus klassischen COM-Schnittstellen abgeleitet wird.

## <a name="syntax"></a>Syntax

```cpp
template<
   typename Derived,
   typename MixInType,
   bool hasImplements = __is_base_of(Details::ImplementsBase,
   MixInType)  
>
struct MixIn;
```

### <a name="parameters"></a>Parameter

*Abgeleitete*  
Ein abgeleiteter Typ von der [implementiert](../windows/implements-structure.md) Struktur.

*MixInType*  
Ein Basistyp.

*hasImplements*  
**"true"** Wenn *MixInType* ist abgeleitet von der aktuellen Implementierung Basistyp **"false"** andernfalls.

## <a name="remarks"></a>Hinweise

Wenn eine Klasse von Windows-Runtime und COM-Klassenschnittstellen abgeleitet ist, Liste der Deklaration muss zunächst alle Windows-Runtime-Schnittstellen aufgelistet, und klicken Sie dann alle klassischen COM-Schnittstellen. **MixIn** wird sichergestellt, dass die Schnittstellen in der richtigen Reihenfolge angegeben werden.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`MixIn`

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)