---
title: "EventSource::Remove-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::Remove"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Remove-Methode"
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# EventSource::Remove-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Löscht die Ereignishandler, die durch das angegebene Ereignistoken Registrierung aus dem Satz von EventSource Objekt zugeordneten Ereignishandler dargestellt.  
  
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
 Weitere Informationen zur Struktur EventRegistrationToken finden Sie Windows::Foundation::EventRegistrationToken Struktur in der Windows-Runtime-Referenzdokumentation.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)