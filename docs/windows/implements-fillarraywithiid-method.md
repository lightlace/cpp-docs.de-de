---
title: 'Implements:: fillarraywithiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c65e2d47d466b223acf19589e5966a05762605e3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611563"
---
# <a name="implementsfillarraywithiid-method"></a>Implements::FillArrayWithIid-Methode

Fügt die Schnittstellen-ID, die durch den aktuellen nullten Vorlagenparameter angegeben wird, in das angegebene Array-Element.

## <a name="syntax"></a>Syntax

```cpp
__forceinline static void FillArrayWithIid(
   unsigned long &index,
   _In_ IID* iids
);
```

### <a name="parameters"></a>Parameter

*index*  
Ein nullbasierter Index, der das Startelement "Array" für diesen Vorgang angibt. Klicken Sie nach Abschluss dieses Vorgangs *Index* um 1 erhöht.

*IIDs*  
Ein Array vom Typ IID.

## <a name="remarks"></a>Hinweise

Interne Hilfsmethode-Funktion.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Implements-Struktur](../windows/implements-structure.md)