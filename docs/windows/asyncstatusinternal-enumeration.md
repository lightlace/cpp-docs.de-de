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
ms.openlocfilehash: a68189c461453dc72585ff4034df5ba69bb41bd5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464875"
---
# <a name="asyncstatusinternal-enumeration"></a>AsyncStatusInternal-Enumeration
Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.  
  
## <a name="syntax"></a>Syntax  
  
```  
enum AsyncStatusInternal;  
```  
  
## <a name="remarks"></a>Hinweise  
 Gibt eine Zuordnung zwischen internen Enumerationen für den Status von asynchronen Vorgängen und die `Windows::Foundation::AsyncStatus` Enumeration.  
  
## <a name="members"></a>Member  
 *_Erstellt*  
 Äquivalent zu:: Windows::Foundation::AsyncStatus:: erstellt  
  
 *_Started*  
 Äquivalent zu:: Windows::Foundation::AsyncStatus:: gestartet  
  
 *_Completed*  
 Äquivalent zu:: Windows::Foundation::AsyncStatus:: abgeschlossen  
  
 *_Cancelled*  
 Äquivalent zu:: Windows::Foundation::AsyncStatus:: abgebrochen  
  
 *_Error*  
 Äquivalent zu:: Windows::Foundation::AsyncStatus::Error  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** async.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)