---
title: 'Implements:: fillarraywithiid-Methode | Microsoft Docs'
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
ms.openlocfilehash: e020bd725d0c0f5c65ab1cfb38b45e2b8fbca62e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875720"
---
# <a name="implementsfillarraywithiid-method"></a>Implements::FillArrayWithIid-Methode
Fügt die Schnittstellen-ID, die durch den aktuellen nullte Vorlagenparameter in das angegebene Array-Element angegeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `index`  
 Ein nullbasierter Index, der das Array Startelement für diesen Vorgang angibt. Wenn dieser Vorgang abgeschlossen ist, `index` um 1 erhöht.  
  
 `iids`  
 Ein Array des Typs IID.  
  
## <a name="remarks"></a>Hinweise  
 Interne Hilfsfunktion.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Implements-Struktur](../windows/implements-structure.md)