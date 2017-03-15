---
title: "GetActivationFactory-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::GetActivationFactory"
  - "client/ABI::Windows::Foundation::GetActivationFactory"
  - "client/Windows::Foundation::GetActivationFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetActivationFactory-Funktion"
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# GetActivationFactory-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft eine Aktivierungsfactory für den Typ ab, der mit dem Vorlagenparameter angegeben wird.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### Parameter  
 `T`  
 Ein Vorlagenparameter, der den Typ der Aktivierungsfactorys angibt.  
  
 `activatableClassId`  
 Der Name der Klasse, die die Aktivierungsfactory erzeugen kann.  
  
 `factory`  
 Wenn dieser Vorgang abgeschlossen wird, ein Verweis auf die Aktivierungsfactory für Typ `T`.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, der angibt, warum dieser Vorgang fehlgeschlagen ist.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Windows::Foundation  
  
## Siehe auch  
 [Windows::Foundation\-Namespace](../windows/windows-foundation-namespace.md)