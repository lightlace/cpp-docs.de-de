---
title: "CAnimationTimerEventHandler-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationTimerEventHandler"
  - "CAnimationTimerEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationTimerEventHandler-Klasse"
ms.assetid: 188dea3b-4b5e-4f6b-8df9-09d993a21619
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationTimerEventHandler-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Rückruf, der von der Animations\-API beim Auftreten von Zeitsteuerungsereignissen aufgerufen wird.  
  
## Syntax  
  
```  
class CAnimationTimerEventHandler : public CUIAnimationTimerEventHandlerBase<CAnimationTimerEventHandler>;  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationTimerEventHandler::CreateInstance](../Topic/CAnimationTimerEventHandler::CreateInstance.md)|Erstellt eine Instanz von `CAnimationTimerEventHandler` Rückruf.|  
|[CAnimationTimerEventHandler::OnPostUpdate](../Topic/CAnimationTimerEventHandler::OnPostUpdate.md)|Behandelt Ereignisse, die auftreten, nachdem ein Animationsupdate beendet ist.  \(Überschreibungen `CUIAnimationTimerEventHandlerBase::OnPostUpdate`.\)|  
|[CAnimationTimerEventHandler::OnPreUpdate](../Topic/CAnimationTimerEventHandler::OnPreUpdate.md)|Behandelt Ereignisse, die auftreten, bevor ein Animationsupdate beginnt.  \(Überschreibungen `CUIAnimationTimerEventHandlerBase::OnPreUpdate`.\)|  
|[CAnimationTimerEventHandler::OnRenderingTooSlow](../Topic/CAnimationTimerEventHandler::OnRenderingTooSlow.md)|Behandelt Ereignisse, die auftreten, wenn die Renderingframerate für eine Animation unter der minimalen erwünschten Framerate ab.  \(Überschreibungen `CUIAnimationTimerEventHandlerBase::OnRenderingTooSlow`.\)|  
|[CAnimationTimerEventHandler::SetAnimationController](../Topic/CAnimationTimerEventHandler::SetAnimationController.md)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## Hinweise  
 Dieser Ereignishandler wird zu IUIAnimationTimer::SetTimerEventHandler erstellt und übergeben, wenn Sie CAnimationController::EnableAnimationTimerEventHandler aufrufen.  
  
## Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationTimerEventHandlerBase`  
  
 `CAnimationTimerEventHandler`  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)