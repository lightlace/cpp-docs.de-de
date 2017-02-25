---
title: "CInterfaceList Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CInterfaceList"
  - "ATL.CInterfaceList"
  - "CInterfaceList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceList class"
ms.assetid: 2077764d-25e5-4b3d-96c8-08a287bbcd25
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CInterfaceList Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, wenn sie eine Liste von COM\-Schnittstellenzeigern nützlich sind, erstellt.  
  
## Syntax  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>   
class CInterfaceList : public CAtlList<  
   ATL::CComQIPtr< I, piid >,  
   CComQIPtrElementTraits< I, piid >  
>  
```  
  
#### Parameter  
 `I`  
 Eine COM\-Schnittstelle, die den Typ des zu speichernden Zeigers angibt.  
  
 `piid`  
 Ein Zeiger auf IID von `I`.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInterfaceList::CInterfaceList](../Topic/CInterfaceList::CInterfaceList.md)|Der Konstruktor für die Schnittstellenliste festgelegt.|  
  
## Hinweise  
 Diese Klasse stellt einen Konstruktor und abgeleiteten Methoden zum Erstellen einer Liste der COM\-Schnittstellenzeiger bereit.  Verwendung [CInterfaceArray](../../atl/reference/cinterfacearray-class.md), wenn ein Array erforderlich ist.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 [CAtlList](../../atl/reference/catllist-class.md)  
  
 `CInterfaceList`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CAtlList Class](../../atl/reference/catllist-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)