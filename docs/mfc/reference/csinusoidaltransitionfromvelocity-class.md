---
title: "CSinusoidalTransitionFromVelocity-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSinusoidalTransitionFromVelocity"
  - "afxanimationcontroller/CSinusoidalTransitionFromVelocity"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSinusoidalTransitionFromVelocity-Klasse"
ms.assetid: cc885f17-b84b-45ee-8f1f-36a8bbb7adad
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSinusoidalTransitionFromVelocity-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen Übergang mit sinusförmiger Geschwindigkeit und einer Amplitude, die von der ursprünglichen Geschwindigkeit der Animationsvariablen bestimmt wird.  
  
## Syntax  
  
```  
class CSinusoidalTransitionFromVelocity : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity](../Topic/CSinusoidalTransitionFromVelocity::CSinusoidalTransitionFromVelocity.md)|Erstellt ein Übergangsobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::Create](../Topic/CSinusoidalTransitionFromVelocity::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CSinusoidalTransitionFromVelocity::m\_duration](../Topic/CSinusoidalTransitionFromVelocity::m_duration.md)|Die Dauer des Übergangs.|  
|[CSinusoidalTransitionFromVelocity::m\_period](../Topic/CSinusoidalTransitionFromVelocity::m_period.md)|Der Schwingungsperiode der sinusförmigen Welle in Sekunden.|  
  
## Hinweise  
 Der Wert der Animationsvariablen schwingt während der gesamten Dauer eines sinusförmigem Übergangs um den Anfangswert.  Die Amplitude der Schwingung wird von der Geschwindigkeit der Animationsvariable zu Beginn des Übergangs bestimmt.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CSinusoidalTransitionFromVelocity](../../mfc/reference/csinusoidaltransitionfromvelocity-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)