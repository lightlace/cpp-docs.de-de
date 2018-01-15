---
title: 'Asyncbase:: Putonprogress-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::PutOnProgress
dev_langs: C++
helpviewer_keywords: PutOnProgress method
ms.assetid: 1f5f180e-eb5a-4afe-ac16-69dbf36f0383
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25479de837c157871d7757b6948d6cd581d56ace
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseputonprogress-method"></a>AsyncBase::PutOnProgress-Methode
Legt die Adresse des ereignishandlers Status mit dem angegebenen Wert fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   PutOnProgress  
)(TProgress* progressHandler);  
```  
  
#### <a name="parameters"></a>Parameter  
 `progressHandler`  
 Die Adresse, die auf der der Status-Ereignishandler festgelegt ist.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)