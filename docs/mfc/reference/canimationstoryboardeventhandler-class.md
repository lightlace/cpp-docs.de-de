---
title: "CAnimationStoryboardEventHandler-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationStoryboardEventHandler"
  - "CAnimationStoryboardEventHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationStoryboardEventHandler-Klasse"
ms.assetid: 10a7e86b-c02d-4124-9a2e-61ecf8ac62fc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationStoryboardEventHandler-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Rückruf, der von der Animations\-API aufgerufen wird, wenn der Status eines Drehbuchs geändert oder ein Storyboard aktualisiert wird.  
  
## Syntax  
  
```  
class CAnimationStoryboardEventHandler : public CUIAnimationStoryboardEventHandlerBase<CAnimationStoryboardEventHandler>;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler](../Topic/CAnimationStoryboardEventHandler::CAnimationStoryboardEventHandler.md)|Erstellt ein `CAnimationStoryboardEventHandler`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationStoryboardEventHandler::CreateInstance](../Topic/CAnimationStoryboardEventHandler::CreateInstance.md)|Erstellt eine Instanz von `CAnimationStoryboardEventHandler` Rückruf.|  
|[CAnimationStoryboardEventHandler::OnStoryboardStatusChanged](../Topic/CAnimationStoryboardEventHandler::OnStoryboardStatusChanged.md)|Behandelt `OnStoryboardStatusChanged`\-Ereignisse, die auftreten, wenn der Status eines Drehbuchs geändert wird \(Überschreibungen `CUIAnimationStoryboardEventHandlerBase::OnStoryboardStatusChanged`.\)|  
|[CAnimationStoryboardEventHandler::OnStoryboardUpdated](../Topic/CAnimationStoryboardEventHandler::OnStoryboardUpdated.md)|Behandelt `OnStoryboardUpdated`\-Ereignisse, die auftreten, wenn ein Storyboard aktualisiert wird \(Überschreibungen `CUIAnimationStoryboardEventHandlerBase::OnStoryboardUpdated`.\)|  
|[CAnimationStoryboardEventHandler::SetAnimationController](../Topic/CAnimationStoryboardEventHandler::SetAnimationController.md)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## Hinweise  
 Dieser Ereignishandler wird erstellt und an `IUIAnimationStoryboard::SetStoryboardEventHandler`\-Methode übergeben, wenn Sie `CAnimationController::EnableStoryboardEventHandler` aufrufen.  
  
## Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationStoryboardEventHandlerBase`  
  
 `CAnimationStoryboardEventHandler`  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)