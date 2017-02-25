---
title: "CDiscreteTransition-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDiscreteTransition"
  - "afxanimationcontroller/CDiscreteTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDiscreteTransition-Klasse"
ms.assetid: b4d84fb3-ccaa-451c-a69b-6b50dcb9b9c8
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CDiscreteTransition-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen einzelnen Übergang.  
  
## Syntax  
  
```  
class CDiscreteTransition : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDiscreteTransition::CDiscreteTransition](../Topic/CDiscreteTransition::CDiscreteTransition.md)|Erstellt ein einzelnes Übergangsobjekt und initialisiert seine Parameter.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDiscreteTransition::Create](../Topic/CDiscreteTransition::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDiscreteTransition::m\_dblFinalValue](../Topic/CDiscreteTransition::m_dblFinalValue.md)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CDiscreteTransition::m\_delay](../Topic/CDiscreteTransition::m_delay.md)|Die Menge an Zeit, um die die unmittelbare Umstellung auf den endgültigen Wert verzögert werden soll.|  
|[CDiscreteTransition::m\_hold](../Topic/CDiscreteTransition::m_hold.md)|Die Menge an Zeit, für die die Variable bei seinem endgültigen Wert gespeichert werden soll.|  
  
## Hinweise  
 Während eines diskreten Übergangs behält die Animationsvariable für eine angegebene Verzögerungszeit den Anfangswert bei und wechselt dann unverzüglich zu einem angegebenen Endwert, der für eine angegebene Haltezeit beibehalten wird.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CDiscreteTransition](../../mfc/reference/cdiscretetransition-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)