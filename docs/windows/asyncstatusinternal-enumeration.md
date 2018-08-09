---
title: AsyncStatusInternal-Enumeration | Microsoft-Dokumentation
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
ms.openlocfilehash: eeaef23178829163725b78685b3460913f53f2c2
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652798"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal-Enumeration
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.  
  
## <a name="members"></a>Member  
 `_Created`  
 Entspricht `::Windows::Foundation::AsyncStatus::Created`.  
  
 `_Started`  
 Entspricht `::Windows::Foundation::AsyncStatus::Started`.  
  
 `_Completed`  
 Entspricht `::Windows::Foundation::AsyncStatus::Completed`.  
  
 `_Cancelled`  
 Entspricht `::Windows::Foundation::AsyncStatus::Cancelled`.  
  
 `_Error`  
 Entspricht `::Windows::Foundation::AsyncStatus::Error`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)