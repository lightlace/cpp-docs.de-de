---
title: "CAnimationBaseObject-Klasse"
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
  - "afxanimationcontroller/CAnimationBaseObject"
  - "CAnimationBaseObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationBaseObject-Klasse"
ms.assetid: 76b25917-940e-4eba-940f-31d270702603
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationBaseObject-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse für alle Animationsobjekte.  
  
## Syntax  
  
```  
class CAnimationBaseObject : public CObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationBaseObject::CAnimationBaseObject](../Topic/CAnimationBaseObject::CAnimationBaseObject.md)|Überladen.  Erstellt ein Animationsobjekt.|  
|[CAnimationBaseObject::~CAnimationBaseObject](../Topic/CAnimationBaseObject::~CAnimationBaseObject.md)|Der Destruktor.  Wird aufgerufen, wenn ein Animationsobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationBaseObject::ApplyTransitions](../Topic/CAnimationBaseObject::ApplyTransitions.md)|Fügt Storyboard Übergänge mit gekapselter Animationsvariable hinzu.|  
|[CAnimationBaseObject::ClearTransitions](../Topic/CAnimationBaseObject::ClearTransitions.md)|Entfernt alle verwandten Übergänge.|  
|[CAnimationBaseObject::ContainsVariable](../Topic/CAnimationBaseObject::ContainsVariable.md)|Bestimmt, ob ein Animationsobjekt eine bestimmte Animationsvariable enthält.|  
|[CAnimationBaseObject::CreateTransitions](../Topic/CAnimationBaseObject::CreateTransitions.md)|Erstellt einem Animationsobjekt zugeordnete Übergänge.|  
|[CAnimationBaseObject::DetachFromController](../Topic/CAnimationBaseObject::DetachFromController.md)|Trennt ein Animationsobjekt von übergeordnetem Animationscontroller.|  
|[CAnimationBaseObject::EnableIntegerValueChangedEvent](../Topic/CAnimationBaseObject::EnableIntegerValueChangedEvent.md)|Richtet IntegerValueChanged\-Ereignishandler ein.|  
|[CAnimationBaseObject::EnableValueChangedEvent](../Topic/CAnimationBaseObject::EnableValueChangedEvent.md)|Richtet ValueChanged\-Ereignishandler ein.|  
|[CAnimationBaseObject::GetAutodestroyTransitions](../Topic/CAnimationBaseObject::GetAutodestroyTransitions.md)|Gibt an, ob verwandter Übergang automatisch zerstört wird.|  
|[CAnimationBaseObject::GetGroupID](../Topic/CAnimationBaseObject::GetGroupID.md)|Gibt aktuelle Gruppen\-ID zurück.|  
|[CAnimationBaseObject::GetObjectID](../Topic/CAnimationBaseObject::GetObjectID.md)|Gibt die aktuelle Objekt\-ID zurück.|  
|[CAnimationBaseObject::GetUserData](../Topic/CAnimationBaseObject::GetUserData.md)|Gibt benutzerdefinierte Daten zurück.|  
|[CAnimationBaseObject::SetAutodestroyTransitions](../Topic/CAnimationBaseObject::SetAutodestroyTransitions.md)|Legt ein Flag fest, das befiehlt, Übergänge automatisch zu zerstören.|  
|[CAnimationBaseObject::SetID](../Topic/CAnimationBaseObject::SetID.md)|Legt neue IDs fest.|  
|[CAnimationBaseObject::SetUserData](../Topic/CAnimationBaseObject::SetUserData.md)|Legt benutzerdefinierte Daten fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md)|Sammelt Zeiger auf enthaltene Animationsvariablen.|  
|[CAnimationBaseObject::SetParentAnimationObjects](../Topic/CAnimationBaseObject::SetParentAnimationObjects.md)|Legt Beziehung zwischen in einem Animationsobjekt enthaltenen Animationsvariablen und ihrem Container fest.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationBaseObject::m\_bAutodestroyTransitions](../Topic/CAnimationBaseObject::m_bAutodestroyTransitions.md)|Gibt an, ob verwandte Übergänge automatisch zerstört werden sollen.|  
|[CAnimationBaseObject::m\_dwUserData](../Topic/CAnimationBaseObject::m_dwUserData.md)|Speichert benutzerdefinierte Daten.|  
|[CAnimationBaseObject::m\_nGroupID](../Topic/CAnimationBaseObject::m_nGroupID.md)|Gibt die Gruppen\-ID des Animationsobjekts an.|  
|[CAnimationBaseObject::m\_nObjectID](../Topic/CAnimationBaseObject::m_nObjectID.md)|Gibt die Objekt\-ID des Animationsobjekts an.|  
|[CAnimationBaseObject::m\_pParentController](../Topic/CAnimationBaseObject::m_pParentController.md)|Ein Zeiger auf den übergeordneten Animationscontroller.|  
  
## Hinweise  
 Diese Klasse implementiert grundlegende Methoden für alle Animationsobjekte.  Ein Animationsobjekt kann einen Wert, einen Punkt, eine Größe, ein Rechteck oder eine Farbe in einer Anwendung, aber auch eine benutzerdefinierte Entität darstellen.  Animationsobjekte werden in Animationsgruppen gespeichert \(siehe CAnimationGroup\).  Jede Gruppe kann getrennt animiert werden und als Entsprechung des Storyboards behandelt werden.  Ein Animationsobjekt kapselt eine oder mehrere Animationsvariablen \(siehe CAnimationVariable\), abhängig von seiner logischen Darstellung.  CAnimationRect enthält z. B. vier Animationsvariablen \- eine Variable für jede Seite des Rechtecks.  Jede Animationsobjektklasse legt eine überladene AddTransition\-Methode offen, die verwendet werden sollte, um Übergänge auf gekapselte Animationsvariablen anzuwenden.  Ein Animationsobjekt kann von Objekt\-ID \(optional\) und Gruppen\-ID identifiziert werden.  Eine Gruppen\-ID ist notwendig, um ein Animationsobjekt korrekt zu einer Gruppe zu platzieren. Wenn keine Gruppen\-ID angegeben ist, wird ein Objekt in der Standardgruppe mit der ID 0 platziert.  Wenn Sie SetID mit einer anderen GroupID aufrufen, wird ein Animationsobjekt in eine andere Gruppe verschoben \(bei Bedarf wird eine neue Gruppe erstellt\).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)