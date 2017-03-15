---
title: "EventSource::Add-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::Add"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Add-Methode"
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::Add-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fügt den Ereignishandler, die durch die angegebenen Delegaten-Schnittstelle zu den Ereignishandler für das aktuelle EventSource-Objekt dargestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `delegateInterface`  
 Die Schnittstelle ein Delegatobjekt, die einen Ereignishandler darstellt.  
  
 `token`  
 Wenn dieser Vorgang abgeschlossen ist, ein Handle, das das Ereignis darstellt. Verwenden Sie dieses Token als Parameter für die [Remove()](../windows/eventsource-remove-method.md) Methode, um den Ereignishandler zu verwerfen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)