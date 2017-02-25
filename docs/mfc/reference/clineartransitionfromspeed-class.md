---
title: "CLinearTransitionFromSpeed-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CLinearTransitionFromSpeed"
  - "CLinearTransitionFromSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransitionFromSpeed-Klasse"
ms.assetid: 8f159a1c-8893-4017-951e-09e5758aba7d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CLinearTransitionFromSpeed-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen Übergang mit linearer Geschwindigkeit.  
  
## Syntax  
  
```  
class CLinearTransitionFromSpeed : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::CLinearTransitionFromSpeed](../Topic/CLinearTransitionFromSpeed::CLinearTransitionFromSpeed.md)|Erstellt ein Übergangsobjekt mit linearer Geschwindigkeit und initialisiert es mit der Geschwindigkeit und dem endgültigen Wert.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::Create](../Topic/CLinearTransitionFromSpeed::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransitionFromSpeed::m\_dblFinalValue](../Topic/CLinearTransitionFromSpeed::m_dblFinalValue.md)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CLinearTransitionFromSpeed::m\_dblSpeed](../Topic/CLinearTransitionFromSpeed::m_dblSpeed.md)|Der absolute Wert der Geschwindigkeit der Variable.|  
  
## Hinweise  
 Während eines Übergangs mit linearer Geschwindigkeit, ändert sich der Wert der Animationsvariablen zu einer angegebenen Rate.  Die Dauer des Übergangs wird aus der Differenz zwischen dem Anfangswert und dem angegebenen Endwert bestimmt.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransitionFromSpeed](../../mfc/reference/clineartransitionfromspeed-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)