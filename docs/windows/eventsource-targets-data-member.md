---
title: 'EventSource:: Targets_-Datenmember | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: event/Microsoft::WRL::EventSource::targets_
dev_langs: C++
helpviewer_keywords: targets_ data member
ms.assetid: 5d5cee05-3315-4514-bce2-19173c923c7d
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c5e15d5cb7714d5f130d50a6f867604fdeb53c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="eventsourcetargets-data-member"></a>EventSource::targets_-Datenmember
Ein Array von ein oder mehrere Ereignishandler.  
  
## <a name="syntax"></a>Syntax  
  
```  
ComPtr<Details::EventTargetArray> targets_;  
```  
  
## <a name="remarks"></a>Hinweise  
 Tritt das Ereignis, das vom aktuellen EventSource-Objekt dargestellt wird, werden die Ereignishandler aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL
 
 ## <a name="see-also"></a>Siehe auch
 [EventSource-Klasse](../windows/eventsource-class.md)