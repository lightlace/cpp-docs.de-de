---
title: "Debugging and Error Reporting Global Functions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Funktionen [ATL], Fehlerberichte"
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# Debugging and Error Reporting Global Functions
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Funktionen stellen nützliche das Debuggen und die Ablaufverfolgung Funktionen aus.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](../Topic/AtlHresultFromLastError.md)|Gibt einen `GetLastError` Fehlercode in Form eines HRESULT zurück.|  
|[AtlHresultFromWin32](../Topic/AtlHresultFromWin32.md)|Konvertiert einen Win32\-Fehlercode in ein HRESULT.|  
|[AtlReportError](../Topic/AtlReportError.md)|richtet **IErrorInfo**, von Fehlerdetails an einen Client bereitzustellen.|  
|[AtlThrow](../Topic/AtlThrow.md)|Löst eine `CAtlException` aus.|  
|[AtlThrowLastWin32](../Topic/AtlThrowLastWin32.md)|Rufen Sie diese Funktion auf, um einen Fehler auf dem Ergebnis der Windows\-Funktion `GetLastError` zu signalisieren.|  
|[AtlTraceLoadSettings](../../misc/atltraceloadsettings.md)|Rufen Sie diese Funktion, um Ablaufverfolgungseinstellungen aus einer Datei zu laden.|  
|[AtlTraceSaveSettings](../../misc/atltracesavesettings.md)|Rufen Sie diese Funktion auf, um die aktuellen Ablaufverfolgungseinstellungen in eine Datei zu speichern.|  
  
## Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)   
 [Debugging and Error Reporting Macros](../../atl/reference/debugging-and-error-reporting-macros.md)