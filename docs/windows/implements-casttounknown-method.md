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
ms.openlocfilehash: efaf7b51da1e4a4e744133884b92ac78db3b3f66
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017768"
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown-Methode
Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
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