---
title: "CParabolicTransitionFromAcceleration-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CParabolicTransitionFromAcceleration"
  - "CParabolicTransitionFromAcceleration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CParabolicTransitionFromAcceleration-Klasse"
ms.assetid: 1e59b86f-358b-4da0-a4fd-8eaf5e85e00f
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CParabolicTransitionFromAcceleration-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen Übergang mit parabelförmiger Beschleunigung.  
  
## Syntax  
  
```  
class CParabolicTransitionFromAcceleration : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration](../Topic/CParabolicTransitionFromAcceleration::CParabolicTransitionFromAcceleration.md)|Erstellt einen Übergang mit parabelförmiger Beschleunigung und initialisiert es mit angegebenen Parametern.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::Create](../Topic/CParabolicTransitionFromAcceleration::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CParabolicTransitionFromAcceleration::m\_dblAcceleration](../Topic/CParabolicTransitionFromAcceleration::m_dblAcceleration.md)|Die Beschleunigung der Animationsvariable vom Übergang.|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalValue](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalValue.md)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CParabolicTransitionFromAcceleration::m\_dblFinalVelocity](../Topic/CParabolicTransitionFromAcceleration::m_dblFinalVelocity.md)|Die Geschwindigkeit der Animationsvariablen am Ende des Übergangs.|  
  
## Hinweise  
 Während eines Übergangs mit parabelförmiger Beschleunigung ändert sich der Wert der Animationsvariablen vom Anfangswert bis zu einem angegebenen Endwert und endet dabei mit einer angegebenen Geschwindigkeit.  Sie können steuern, wie schnell die Variable den Endwert erreicht, indem Sie die Rate der Beschleunigung angeben.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CParabolicTransitionFromAcceleration](../../mfc/reference/cparabolictransitionfromacceleration-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)