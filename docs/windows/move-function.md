---
title: "Move-Funktion | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "internal/Microsoft::WRL::Details::Move"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Move-Funktion"
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Move-Funktion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template<  
   class T  
>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
#### Parameter  
 `T`  
 Der Typ des Arguments.  
  
 `arg`  
 Ein Argument zu verschiebenden.  
  
## Rückgabewert  
 Parameter `arg` nach Bezugs\- oder Bezugsmerkmalen ggf. wurden entfernt.  
  
## Hinweise  
 Verschiebt das angegebene Argument von einem Speicherort auf einen anderen.  
  
 Weitere Informationen finden Sie im Abschnitt **Verschiebesemantik** von [Rvalue\-Verweisdeklarator: &&](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Anforderungen  
 **Header:**  internal.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)