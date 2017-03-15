---
title: "AsWeak-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::AsWeak"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsWeak-Funktion"
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsWeak-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen schwachen Verweis auf einer bestimmten Instanz ab.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### Parameter  
 `T`  
 Ein Zeiger auf den Typ des Parameters `p`.  
  
 `p`  
 Eine Instanz eines Typs.  
  
 `pWeak`  
 Wenn dieser Vorgang abgeschlossen ist, ein Zeiger auf einen schwachen Verweis auf Parameter `p`.  
  
## Rückgabewert  
 S\_OK, wenn der Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, der die Ursache des Fehlers angibt.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)