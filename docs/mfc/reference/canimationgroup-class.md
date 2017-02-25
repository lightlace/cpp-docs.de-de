---
title: "CAnimationGroup-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationGroup"
  - "CAnimationGroup"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationGroup-Klasse"
ms.assetid: 8bc18ceb-33a2-41d0-9731-71811adacab7
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationGroup-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine Animationsgruppe, in der ein Animationsdrehbuch, Animationsobjekte und Übergänge kombiniert werden, um eine Animation zu definieren.  
  
## Syntax  
  
```  
class CAnimationGroup;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationGroup::CAnimationGroup](../Topic/CAnimationGroup::CAnimationGroup.md)|Erstellt eine Animationsgruppe.|  
|[CAnimationGroup::~CAnimationGroup](../Topic/CAnimationGroup::~CAnimationGroup.md)|Der Destruktor.  Wird aufgerufen, wenn eine Animationsgruppe zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationGroup::Animate](../Topic/CAnimationGroup::Animate.md)|Animiert eine Gruppe.|  
|[CAnimationGroup::ApplyTransitions](../Topic/CAnimationGroup::ApplyTransitions.md)|Übernimmt Übergänge für Animationsobjekte.|  
|[CAnimationGroup::FindAnimationObject](../Topic/CAnimationGroup::FindAnimationObject.md)|Sucht ein Animationsobjekt, das die angegebene Animationsvariable enthält.|  
|[CAnimationGroup::GetGroupID](../Topic/CAnimationGroup::GetGroupID.md)|Gibt GroupID zurück.|  
|[CAnimationGroup::RemoveKeyframes](../Topic/CAnimationGroup::RemoveKeyframes.md)|Entfernt und zerstört optional alle Keyframes, die zu einer Animationsgruppe gehören.|  
|[CAnimationGroup::RemoveTransitions](../Topic/CAnimationGroup::RemoveTransitions.md)|Entfernt Übergänge aus Animationsobjekten, die zu einer Animationsgruppe gehören.|  
|[CAnimationGroup::Schedule](../Topic/CAnimationGroup::Schedule.md)|Plant eine Animation zu dem angegebenen Zeitpunkt.|  
|[CAnimationGroup::SetAutodestroyTransitions](../Topic/CAnimationGroup::SetAutodestroyTransitions.md)|Weist alle Animationsobjekte, die zu Gruppe gehören, an, Übergänge automatisch zu zerstören.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationGroup::AddKeyframes](../Topic/CAnimationGroup::AddKeyframes.md)|Eine Hilfe, die einem Storyboard Keyframes hinzufügt.|  
|[CAnimationGroup::AddTransitions](../Topic/CAnimationGroup::AddTransitions.md)|Eine Hilfe, die einem Storyboard Übergänge hinzufügt.|  
|[CAnimationGroup::CreateTransitions](../Topic/CAnimationGroup::CreateTransitions.md)|Eine Hilfe, die COM\-Übergangsobjekte erstellt.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationGroup::m\_bAutoclearTransitions](../Topic/CAnimationGroup::m_bAutoclearTransitions.md)|Gibt an, wie Übergänge von Animationsobjekten, die zu Gruppe gehören, gelöscht werden.  Wenn dieser Member TRUE ist, werden Übergänge automatisch entfernt, wenn eine Animation geplant wurde.  Andernfalls müssen Sie Übergänge manuell entfernen.|  
|[CAnimationGroup::m\_bAutodestroyAnimationObjects](../Topic/CAnimationGroup::m_bAutodestroyAnimationObjects.md)|Gibt an, wie Animationsobjekte zerstört werden.  Wenn dieser Parameter TRUE ist, werden Animationsobjekte automatisch zerstört, wenn die Gruppe zerstört wird.  Andernfalls müssen Animationsobjekte manuell zerstört werden.  Der Standardwert ist FALSE.  Legen Sie diesen Wert nur auf TRUE fest, wenn alle Animationsobjekte, die zur Gruppe gehören, dynamisch mit dem new\-Operator zugeordnet werden.|  
|[CAnimationGroup::m\_bAutodestroyKeyframes](../Topic/CAnimationGroup::m_bAutodestroyKeyframes.md)|Gibt an, wie Keyframes zerstört werden.  Wenn dieser Wert TRUE ist, werden alle Keyframes entfernt und zerstört. Andernfalls werden sie nur aus der Liste entfernt.  Der Standardwert ist TRUE.|  
|[CAnimationGroup::m\_lstAnimationObjects](../Topic/CAnimationGroup::m_lstAnimationObjects.md)|Enthält eine Liste von Animationsobjekten.|  
|[CAnimationGroup::m\_lstKeyFrames](../Topic/CAnimationGroup::m_lstKeyFrames.md)|Enthält eine Liste von Keyframes.|  
|[CAnimationGroup::m\_pStoryboard](../Topic/CAnimationGroup::m_pStoryboard.md)|Zeigt auf Animationsstoryboard.  Dieser Zeiger ist erst nach einem Aufruf von Animate gültig.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationGroup::m\_nGroupID](../Topic/CAnimationGroup::m_nGroupID.md)|Ein eindeutiger Bezeichner der Animationsgruppe.|  
|[CAnimationGroup::m\_pParentController](../Topic/CAnimationGroup::m_pParentController.md)|Ein Zeiger auf den Animationscontroller, zu dem diese Gruppe gehört.|  
  
## Hinweise  
 Animationsgruppen werden automatisch von Animationscontroller \(CAnimationController\) erstellt, wenn Sie Animationsobjekte mit CAnimationController::AddAnimationObject hinzufügen.  Eine Animationsgruppe wird durch eine GroupID identifiziert, die normalerweise als Parameter angegeben wird, um Animationsgruppen zu bearbeiten.  Die GroupID wird vom ersten Animationsobjekt abgerufen, das einer neuen Animationsgruppe hinzugefügt wird.  Ein gekapseltes Animationsstoryboard wird erstellt, nachdem Sie CAnimationController::AnimateGroup aufgerufen haben. Ein Zugriff ist über den öffentlichen Member m\_pStoryboard möglich.  
  
## Vererbungshierarchie  
 [CAnimationGroup](../../mfc/reference/canimationgroup-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)