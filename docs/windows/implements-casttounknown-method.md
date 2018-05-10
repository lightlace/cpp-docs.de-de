---
title: 'Implements:: casttounknown-Methode | Microsoft Docs'
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
ms.openlocfilehash: 857d13736a92bbbc2c6f1228b3444081ffc18de5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="implementscasttounknown-method"></a>Implements::CastToUnknown-Methode
Ruft einen Zeiger auf die zugrunde liegenden IUnknown-Schnittstelle.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline IUnknown* CastToUnknown();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Dieser Vorgang wird immer erfolgreich, und gibt den IUnknown-Zeiger zurück.  
  
## <a name="remarks"></a>Hinweise  
 Interne Hilfsfunktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Struktur](../windows/implements-structure.md)