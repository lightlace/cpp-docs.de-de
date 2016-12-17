---
title: "CAnimationVariable-Klasse"
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
  - "CAnimationVariable"
  - "afxanimationcontroller/CAnimationVariable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationVariable-Klasse"
ms.assetid: 506e697e-31a8-4033-a27e-292f4d7b42d9
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationVariable-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Animationsvariable dar.  
  
## Syntax  
  
```  
class CAnimationVariable;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::CAnimationVariable](../Topic/CAnimationVariable::CAnimationVariable.md)|Erstellt ein Animationsvariablenobjekt.|  
|[CAnimationVariable::~CAnimationVariable](../Topic/CAnimationVariable::~CAnimationVariable.md)|Der Destruktor.  Wird aufgerufen, wenn ein CAnimationVariable\-Objekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::AddTransition](../Topic/CAnimationVariable::AddTransition.md)|Fügt einen Übergang hinzu.|  
|[CAnimationVariable::ApplyTransitions](../Topic/CAnimationVariable::ApplyTransitions.md)|Fügt Storyboard Übergänge von der internen Liste hinzu.|  
|[CAnimationVariable::ClearTransitions](../Topic/CAnimationVariable::ClearTransitions.md)|Löscht Übergänge.|  
|[CAnimationVariable::Create](../Topic/CAnimationVariable::Create.md)|Erstellt das zugrunde liegende Animationsvariablen\-COM\-Objekt.|  
|[CAnimationVariable::CreateTransitions](../Topic/CAnimationVariable::CreateTransitions.md)|Erstellt alle Übergänge, die auf diese Animationsvariable angewendet werden sollen.|  
|[CAnimationVariable::EnableIntegerValueChangedEvent](../Topic/CAnimationVariable::EnableIntegerValueChangedEvent.md)|Aktiviert oder deaktiviert das IntegerValueChanged\-Ereignis.|  
|[CAnimationVariable::EnableValueChangedEvent](../Topic/CAnimationVariable::EnableValueChangedEvent.md)|Aktiviert oder deaktiviert das ValueChanged\-Ereignis.|  
|[CAnimationVariable::GetDefaultValue](../Topic/CAnimationVariable::GetDefaultValue.md)|Gibt Standardwert zurück.|  
|[CAnimationVariable::GetParentAnimationObject](../Topic/CAnimationVariable::GetParentAnimationObject.md)|Gibt das übergeordnete Animationsobjekt zurück.|  
|[CAnimationVariable::GetValue](../Topic/CAnimationVariable::GetValue.md)|Überladen.  Gibt den aktuellen Wert der Animationsvariable zurück.|  
|[CAnimationVariable::GetVariable](../Topic/CAnimationVariable::GetVariable.md)|Gibt einen Zeiger auf IUIAnimationVariable\-COM\-Objekt zurück.|  
|[CAnimationVariable::SetDefaultValue](../Topic/CAnimationVariable::SetDefaultValue.md)|Legt Standardwert fest und gibt IUIAnimationVariable\-COM\-Objekt frei.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::SetParentAnimationObject](../Topic/CAnimationVariable::SetParentAnimationObject.md)|Legt die Beziehung zwischen einer Animationsvariable und einem Animationsobjekt fest.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::m\_bAutodestroyTransitions](../Topic/CAnimationVariable::m_bAutodestroyTransitions.md)|Gibt an, ob verwandte Übergangsobjekte gelöscht werden sollen.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationVariable::m\_dblDefaultValue](../Topic/CAnimationVariable::m_dblDefaultValue.md)|Gibt den Standardwert an, der an IUIAnimationVariable weitergegeben wird.|  
|[CAnimationVariable::m\_lstTransitions](../Topic/CAnimationVariable::m_lstTransitions.md)|Enthält eine Liste von Übergängen, die diese Animationsvariable animieren.|  
|[CAnimationVariable::m\_pParentObject](../Topic/CAnimationVariable::m_pParentObject.md)|Ein Zeiger auf ein Animationsobjekt, das diese Animationsvariable kapselt.|  
|[CAnimationVariable::m\_variable](../Topic/CAnimationVariable::m_variable.md)|Speichert einen Zeiger auf IUIAnimationVariable\-COM\-Objekt.  NULL, wenn das COM\-Objekt noch nicht erstellt wurde oder wenn die Erstellung fehlschlug.|  
  
## Hinweise  
 Die CAnimationVariable\-Klasse kapselt IUIAnimationVariable\-COM\-Objekt.  Es enthält auch eine Liste von Übergängen, die auf die Animationsvariable in einem Storyboard angewendet werden soll.  CAnimationVariable\-Objekte werden in Animationsobjekten eingebettet, die in einer Anwendung einen animierten Wert, einen Punkt, eine Größe, eine Farbe oder ein Rechteck darstellen können.  
  
## Vererbungshierarchie  
 [CAnimationVariable](../../mfc/reference/canimationvariable-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)