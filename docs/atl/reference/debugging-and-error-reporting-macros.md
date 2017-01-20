---
title: "Debugging and Error Reporting Macros"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Makros, Fehlerberichte"
ms.assetid: 4da9b87f-ec5c-4a32-ab93-637780909b9d
caps.latest.revision: 18
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Debugging and Error Reporting Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Makros zum Debuggen und die Ablaufverfolgung nützliche Funktionen aus.  
  
|||  
|-|-|  
|[\_ATL\_DEBUG\_INTERFACES](../Topic/_ATL_DEBUG_INTERFACES.md)|Schreibt, an das Ausgabefenster, alle Schnittstellenverluste, die erkannt werden, wenn `_Module.Term` aufgerufen wird.|  
|[\_ATL\_DEBUG\_QI](../Topic/_ATL_DEBUG_QI.md)|Schreibt `QueryInterface` alle Aufrufe an das Ausgabefenster.|  
|[ATLASSERT](../Topic/ATLASSERT.md)|Führt die gleiche Funktionalität wie das [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)\-Makro aus, das in der C\-Laufzeitbibliothek gefunden wird.|  
|[ATLENSURE](../Topic/ATLENSURE.md)|Führt Parametervalidierung aus.  Aufruf `AtlThrow` nach Bedarf|  
|[ATLTRACENOTIMPL](../Topic/ATLTRACENOTIMPL.md)|Sendet eine Meldung in das Sicherungsgerät, dass die angegebene Funktion nicht implementiert wird.|  
|[ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md)|Zeigt Warnungen ein Ausgabegerät, wie das Debuggerfenster, entsprechend den angegebenen Flags und den Ebenen.  Ist für Abwärtskompatibilität.|  
|[ATLTRACE2](../Topic/ATLTRACE2.md)|Zeigt Warnungen ein Ausgabegerät, wie das Debuggerfenster, entsprechend den angegebenen Flags und den Ebenen.|  
  
## Siehe auch  
 [Macros](../../atl/reference/atl-macros.md)   
 [Debugging and Error Reporting Global Functions](../../atl/reference/debugging-and-error-reporting-global-functions.md)