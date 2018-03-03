---
title: 'EventSource:: Remove-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a11bce6d70c70bba2a4e75753c55d83bec32329f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="eventsourceremove-method"></a>EventSource::Remove-Methode
Löscht den Ereignishandler, dargestellt durch das angegebene Ereignistoken für die Registrierung aus dem Satz von Ereignishandlern, die dem aktuellen EventSource-Objekt zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `token`  
 Ein Handle, das einen Ereignishandler darstellt. Dieses Token wurde zurückgegeben, wenn der Ereignishandler registriert wurde die [Add()](../windows/eventsource-add-method.md) Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zu den EventRegistrationToken-Struktur finden Sie unter der Struktur Windows::Foundation::EventRegistrationToken Thema in der Windows-Runtime-Referenzdokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)