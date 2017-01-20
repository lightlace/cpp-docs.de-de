---
title: "DeferrableEventArgs::GetDeferral-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: ef6dc7c5-b0be-4b85-8507-d3fd97f2185d
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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