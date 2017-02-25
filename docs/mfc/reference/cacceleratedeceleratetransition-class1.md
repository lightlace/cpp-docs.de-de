---
title: "CAccelerateDecelerateTransition-Class1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAccelerateDecelerateTransition"
  - "afxanimationcontroller/CAccelerateDecelerateTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccelerateDecelerateTransition-Klasse"
ms.assetid: b1f31ee8-bb11-4ccc-b124-365fb02b025c
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# CAccelerateDecelerateTransition-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen Übergang mit Beschleunigung\/Verlangsamung.  
  
## Syntax  
  
```  
class CAccelerateDecelerateTransition : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::CAccelerateDecelerateTransition](../Topic/CAccelerateDecelerateTransition::CAccelerateDecelerateTransition.md)|Erstellt ein Übergangsobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::Create](../Topic/CAccelerateDecelerateTransition::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAccelerateDecelerateTransition::m\_accelerationRatio](../Topic/CAccelerateDecelerateTransition::m_accelerationRatio.md)|Das Verhältnis zur während der Beschleunigung verstrichenen Zeit.|  
|[CAccelerateDecelerateTransition::m\_decelerationRatio](../Topic/CAccelerateDecelerateTransition::m_decelerationRatio.md)|Das Verhältnis zur während der Verlangsamung verstrichenen Zeit.|  
|[CAccelerateDecelerateTransition::m\_duration](../Topic/CAccelerateDecelerateTransition::m_duration.md)|Die Dauer des Übergangs.|  
|[CAccelerateDecelerateTransition::m\_finalValue](../Topic/CAccelerateDecelerateTransition::m_finalValue.md)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
  
## Hinweise  
 Während eines Übergangs mit Beschleunigung\/Verlangsamung wird die Animationsvariable über die Dauer des Übergangs beschleunigt und anschließend verlangsamt und endet mit einem angegebenen Wert.  Sie können unabhängig voneinander steuern, wie schnell die Variable beschleunigt und langsamer wird, indem Sie unterschiedliche Beschleunigungs\- und Verlangsamungsraten angeben.  Wenn die ursprüngliche Geschwindigkeit 0 \(null\) ist, ist die Beschleunigungsrate der Zeitabschnitt, in dem die Variable beschleunigt. Ebenso verhält es sich mit der Verlangsamungsrate.  Wenn die ursprüngliche Geschwindigkeit ungleich 0 \(null\) ist, ist dies der Zeitabschnitt zwischen dem Erreichen der Geschwindigkeit 0 \(null\) und dem Ende des Übergangs.  Das Beschleunigungsverhältnis und das Verlangsamungsverhältnis sollten in der Summe maximal 1.0 ergeben.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CAccelerateDecelerateTransition](../../mfc/reference/cacceleratedeceleratetransition-class1.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)