---
title: "CInterfaceArray Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CInterfaceArray"
  - "CInterfaceArray"
  - "ATL::CInterfaceArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterfaceArray class"
ms.assetid: 1f29cf66-a086-4a7b-b6a8-64f73da39f79
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CInterfaceArray Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Methoden, wenn sie ein Array COM\-Schnittstellenzeiger nützlich sind, erstellt.  
  
## Syntax  
  
```  
  
      template<  
   class I,  
   const IID* piid = & __uuidof( I )  
>  
class CInterfaceArray : public CAtlArray<  
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
|[CInterfaceArray::CInterfaceArray](../Topic/CInterfaceArray::CInterfaceArray.md)|Der Konstruktor für das Schnittstellenarray.|  
  
## Hinweise  
 Diese Klasse stellt einen Konstruktor und abgeleiteten Methoden zum Erstellen eines Arrays COM\-Schnittstellenzeiger bereit.  Verwendung [CInterfaceList](../../atl/reference/cinterfacelist-class.md), wenn eine Liste erforderlich ist.  
  
 Weitere Informationen finden Sie unter [ATL\-Auflistungsklassen](../../atl/atl-collection-classes.md).  
  
## Vererbungshierarchie  
 `CAtlArray`  
  
 `CInterfaceArray`  
  
## Anforderungen  
 **Header:** atlcoll.h  
  
## Siehe auch  
 [CAtlArray Class](../../atl/reference/catlarray-class.md)   
 [CComQIPtr Class](../../atl/reference/ccomqiptr-class.md)   
 [CComQIPtrElementTraits Class](../../atl/reference/ccomqiptrelementtraits-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)