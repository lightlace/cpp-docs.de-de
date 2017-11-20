---
title: "DeferrableEventArgs::GetDeferral-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# DeferrableEventArgs::GetDeferral-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Verweis auf das [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\-Objekt ab, das ein verzögertes Ereignis darstellt.  
  
## Syntax  
  
```cpp  
HRESULT GetDeferral([out, retval] Windows::Foundation::IDeferral** result)  
```  
  
#### Parameter  
 `result`  
 Ein Zeiger, der auf das [Deferral](http://go.microsoft.com/fwlink/?LinkId=526520)\-Objekt verweist, wenn der Aufruf abgeschlossen wird.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Ein Codebeispiel finden Sie unter [DeferrableEventArgs\-Klasse](../windows/deferrableeventargs-class.md).  
  
## Anforderungen  
 **Header:** event.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [DeferrableEventArgs\-Klasse](../windows/deferrableeventargs-class.md)