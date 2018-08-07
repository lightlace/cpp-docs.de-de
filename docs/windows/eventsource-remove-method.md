---
title: 'EventSource:: Remove-Methode | Microsoft-Dokumentation'
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
ms.openlocfilehash: 9dd026158a2bbc76e7a3e195bc5346f65821f2b7
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569494"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove-Methode
Löscht den Ereignishandler, die durch das angegebene Ereignis Registrierungstoken dargestellt wird, aus dem Satz von Ereignishandlern verknüpft ist, mit dem aktuellen **EventSource** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *token*  
 Ein Handle, das einen Ereignishandler darstellt. Dieses Token zurückgegeben wurde, wenn der Ereignishandler, indem registriert wurde die [Add()](../windows/eventsource-add-method.md) Methode.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen über die EventRegistrationToken-Struktur finden Sie unter den `Windows::Foundation::EventRegistrationToken` Struktur Thema in der Windows-Runtime-Referenzdokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)