---
title: "CAtlException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlException"
  - "ATL::CAtlException"
  - "ATL.CAtlException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlException class"
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CAtlException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse definiert eine ATL\-Ausnahme.  
  
## Syntax  
  
```  
  
class CAtlException  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlException::CAtlException](../Topic/CAtlException::CAtlException.md)|Der \-Konstruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](../Topic/CAtlException::operator%20HRESULT.md)|Wandelt das aktuelle Objekt in einen HRESULT\-Wert um.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAtlException::m\_hr](../Topic/CAtlException::m_hr.md)|Die Variable des Typs HRESULT erstellt durch das Objekt und verwendet, um den Fehlerzustand zu speichern.|  
  
## Hinweise  
 Ein Objekt `CAtlException` stellt eine Ausnahmebedingung dar, die einem ATL\-Vorgang verknüpft ist.  Die `CAtlException`\-Klasse enthält einen öffentlichen Datenmember, der den Statuscode gespeichert werden, der den Grund für die Ausnahme und einen Typumwandlungsoperator, angibt, der Ihnen ermöglicht, die Ausnahme zu behandeln, als ob es ein HRESULT war.  
  
 Im Allgemeinen rufen Sie `AtlThrow` anstatt auf, ein `CAtlException`\-Objekt direkt erstellen.  
  
## Anforderungen  
 **Header:** atlexcept.h  
  
## Siehe auch  
 [AtlThrow](../Topic/AtlThrow.md)   
 [Class Overview](../../atl/atl-class-overview.md)