---
title: "FtmBase::DisconnectObject-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ftm/Microsoft::WRL::FtmBase::DisconnectObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DisconnectObject-Methode"
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# FtmBase::DisconnectObject-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt erzwungen alle externen Verbindungen mit einem Objekt frei.  Der Server des Objekts ruft die Implementierung des Objekts dieser Methode vor dem Herunterfahren auf.  
  
## Syntax  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### Parameter  
 `dwReserved`  
 Für die zukünftige Verwendung reserviert. Muss 0 \(null\) sein.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Anforderungen  
 **Header:**  ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [FtmBase\-Klasse](../windows/ftmbase-class.md)