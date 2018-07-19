---
title: AsyncStatusInternal-Enumeration | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::AsyncStatusInternal
dev_langs:
- C++
helpviewer_keywords:
- AsyncStatusInternal enumeration
ms.assetid: b783923f-3f1c-4487-9384-be572cbc62d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 150169442aa68395b4dc8a4f4c74951e877f18f5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33863724"
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