---
title: "ComPtrRefBase-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::Details::ComPtrRefBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtrRefBase-Klasse"
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ComPtrRefBase-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### Parameter  
 `T`  
 Ein [ComPtr \<T\>](../windows/comptr-class.md)\-Typ oder einen davon abgeleiteten Typ, nicht nur die Schnittstelle, die vom ComPtr dargestellt wird.  
  
## Hinweise  
 Stellt die Basisklasse für die [ComPtrRef](../windows/comptrref-class.md)\-Klasse dar.  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`InterfaceType`|Ein Synonym für den Typ des Vorlagenparameters `T`.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ComPtrRefBase::operator IInspectable\*\*\-Operator](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|Wandelt den aktuellen [ptr\_](../windows/comptrrefbase-ptr-data-member.md) Datenmember in ein Zeiger\-zu\-ein\-Zeiger\-zur IInspectable\-Schnittstelle um.|  
|[ComPtrRefBase::operator IUnknown\*\*\-Operator](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|Wandelt den aktuellen [ptr\_](../windows/comptrrefbase-ptr-data-member.md) Datenmember in ein Zeiger\-zu\-ein\-Zeiger\-zur IUnknown\-Schnittstelle um.|  
  
### Geschützte Datenmember  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[ComPtrRefBase::ptr\_\-Datenmember](../windows/comptrrefbase-ptr-data-member.md)|Zeiger auf den Typ angegeben durch den aktuellen von Vorlagenparametern.|  
  
## Vererbungshierarchie  
 `ComPtrRefBase`  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)