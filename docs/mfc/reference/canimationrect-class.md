---
title: "CAnimationRect-Klasse"
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
  - "CAnimationRect"
  - "afxanimationcontroller/CAnimationRect"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationRect-Klasse"
ms.assetid: 0294156d-241e-4a57-92b2-31234fe557d6
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationRect-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion eines Rechtecks, dessen Seiten animiert werden können.  
  
## Syntax  
  
```  
class CAnimationRect : public CAnimationBaseObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::CAnimationRect](../Topic/CAnimationRect::CAnimationRect.md)|Überladen.  Erstellt ein Animation rect\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::AddTransition](../Topic/CAnimationRect::AddTransition.md)|Fügt Übergänge für links, oben, rechts und unten Koordinaten hinzu.|  
|[CAnimationRect::GetBottom](../Topic/CAnimationRect::GetBottom.md)|Bietet Zugriff auf CAnimationVariable, das Unterseitenkoordinate darstellt.|  
|[CAnimationRect::GetDefaultValue](../Topic/CAnimationRect::GetDefaultValue.md)|Gibt die Standardwerte für die Grenzen des Rechtecks zurück.|  
|[CAnimationRect::GetLeft](../Topic/CAnimationRect::GetLeft.md)|Bietet Zugriff auf CAnimationVariable, das linkskoordinate darstellt.|  
|[CAnimationRect::GetRight](../Topic/CAnimationRect::GetRight.md)|Bietet Zugriff auf CAnimationVariable, das Rechtkoordinate darstellt.|  
|[CAnimationRect::GetTop](../Topic/CAnimationRect::GetTop.md)|Bietet Zugriff auf CAnimationVariable, das Spitzenkoordinate darstellt.|  
|[CAnimationRect::GetValue](../Topic/CAnimationRect::GetValue.md)|Gibt aktuellen Wert zurück.|  
|[CAnimationRect::SetDefaultValue](../Topic/CAnimationRect::SetDefaultValue.md)|Legt Standardwert fest.|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::GetAnimationVariableList](../Topic/CAnimationRect::GetAnimationVariableList.md)|Setzt die gekapselten Animationsvariablen in eine Liste.  \(Überschreibungen [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::operator RECT](../Topic/CAnimationRect::operator%20RECT.md)|Konvertiert ein CAnimationRect in RECT.|  
|[CAnimationRect::operator\=](../Topic/CAnimationRect::operator=.md)|Weist CAnimationRect rect zu.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::m\_bFixedSize](../Topic/CAnimationRect::m_bFixedSize.md)|Gibt an, ob das Rechteck Größe behoben hat.|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CAnimationRect::m\_bottomValue](../Topic/CAnimationRect::m_bottomValue.md)|Die gekapselte Animationsvariablen, die untere Begrenzung des Animationsrechtecks darstellt.|  
|[CAnimationRect::m\_leftValue](../Topic/CAnimationRect::m_leftValue.md)|Die gekapselte Animationsvariablen, die linke Begrenzung des Animationsrechtecks darstellt.|  
|[CAnimationRect::m\_rightValue](../Topic/CAnimationRect::m_rightValue.md)|Die gekapselte Animationsvariablen, die richtige Begrenzung des Animationsrechtecks darstellt.|  
|[CAnimationRect::m\_szInitial](../Topic/CAnimationRect::m_szInitial.md)|Gibt ursprüngliche Größe des Animationsrechtecks an.|  
|[CAnimationRect::m\_topValue](../Topic/CAnimationRect::m_topValue.md)|Die gekapselte Animationsvariablen, die obere Begrenzung des Animationsrechtecks darstellt.|  
  
## Hinweise  
 Die CAnimationRect\-Klasse kapselt vier CAnimationVariable\-Objekte und kann in Anwendungen ein Rechteck darstellen.  Um diese Klasse in der Anwendung verwenden, nur ein Objekt dieser Klasse instanziieren, es dem Animationscontroller hinzuzufügen, der CAnimationController::AddAnimationObject und AddTransition aufzurufen verwendet, damit jeder Übergang zur links, Rechtspitze und zu den Unterseitenkoordinaten angewendet werden kann.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationRect](../../mfc/reference/canimationrect-class.md)  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)