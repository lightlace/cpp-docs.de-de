---
title: "CAnimationVariableChangeHandler-Klasse"
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
  - "afxanimationcontroller/CAnimationVariableChangeHandler"
  - "CAnimationVariableChangeHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariableChangeHandler-Klasse"
ms.assetid: 2ea4996d-5c04-4dfc-be79-d42d55050795
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationVariableChangeHandler-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Rückruf, der von der Animations\-API aufgerufen wird, wenn sich der Wert einer Animationsvariablen ändert.  
  
## Syntax  
  
```  
class CAnimationVariableChangeHandler : public CUIAnimationVariableChangeHandlerBase<CAnimationVariableChangeHandler>;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CAnimationVariableChangeHandler::CAnimationVariableChangeHandler`|Erstellt ein `CAnimationVariableChangeHandler`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|`CAnimationVariableChangeHandler::CreateInstance`|Erstellt eine Instanz von `CAnimationVariableChangeHandler`\-Objekt.|  
|[CAnimationVariableChangeHandler::OnValueChanged](../Topic/CAnimationVariableChangeHandler::OnValueChanged.md)|Aufgerufen, wenn ein Wert einer Animationsvariablen geändert hat.  \(Überschreibungen `CUIAnimationVariableChangeHandlerBase::OnValueChanged`.\)|  
|[CAnimationVariableChangeHandler::SetAnimationController](../Topic/CAnimationVariableChangeHandler::SetAnimationController.md)|Speichert einen Zeiger auf den Animationscontroller, um Ereignisse weiterzuleiten.|  
  
## Hinweise  
 Dieser Ereignishandler wird erstellt und an `IUIAnimationVariable::SetVariableChangeHandler`\-Methode übergeben, wenn Sie `CAnimationVariable::EnableValueChangedEvent` oder `CAnimationBaseObject::EnableValueChangedEvent` aufrufen \(das dieses Ereignis für alle Animationsvariablen aktiviert, die in einem Animationsobjekt gekapselt werden\).  
  
## Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationVariableChangeHandlerBase`  
  
 `CAnimationVariableChangeHandler`  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)