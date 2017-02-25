---
title: "Win32ThreadTraits Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "Win32ThreadTraits"
  - "ATL::Win32ThreadTraits"
  - "ATL.Win32ThreadTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Threading [ATL], creation functions"
  - "Threading [ATL], Windows threads"
  - "Win32ThreadTraits class"
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# Win32ThreadTraits Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Erstellungsfunktion für einen Windows\-Thread bereit.  Verwenden Sie diese Klasse, wenn der Thread nicht CRT\-Funktionen verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class Win32ThreadTraits  
  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](../Topic/Win32ThreadTraits::CreateThread.md)|\(Statisch\) rufen Sie diese Funktion auf, um einen Thread zu erstellen, der CRT\-Funktionen nicht verwenden soll.|  
  
## Hinweise  
 Threadmerkmale sind Klassen, die eine Erstellungsfunktion für einen bestimmten Typ Thread bereitstellen.  Die Erstellungsfunktion verfügt über die gleiche Signatur und Semantik wie die Funktion Windows [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453).  
  
 Threadmerkmale werden durch die folgenden Klassen:  
  
-   [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
-   [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Wenn der Thread CRT\-Funktionen verwendet, verwenden Sie stattdessen [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md).  
  
## Anforderungen  
 **Header:** atlbase.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)