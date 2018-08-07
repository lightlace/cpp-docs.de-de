---
title: 'Implements:: casttounknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: ca3324f7-4136-406b-8698-7389f4f3d3c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a490e3b8dc620cb3f0f440b2e28cce1f2e69c76d
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39607247"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown-Methode
Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Dieser Vorgang immer erfolgreich ist, und gibt die `IUnknown` Zeiger.  
  
## <a name="remarks"></a>Hinweise  
 Interne Hilfsmethode-Funktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Struktur](../windows/implements-structure.md)