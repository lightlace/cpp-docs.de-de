---
title: "EventSource::GetSize-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::GetSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetSize-Methode"
ms.assetid: 7825aab5-1a6b-465f-9159-3a6684142d1f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::GetSize-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Anzahl der dem aktuellen EventSource-Objekt zugeordneten Ereignishandler  
  
## <a name="syntax"></a>Syntax  
  
```  
size_t GetSize() const;  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Ereignishandler in [Targets_](../windows/eventsource-targets-data-member.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [EventSource-Klasse](../windows/eventsource-class.md)