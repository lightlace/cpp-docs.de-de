---
title: "CRTThreadTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CRTThreadTraits"
  - "ATL.CRTThreadTraits"
  - "CRTThreadTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRTThreadTraits class"
  - "Threading [ATL], creation functions"
  - "Threading [ATL], CRT threads"
ms.assetid: eb6e20b0-c2aa-4170-8e34-aaeeacc86343
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CRTThreadTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Erstellungsfunktion für einen CRT\-Thread bereit.  Verwenden Sie diese Klasse, wenn der Thread CRT\-Funktionen verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CRTThreadTraits  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRTThreadTraits::CreateThread](../Topic/CRTThreadTraits::CreateThread.md)|\(Statisch\) rufen Sie diese Funktion auf, um einen Thread zu erstellen, der CRT\-Funktionen verwenden kann.|  
  
## Hinweise  
 Threadmerkmale sind Klassen, die eine Erstellungsfunktion für einen bestimmten Typ Thread bereitstellen.  Die Erstellungsfunktion verfügt über die gleiche Signatur und Semantik wie die Funktion Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453).  
  
 Threadmerkmale werden durch die folgenden Klassen:  
  
-   [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
-   [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Wenn der Thread nicht CRT\-Funktionen verwendet, verwenden Sie stattdessen [Win32ThreadTraits](../../atl/reference/win32threadtraits-class.md).  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)