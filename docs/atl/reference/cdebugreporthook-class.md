---
title: "CDebugReportHook Class"
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
  - "ATL.CDebugReportHook"
  - "CDebugReportHook"
  - "ATL::CDebugReportHook"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDebugReportHook class"
ms.assetid: 798076c3-6e63-4286-83b8-aa1bbcd0c20c
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CDebugReportHook Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwenden Sie diese Klasse, um Debugberichte zu einer benannten Pipe zu senden.  
  
## Syntax  
  
```  
  
class CDebugReportHook  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHook](../Topic/CDebugReportHook::CDebugReportHook.md)|Aufrufe [SetPipeName](../Topic/CDebugReportHook::SetPipeName.md), [SetTimeout](../Topic/CDebugReportHook::SetTimeout.md) und [SetHook](../Topic/CDebugReportHook::SetHook.md).|  
|[CDebugReportHook::~CDebugReportHook](../Topic/CDebugReportHook::~CDebugReportHook.md)|Aufrufe [CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md).|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDebugReportHook::CDebugReportHookProc](../Topic/CDebugReportHook::CDebugReportHookProc.md)|\(Statisch\) die benutzerdefinierte Berichtsfunktion, die in Debug\- Berichterstellungsprozess der C\-Laufzeit verknüpft ist.|  
|[CDebugReportHook::RemoveHook](../Topic/CDebugReportHook::RemoveHook.md)|Rufen Sie diese Methode auf, um Debugberichte, die Named Pipe zu senden beenden und den vorherigen Berichtshook wiederherzustellen.|  
|[CDebugReportHook::SetHook](../Topic/CDebugReportHook::SetHook.md)|Rufen Sie diese Methode auf, um das Senden von Debugberichten zur Named Pipe zu starten.|  
|[CDebugReportHook::SetPipeName](../Topic/CDebugReportHook::SetPipeName.md)|Rufen Sie diese Methode auf, um den Computer und den Namen der Pipe festzulegen, zu der die Debugberichte gesendet werden.|  
|[CDebugReportHook::SetTimeout](../Topic/CDebugReportHook::SetTimeout.md)|Rufen Sie diese Methode auf, um die Zeit in Millisekunden festzulegen, dass diese Klasse auf die benannte Pipe wartet, um verfügbar wird.|  
  
## Hinweise  
 Erstellen Sie eine Instanz dieser Klasse in Debugbuilds der Dienste oder Anwendungen, Debugberichte zu einer benannten Pipe zu senden.  Debugberichte werden generiert, indem [\_CrtDbgReport](../../c-runtime-library/reference/crtdbgreport-crtdbgreportw.md) aufruft oder einen Wrapper für diese Funktion wie die [ATLTRACE](../Topic/ATLTRACE%20\(ATL\).md) und [ATLASSERT](../Topic/ATLASSERT.md)\-Makros verwendet.  
  
 Die Verwendung dieser Klasse ermöglicht die interaktiv Debug\- Komponenten fortlaufenden in allein stehendes [Windowstationen](http://msdn.microsoft.com/library/windows/desktop/ms687096).  
  
 Beachten Sie, dass Debugberichte mithilfe des zugrunde liegenden Sicherheitskontext des Threads gesendet werden.  Identitätswechsel ist vorübergehend deaktiviert, damit Debugberichte in Situationen, in denen Identitätswechsel von niedrigen Rechtbenutzern stattfindet, wie in Webanwendungen angezeigt werden können.  
  
## Anforderungen  
 **Header:** atlutil.h  
  
## Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)