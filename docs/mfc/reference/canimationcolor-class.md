---
title: "CAnimationColor-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationColor"
  - "afxanimationcontroller/CAnimationColor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationColor-Klasse"
ms.assetid: 88bfabd4-efeb-4652-87e8-304253d8e48c
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationColor-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion einer Farbe, deren Rot\-, Grün\- und Blauanteil animiert werden kann.  
  
## Syntax  
  
```  
class CAnimationColor : public CAnimationBaseObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationColor::CAnimationColor](../Topic/CAnimationColor::CAnimationColor.md)|Überladen.  Erstellt ein Animationsfarbobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationColor::AddTransition](../Topic/CAnimationColor::AddTransition.md)|Fügt Übergänge für Rot\-, Grün\- und Blauanteile hinzu.|  
|[CAnimationColor::GetB](../Topic/CAnimationColor::GetB.md)|Bietet Zugriff auf CAnimationVariable, die den Blauanteil darstellt.|  
|[CAnimationColor::GetDefaultValue](../Topic/CAnimationColor::GetDefaultValue.md)|Gibt die Standardwerte für Farbanteile zurück.|  
|[CAnimationColor::GetG](../Topic/CAnimationColor::GetG.md)|Bietet Zugriff auf CAnimationVariable, die den Grünanteil darstellt.|  
|[CAnimationColor::GetR](../Topic/CAnimationColor::GetR.md)|Bietet Zugriff auf CAnimationVariable, die den Rotanteil darstellt.|  
|[CAnimationColor::GetValue](../Topic/CAnimationColor::GetValue.md)|Gibt aktuellen Wert zurück.|  
|[CAnimationColor::SetDefaultValue](../Topic/CAnimationColor::SetDefaultValue.md)|Legt den Standardwert fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationColor::GetAnimationVariableList](../Topic/CAnimationColor::GetAnimationVariableList.md)|Fügt die gekapselten Animationsvariablen in eine Liste ein.  \(Überschreibt [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationColor::operator COLORREF](../Topic/CAnimationColor::operator%20COLORREF.md)||  
|[CAnimationColor::operator\=](../Topic/CAnimationColor::operator=.md)|Weist CAnimationColor Farbe zu.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationColor::m\_bValue](../Topic/CAnimationColor::m_bValue.md)|Die gekapselte Animationsvariable, die Blauanteil der Animationsfarbe darstellt.|  
|[CAnimationColor::m\_gValue](../Topic/CAnimationColor::m_gValue.md)|Die gekapselte Animationsvariable, die den Grünanteil der Animationsfarbe darstellt.|  
|[CAnimationColor::m\_rValue](../Topic/CAnimationColor::m_rValue.md)|Die gekapselte Animationsvariable, die den Rotanteil der Animationsfarbe darstellt.|  
  
## Hinweise  
 Die CAnimationColor\-Klasse kapselt drei CAnimationVariable\-Objekte und kann eine Farbe in Anwendungen darstellen.  Beispielsweise können Sie mit dieser Klasse Farben eines beliebigen Objekts auf dem Bildschirm \(Textfarbe, Hintergrundfarbe usw.\) animieren.  Um diese Klasse in der Anwendung verwenden zu können, instanziieren Sie einfach ein Objekt dieser Klasse, fügen Sie es mit CAnimationController::AddAnimationObject dem Animationscontroller hinzu, und rufen Sie AddTransition für jeden Übergang auf, der auf die Komponenten Red, Green und Blue angewendet werden soll.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationColor](../../mfc/reference/canimationcolor-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)