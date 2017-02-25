---
title: "CComPtr Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComPtr class"
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CComPtr Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Klasse des intelligenten Zeigermechanismus zum Verwalten von COM\-Schnittstellenzeigern.  
  
## Syntax  
  
```  
  
      template<  
   class T   
>  
class CComPtr  
```  
  
#### Parameter  
 `T`  
 Eine COM\-Schnittstelle, die den Typ des zu speichernden Zeigers angibt.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)|Der \-Konstruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComPtr::operator \=](../Topic/CComPtr::operator%20=.md)|Weist einen Zeiger auf das Memberzeiger zu.|  
  
## Hinweise  
 ATL verwendet `CComPtr` und [CComQIPtr](../../atl/reference/ccomqiptr-class.md), um COM\-Schnittstellenzeiger zu verwalten.  Beide werden von [CComPtrBase](../../atl/reference/ccomptrbase-class.md) berechnet, und beide führen automatische Verweiszählung aus.  
  
 Die **CComPtr** und [CComQIPtr](../../atl/reference/ccomqiptr-class.md)\-Klassen können helfen, Speicherverluste zu beseitigen, indem sie automatische Verweiszählung ausführen.  Die folgenden Funktionen beide führen die gleichen logischen Operationen aus; Beachten Sie jedoch, wie die zweite Version möglicherweise weniger fehleranfällig ist, indem die **CComPtr**\-Klasse verwendet:  
  
 [!CODE [NVC_ATL_Utilities#130](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#130)]  
  
 [!CODE [NVC_ATL_Utilities#131](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Utilities#131)]  
  
 In Debugbuilds Link atlsd.lib für Ablaufverfolgung.  
  
## Vererbungshierarchie  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## Anforderungen  
 **Header:**  atlbase.h  
  
## Siehe auch  
 [CComPtr::CComPtr](../Topic/CComPtr::CComPtr.md)   
 [CComQIPtr::CComQIPtr](../Topic/CComQIPtr::CComQIPtr.md)   
 [Class Overview](../../atl/atl-class-overview.md)