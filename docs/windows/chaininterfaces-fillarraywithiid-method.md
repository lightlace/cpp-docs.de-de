---
title: 'Chaininterfaces:: Fillarraywithiid-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: f1ce699c-dfb6-40a9-9ea0-e6703d3cf971
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c795a3a80c48e7fa976807ab3e261fc927d7e104
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644270"
---
# <a name="chaininterfacesfillarraywithiid-method"></a>ChainInterfaces::FillArrayWithIid-Methode
Speichert die Schnittstellen-ID, durch definiert die *I0* Template-Parameter in einer angegebenen Position in einem angegebenen Array von Schnittstellen-IDs.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
__forceinline static void FillArrayWithIid(  
   _Inout_ unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *index*  
 Zeiger auf einen Indexwert in der *Iids* Array.  
  
 *IIDs*  
 Ein Array von Schnittstellen-IDs.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [ChainInterfaces-Struktur](../windows/chaininterfaces-structure.md)