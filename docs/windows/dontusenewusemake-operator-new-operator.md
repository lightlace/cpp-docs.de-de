---
title: "DontUseNewUseMake::operator new-Operator"
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
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator new-Operator"
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# DontUseNewUseMake::operator new-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### Parameter  
 `__unnamed0`  
 Ein unbenannter Parameter, der die Anzahl von Bytes Speicherplatz angibt, um zu verknüpfen.  
  
 `placement`  
 Der Typ zugeordnet werden.  
  
## Rückgabewert  
 Bietet eine Möglichkeit, zusätzliche Argumente übergeben werden, wenn Sie `new` überladen.  
  
## Hinweise  
 Überlädt Operator `new` und durch ihn in RuntimeClass verwendet werden.  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [DontUseNewUseMake\-Klasse](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)