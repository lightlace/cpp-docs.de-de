---
title: AsyncStatusInternal-Enumeration | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs: C++
helpviewer_keywords: AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd277fecb0bc63d5ee823af98df8aa298b285964
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal-Enumeration
Unterstützt die WRL-Infrastruktur und ist nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die **Windows::Foundation::AsyncStatus** Enumeration.  
  
## <a name="members"></a>Member  
 `_Created`  
 Entspricht:: Windows::Foundation::AsyncStatus:: erstellt  
  
 `_Started`  
 Entspricht:: Windows::Foundation::AsyncStatus:: gestartet  
  
 `_Completed`  
 Entspricht:: Windows::Foundation::AsyncStatus:: abgeschlossen  
  
 `_Cancelled`  
 Entspricht:: Windows::Foundation::AsyncStatus:: abgebrochen  
  
 `_Error`  
 Entspricht:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)