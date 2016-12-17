---
title: "CComQIPtr Class"
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
  - "ATL.CComQIPtr"
  - "ATL::CComQIPtr"
  - "CComQIPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComQIPtr class"
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CComQIPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse des intelligenten Zeigermechanismus zum Verwalten von COM\-Schnittstellenzeigern.  
  
## Syntax  
  
```  
  
      template<  
   class T,  
   const IID* piid = &__uuidof(T)  
>  
class CComQIPtr: public CComPtr<T>  
```  
  
#### Parameter  
 `T`  
 Eine COM\-Schnittstelle, die den Typ des zu speichernden Zeigers angibt.  
  
 `piid`  
 Ein Zeiger auf IID von `T`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)|Konstruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComQIPtr::operator \=](../Topic/CComQIPtr::operator%20=.md)|Weist einen Zeiger auf das Memberzeiger zu.|  
  
## Hinweise  
 ATL verwendet `CComQIPtr` und [CComPtr](../../atl/reference/ccomptr-class.md), um COM\-Schnittstellenzeiger verwalten, die von [CComPtrBase](../../atl/reference/ccomptrbase-class.md) berechnen.  Beide Klassen führen automatische Verweiszählung durch Aufrufe `AddRef` und zu **Release** aus.  Überladene Operatoren behandeln gibt eine Reihe von Zeigeroperationen.  
  
## Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## Anforderungen  
 **Header:**  atlcomcli.h  
  
## Siehe auch  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [CComPtrBase Class](../../atl/reference/ccomptrbase-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)