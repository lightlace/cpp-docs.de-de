---
title: "CAnimationVariableIntegerChangeHandler-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationVariableIntegerChangeHandler"
  - "CAnimationVariableIntegerChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableIntegerChangeHandler-Klasse"
ms.assetid: 6ac8e91b-e514-4ff6-babd-33f77c4b2b61
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CAnimationVariableIntegerChangeHandler-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Rückruf, der von der Animations\-API aufgerufen wird, wenn sich der Wert einer Animationsvariablen ändert.  
  
## Syntax  
  
```  
class CAnimationVariableIntegerChangeHandler : public CUIAnimationVariableIntegerChangeHandlerBase<CAnimationVariableIntegerChangeHandler>;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler](../Topic/CAnimationVariableIntegerChangeHandler::CAnimationVariableIntegerChangeHandler.md)|Erstellt ein `CAnimationVariableIntegerChangeHandler`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariableIntegerChangeHandler::CreateInstance](../Topic/CAnimationVariableIntegerChangeHandler::CreateInstance.md)|Erstellt eine Instanz von `CAnimationVariableIntegerChangeHandler` Rückruf.|  
|[CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged](../Topic/CAnimationVariableIntegerChangeHandler::OnIntegerValueChanged.md)|Wird aufgerufen, wenn sich ein Wert einer Animationsvariablen geändert hat.  \(Überschreibungen `CUIAnimationVariableIntegerChangeHandlerBase::OnIntegerValueChanged`.\)|  
|[CAnimationVariableIntegerChangeHandler::SetAnimationController](../Topic/CAnimationVariableIntegerChangeHandler::SetAnimationController.md)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## Hinweise  
 Dieser Ereignishandler wird erstellt und an die IUIAnimationVariable::SetVariableIntegerChangeHandler\-Methode übergeben, wenn Sie CAnimationVariable::EnableIntegerValueChangedEvent oder CAnimationBaseObject::EnableIntegerValueChangedEvent aufrufen \(die dieses Ereignis für alle in einem Animationsobjekt gekapselten Animationsvariablen aktiviert\).  
  
## Vererbungshierarchie  
 [MFC\-Klassen](../../mfc/reference/mfc-classes.md)  
  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableIntegerChangeHandlerBase`  
  
 `CAnimationVariableIntegerChangeHandler`  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)