---
title: "RuntimeClass::GetRuntimeClassName-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass::GetRuntimeClassName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRuntimeClassName-Methode"
ms.assetid: f6388163-fe65-4948-a4bc-ae6826f480e7
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# RuntimeClass::GetRuntimeClassName-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft den Ablaufklassennamen des aktuellen RuntimeClass\-Objekts ab.  
  
## Syntax  
  
```  
STDMETHOD(  
   GetRuntimeClassName  
)(_Out_ HSTRING* runtimeName);  
```  
  
## Parameter  
 `runtimeName`  
 Wenn dieser Vorgang abgeschlossen wurde, der Ablaufklassenname.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Ein Assertionsfehler wird ausgegeben, wenn \_\_WRL\_STRICT\_\_or \_\_WRL\_FORCE\_INSPECTABLE\_CLASS\_MACRO nicht definiert ist.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [RuntimeClass\-Klasse](../windows/runtimeclass-class.md)