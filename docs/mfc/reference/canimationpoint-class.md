---
title: "CAnimationPoint Class"
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
  - "CAnimationPoint"
  - "afxanimationcontroller/CAnimationPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationPoint-Klasse"
ms.assetid: 5dc4d46f-e695-4681-b15c-544b78b3e317
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationPoint Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion eines Punkts, dessen Koordinaten animiert werden können.  
  
## Syntax  
  
```  
class CAnimationPoint : public CAnimationBaseObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::CAnimationPoint](../Topic/CAnimationPoint::CAnimationPoint.md)|Überladen.  Erstellt CAnimationPoint\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::AddTransition](../Topic/CAnimationPoint::AddTransition.md)|Fügt Übergänge für x\- und y\-Koordinaten hinzu.|  
|[CAnimationPoint::GetDefaultValue](../Topic/CAnimationPoint::GetDefaultValue.md)|Gibt die Standardwerte für x\- und y\-Koordinaten zurück.|  
|[CAnimationPoint::GetValue](../Topic/CAnimationPoint::GetValue.md)|Gibt aktuellen Wert zurück.|  
|[CAnimationPoint::GetX](../Topic/CAnimationPoint::GetX.md)|Stellt Zugriff auf CAnimationVariable für x\-Koordinate bereit.|  
|[CAnimationPoint::GetY](../Topic/CAnimationPoint::GetY.md)|Stellt Zugriff auf CAnimationVariable für y\-Koordinate bereit.|  
|[CAnimationPoint::SetDefaultValue](../Topic/CAnimationPoint::SetDefaultValue.md)|Legt den Standardwert fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::GetAnimationVariableList](../Topic/CAnimationPoint::GetAnimationVariableList.md)|Fügt die gekapselten Animationsvariablen in eine Liste ein.  \(Überschreibt [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::operator CPoint](../Topic/CAnimationPoint::operator%20CPoint.md)|Konvertiert einen CAnimationPoint in einen CPoint.|  
|[CAnimationPoint::operator\=](../Topic/CAnimationPoint::operator=.md)|Weist CAnimationPoint ptSrc zu.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationPoint::m\_xValue](../Topic/CAnimationPoint::m_xValue.md)|Die gekapselte Animationsvariable, die x\-Koordinate des Animationspunkts darstellt.|  
|[CAnimationPoint::m\_yValue](../Topic/CAnimationPoint::m_yValue.md)|Die gekapselte Animationsvariable, die y\-Koordinate des Animationspunkts darstellt.|  
  
## Hinweise  
 Die CAnimationPoint\-Klasse kapselt zwei CAnimationVariable\-Objekte und kann einen Punkt in Anwendungen darstellen.  Sie können mithilfe dieser Klasse z. B. eine Position eines beliebigen Objekts auf dem Bildschirm animieren \(wie Textzeichenfolgen, Kreise, Punkte usw.\).  Um diese Klasse in der Anwendung verwenden zu können, instanziieren Sie einfach ein Objekt dieser Klasse, fügen Sie es mit CAnimationController::AddAnimationObject dem Animationscontroller hinzu, und rufen Sie AddTransition für jeden Übergang auf, der auf X\- und\/oder Y\-Koordinaten angewendet werden soll.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationPoint](../../mfc/reference/canimationpoint-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)