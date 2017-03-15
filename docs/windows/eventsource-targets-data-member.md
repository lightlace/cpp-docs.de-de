---
title: "EventSource::targets_-Datenmember | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::EventSource::targets_"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "targets_-Datenmember"
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# EventSource::targets_-Datenmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Array von ein oder mehrere Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```  
ComPtr<Details::EventTargetArray> targets_;  
```  
  
## <a name="remarks"></a>Hinweise  
 Tritt das Ereignis, das durch das aktuelle EventSource-Objekt dargestellt wird, werden die Ereignishandler aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)