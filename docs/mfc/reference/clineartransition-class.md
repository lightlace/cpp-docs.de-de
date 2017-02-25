---
title: "CLinearTransition-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CLinearTransition"
  - "afxanimationcontroller/CLinearTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLinearTransition-Klasse"
ms.assetid: 7fcb2dba-beb8-4933-9f5d-3b7fb1585ef0
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CLinearTransition-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt einen linearen Übergang.  
  
## Syntax  
  
```  
class CLinearTransition : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransition::CLinearTransition](../Topic/CLinearTransition::CLinearTransition.md)|Erstellt ein lineares Übergangsobjekt und initialisiert es mit Dauer und endgültigem Wert.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransition::Create](../Topic/CLinearTransition::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CLinearTransition::m\_dblFinalValue](../Topic/CLinearTransition::m_dblFinalValue.md)|Der Wert der Animationsvariablen am Ende des Übergangs.|  
|[CLinearTransition::m\_duration](../Topic/CLinearTransition::m_duration.md)|Die Dauer des Übergangs.|  
  
## Hinweise  
 Während eines linearen Übergangs ändert sich der Wert der Animationsvariablen linear vom Anfangswert bis zu einem angegebenen Endwert.  Da alle Übergänge automatisch gelöscht werden, wird empfohlen, sie mit dem new\-Operator zuzuordnen.  Das gekapselte IUIAnimationTransition\-COM\-Objekt wird von CAnimationController::AnimateGroup erstellt. Bis zur Erstellung ist es NULL.  Das Ändern von Membervariablen nach der Erstellung dieses COM\-Objekts hat keine Auswirkungen.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CLinearTransition](../../mfc/reference/clineartransition-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)