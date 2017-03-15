---
title: "ActivateInstance-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance-Funktion"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# ActivateInstance-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Register und eine Instanz des angegebenen Typs ab, der in einer bestimmten ID Klasse definiert wird  
  
## Syntax  
  
```  
template<  
   typename T  
>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### Parameter  
 `T`  
 Ein Typ zu aktivieren.  
  
 `activatableClassId`  
 Der Name der Klassenbezeichner, die Parameter `T` definiert.  
  
 `instance`  
 Wenn dieser Vorgang abgeschlossen wird, ein Verweis auf eine Instanz von `T`.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, der die Ursache des Fehlers angibt.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Windows::Foundation  
  
## Siehe auch  
 [Windows::Foundation\-Namespace](../windows/windows-foundation-namespace.md)