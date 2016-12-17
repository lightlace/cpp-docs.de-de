---
title: "CInterpolatorBase-Klasse"
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
  - "afxanimationcontroller/CInterpolatorBase"
  - "CInterpolatorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInterpolatorBase-Klasse"
ms.assetid: bbc3dce7-8398-47f9-b97e-e4fd2d737232
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CInterpolatorBase-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Rückruf, der von der Animations\-API aufgerufen wird, wenn ein neuer Wert einer Animationsvariablen berechnet werden muss.  
  
## Syntax  
  
```  
class CInterpolatorBase : public CUIAnimationInterpolatorBase<CInterpolatorBase>;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CInterpolatorBase::CInterpolatorBase](../Topic/CInterpolatorBase::CInterpolatorBase.md)|Erstellt das `CInterpolatorBase`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CInterpolatorBase::CreateInstance](../Topic/CInterpolatorBase::CreateInstance.md)|Erstellt eine Instanz von `CInterpolatorBase` und speichert einen Zeiger auf den benutzerdefinierten Interpolator, der Ereignisse behandeln wird.|  
|[CInterpolatorBase::GetDependencies](../Topic/CInterpolatorBase::GetDependencies.md)|Ruft die Abhängigkeiten des Interpolators ab.  \(Überschreibungen `CUIAnimationInterpolatorBase::GetDependencies`.\)|  
|[CInterpolatorBase::GetDuration](../Topic/CInterpolatorBase::GetDuration.md)|Ruft die Dauer des Interpolators ab.  \(Überschreibungen `CUIAnimationInterpolatorBase::GetDuration`.\)|  
|[CInterpolatorBase::GetFinalValue](../Topic/CInterpolatorBase::GetFinalValue.md)|Ruft den Endwert ab, zu dem der Interpolator führt.  \(Überschreibungen `CUIAnimationInterpolatorBase::GetFinalValue`.\)|  
|[CInterpolatorBase::InterpolateValue](../Topic/CInterpolatorBase::InterpolateValue.md)|Interpolieren den Wert an einem angegebenen Offset \(Überschreibungen `CUIAnimationInterpolatorBase::InterpolateValue`.\)|  
|[CInterpolatorBase::InterpolateVelocity](../Topic/CInterpolatorBase::InterpolateVelocity.md)|Interpolieren die Geschwindigkeit an einem angegebenen Offset \(Überschreibungen `CUIAnimationInterpolatorBase::InterpolateVelocity`.\)|  
|[CInterpolatorBase::SetCustomInterpolator](../Topic/CInterpolatorBase::SetCustomInterpolator.md)|Speichert einen Zeiger auf benutzerdefinierten Interpolator, der Ereignisse behandelt.|  
|[CInterpolatorBase::SetDuration](../Topic/CInterpolatorBase::SetDuration.md)|Legt die Dauer des Interpolators fest \(Überschreibungen `CUIAnimationInterpolatorBase::SetDuration`.\)|  
|[CInterpolatorBase::SetInitialValueAndVelocity](../Topic/CInterpolatorBase::SetInitialValueAndVelocity.md)|Legt den Anfangswert und die Geschwindigkeit des Interpolators fest.  \(Überschreibungen `CUIAnimationInterpolatorBase::SetInitialValueAndVelocity`.\)|  
  
## Hinweise  
 Dieser Handler wird zu `IUIAnimationTransitionFactory::CreateTransition` erstellt und übergeben, wenn ein Objekt `CCustomTransition` während Teil des Animationsinitialisierungsprozesses erstellt wird \(durch `CAnimationController::AnimateGroup` gestartet\).  Normalerweise müssen Sie nicht, um diese Klasse direkt zu verwenden, es werden nur alle Ereignisse zu `CCustomInterpolator` von abgeleitete Klasse, deren Zeiger an den Konstruktor von `CCustomTransition` übergeben wird.  
  
## Vererbungshierarchie  
 `CUIAnimationCallbackBase`  
  
 `CUIAnimationInterpolatorBase`  
  
 `CInterpolatorBase`  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)