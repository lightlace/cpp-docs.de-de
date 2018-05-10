---
title: 'EventSource:: Remove-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbf0480252fca342b8a690e93f92ae14ca5e84c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
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