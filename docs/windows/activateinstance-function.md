---
title: "ActivateInstance-Funktion"
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
  - "client/Windows::Foundation::ActivateInstance"
  - "client/ABI::Windows::Foundation::ActivateInstance"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActivateInstance-Funktion"
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
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