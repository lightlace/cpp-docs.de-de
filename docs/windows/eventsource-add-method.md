---
title: 'EventSource:: Add-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 90750f965768d5ecda40e074f9a136407613d2d2
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570381"
---
# <a name="eventsourceadd-method"></a>EventSource::Add-Methode
Fügt den Ereignishandler, die durch die Schnittstelle für die angegebenen Delegaten dargestellt wird, auf den Satz von Ereignishandlern für die aktuelle **EventSource** Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *delegateInterface*  
 Die Schnittstelle an ein Delegatobjekt, das einen Ereignishandler darstellt.  
  
 *token*  
 Wenn dieser Vorgang abgeschlossen ist, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter an die ["Remove()""](../windows/eventsource-remove-method.md) Methode, um den Ereignishandler zu verwerfen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)