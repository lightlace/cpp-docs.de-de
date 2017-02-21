---
title: "CBaseTransition-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CBaseTransition"
  - "afxanimationcontroller/CBaseTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBaseTransition-Klasse"
ms.assetid: dfe84007-bbc5-43b7-b5b8-fae9145573bf
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CBaseTransition-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen einfachen Übergang dar.  
  
## Syntax  
  
```  
class CBaseTransition : public CObject;  
```  
  
## Mitglieder  
  
### Öffentliche Enumeration  
  
|Name|Description|  
|----------|-----------------|  
|[CBaseTransition::TRANSITION\_TYPE \- Enumeration](../Topic/CBaseTransition::TRANSITION_TYPE%20Enumeration.md)|Definiert die gerade von der MFC\-Implementierung der Windows\-Animations\-API unterstützten Übergangstypen.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CBaseTransition::CBaseTransition](../Topic/CBaseTransition::CBaseTransition.md)|Erstellt ein Basisübergangsobjekt.|  
|[CBaseTransition::~CBaseTransition](../Topic/CBaseTransition::~CBaseTransition.md)|Der Destruktor.  Wird aufgerufen, wenn ein Übergangsobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CBaseTransition::AddToStoryboard](../Topic/CBaseTransition::AddToStoryboard.md)|Fügt einem Storyboard einen Übergang hinzu.|  
|[CBaseTransition::AddToStoryboardAtKeyframes](../Topic/CBaseTransition::AddToStoryboardAtKeyframes.md)|Fügt einem Storyboard einen Übergang hinzu.|  
|[CBaseTransition::Clear](../Topic/CBaseTransition::Clear.md)|Gibt gekapseltes IUIAnimationTransitions\-COM\-Objekt frei.|  
|[CBaseTransition::Create](../Topic/CBaseTransition::Create.md)|Erstellt einen COM\-Übergang.|  
|[CBaseTransition::GetEndKeyframe](../Topic/CBaseTransition::GetEndKeyframe.md)|Gibt den Startkeyframe zurück.|  
|[CBaseTransition::GetRelatedVariable](../Topic/CBaseTransition::GetRelatedVariable.md)|Gibt einen Zeiger auf verwandte Variable zurück.|  
|[CBaseTransition::GetStartKeyframe](../Topic/CBaseTransition::GetStartKeyframe.md)|Gibt den Startkeyframe zurück.|  
|[CBaseTransition::GetTransition](../Topic/CBaseTransition::GetTransition.md)|Überladen.  Gibt einen Zeiger auf zugrunde liegendes COM\-Übergangsobjekt zurück.|  
|[CBaseTransition::GetType](../Topic/CBaseTransition::GetType.md)|Gibt Übergangstyp zurück.|  
|[CBaseTransition::IsAdded](../Topic/CBaseTransition::IsAdded.md)|Gibt an, ob Storyboard ein Übergang hinzugefügt wurde.|  
|[CBaseTransition::SetKeyframes](../Topic/CBaseTransition::SetKeyframes.md)|Legt Keyframes für einen Übergang fest.|  
|[CBaseTransition::SetRelatedVariable](../Topic/CBaseTransition::SetRelatedVariable.md)|Legt eine Beziehung zwischen Animationsvariable und Übergang fest.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CBaseTransition::m\_bAdded](../Topic/CBaseTransition::m_bAdded.md)|Gibt an, ob einem Storyboard ein Übergang hinzugefügt wurde.|  
|[CBaseTransition::m\_pEndKeyframe](../Topic/CBaseTransition::m_pEndKeyframe.md)|Speichert einen Zeiger auf den Keyframe, der das Ende des Übergangs angibt.|  
|[CBaseTransition::m\_pRelatedVariable](../Topic/CBaseTransition::m_pRelatedVariable.md)|Ein Zeiger auf eine Animationsvariable, die mit dem in m\_transition gespeicherten Übergang animiert wird.|  
|[CBaseTransition::m\_pStartKeyframe](../Topic/CBaseTransition::m_pStartKeyframe.md)|Speichert einen Zeiger auf den Keyframe, der den Anfang des Übergangs angibt.|  
|[CBaseTransition::m\_transition](../Topic/CBaseTransition::m_transition.md)|Speichert einen Zeiger auf IUIAnimationTransition.  NULL, wenn ein COM\-Übergangsobjekt nicht erstellt wurde.|  
|[CBaseTransition::m\_type](../Topic/CBaseTransition::m_type.md)|Speichert den Übergangstyp.|  
  
## Hinweise  
 Diese Klasse kapselt die IUIAnimationTransitions\-Schnittstelle und dient als Basisklasse für alle Übergänge.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)