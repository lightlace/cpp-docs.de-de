---
title: "ComPtrRefBase::operator IInspectable**-Operator"
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
  - "client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator IInspectable**-Operator"
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtrRefBase::operator IInspectable**-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
operator IInspectable**() const;  
```  
  
## Hinweise  
 Wandelt den aktuellen [ptr\_](../windows/comptrrefbase-ptr-data-member.md) Datenmember in ein Zeiger\-zu\-ein\-Zeiger\-zur IInspectable\-Schnittstelle um.  
  
 Ein Fehler wird ausgegeben, wenn das aktuelle ComPtrRefBase nicht von IInspectable abgeleitet.  
  
 Dadurch, die umgewandelt wird, ist nur verfügbar, wenn **\_\_WRL\_CLASSIC\_COM\_\_** definiert wird.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [ComPtrRefBase\-Klasse](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)