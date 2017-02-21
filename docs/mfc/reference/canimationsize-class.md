---
title: "CAnimationSize-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationSize"
  - "CAnimationSize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationSize-Klasse"
ms.assetid: ea06d1b5-502c-44a3-82ca-8bd6ba6a9364
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationSize-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion eines Größenobjekts, dessen Dimensionen animiert werden können.  
  
## Syntax  
  
```  
class CAnimationSize : public CAnimationBaseObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationSize::CAnimationSize](../Topic/CAnimationSize::CAnimationSize.md)|Überladen.  Erstellt ein Animationsgrößenobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationSize::AddTransition](../Topic/CAnimationSize::AddTransition.md)|Fügt Übergänge für Breite und Höhe hinzu.|  
|[CAnimationSize::GetCX](../Topic/CAnimationSize::GetCX.md)|Bietet Zugriff auf CAnimationVariable, die die Breite darstellt.|  
|[CAnimationSize::GetCY](../Topic/CAnimationSize::GetCY.md)|Bietet Zugriff auf CAnimationVariable, die die Höhe darstellt.|  
|[CAnimationSize::GetDefaultValue](../Topic/CAnimationSize::GetDefaultValue.md)|Gibt die Standardwerte für Breite und Höhe zurück.|  
|[CAnimationSize::GetValue](../Topic/CAnimationSize::GetValue.md)|Gibt aktuellen Wert zurück.|  
|[CAnimationSize::SetDefaultValue](../Topic/CAnimationSize::SetDefaultValue.md)|Legt den Standardwert fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationSize::GetAnimationVariableList](../Topic/CAnimationSize::GetAnimationVariableList.md)|Fügt die gekapselten Animationsvariablen in eine Liste ein.  \(Überschreibt [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationSize::operator CSize](../Topic/CAnimationSize::operator%20CSize.md)|Konvertiert einen CAnimationSize in einen CSize.|  
|[CAnimationSize::operator\=](../Topic/CAnimationSize::operator=.md)|Weist CAnimationSize szSrc zu.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationSize::m\_cxValue](../Topic/CAnimationSize::m_cxValue.md)|Die gekapselte Animationsvariable, die die Breite der Animationsgröße darstellt.|  
|[CAnimationSize::m\_cyValue](../Topic/CAnimationSize::m_cyValue.md)|Die gekapselte Animationsvariable, die die Höhe der Animationsgröße darstellt.|  
  
## Hinweise  
 Die CAnimationSize\-Klasse kapselt zwei CAnimationVariable\-Objekte und kann eine Größe in Anwendungen darstellen.  Beispielsweise können Sie mithilfe dieser Klasse eine Größe irgendeines zweidimensionalen Objekts auf dem Bildschirm \(Rechteck, Steuerelement usw.\) animieren.  Um diese Klasse in der Anwendung verwenden zu können, instanziieren Sie einfach ein Objekt dieser Klasse, fügen Sie es mit CAnimationController::AddAnimationObject dem Animationscontroller hinzu, und rufen Sie AddTransition für jeden Übergang auf, der auf Width und\/oder Height angewendet werden soll.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationSize](../../mfc/reference/canimationsize-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)