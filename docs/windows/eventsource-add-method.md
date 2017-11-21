---
title: 'EventSource:: Add-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::Add
dev_langs: C++
helpviewer_keywords: Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dca2e67baccfedea10f7faae9ac49ebb0e5bdb14
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourceadd-method"></a>EventSource::Add-Methode
Fügt den Ereignishandler, die durch die Schnittstelle des angegebenen Delegaten dargestellt wird, auf den Satz der Ereignishandler für das aktuelle EventSource-Objekt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `delegateInterface`  
 Die Schnittstelle mit einem Delegatobjekt, der einen Ereignishandler darstellt.  
  
 `token`  
 Wenn dieser Vorgang abgeschlossen wird, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter an die [Remove()](../windows/eventsource-remove-method.md) Methode, um den Ereignishandler zu verwerfen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)