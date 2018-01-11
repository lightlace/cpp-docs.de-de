---
title: 'Asyncbase:: Getonprogress-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::GetOnProgress
dev_langs: C++
helpviewer_keywords: GetOnProgress method
ms.assetid: 286ddc9c-3e30-41a2-8e8b-e53d3fb0649d
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8d83099b6842f9e758755e64aa8d7828a656aafb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasegetonprogress-method"></a>AsyncBase::GetOnProgress-Methode
Kopiert die Adresse des aktuellen ereignishandlers Status der angegebenen Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHOD(  
   GetOnProgress  
)(TProgress** progressHandler);  
```  
  
#### <a name="parameters"></a>Parameter  
 `progressHandler`  
 Der Speicherort, in dem die Adresse des aktuellen ereignishandlers Status gespeichert wird.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [AsyncBase-Klasse](../windows/asyncbase-class.md)