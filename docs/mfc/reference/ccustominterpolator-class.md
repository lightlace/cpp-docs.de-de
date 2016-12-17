---
title: "CCustomInterpolator-Klasse"
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
  - "afxanimationcontroller/CCustomInterpolator"
  - "CCustomInterpolator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomInterpolator-Klasse"
ms.assetid: 28d85595-989a-40a3-b003-e0e38437a94d
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CCustomInterpolator-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen einfachen Interpolator.  
  
## Syntax  
  
```  
class CCustomInterpolator;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCustomInterpolator::CCustomInterpolator](../Topic/CCustomInterpolator::CCustomInterpolator.md)|Überladen.  Erstellt ein benutzerdefiniertes Interpolatorobjekt und initialisiert Dauer und Geschwindigkeit zu den angegebenen Werten.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCustomInterpolator::GetDependencies](../Topic/CCustomInterpolator::GetDependencies.md)|Ruft die Abhängigkeiten des Interpolators ab.|  
|[CCustomInterpolator::GetDuration](../Topic/CCustomInterpolator::GetDuration.md)|Ruft die Dauer des Interpolators ab.|  
|[CCustomInterpolator::GetFinalValue](../Topic/CCustomInterpolator::GetFinalValue.md)|Ruft den endgültigen Wert ab, auf den der Interpolator führt.|  
|[CCustomInterpolator::Init](../Topic/CCustomInterpolator::Init.md)|Initialisiert Dauer und endgültigen Wert.|  
|[CCustomInterpolator::InterpolateValue](../Topic/CCustomInterpolator::InterpolateValue.md)|Interpolieren den Wert an einem angegebenen Offset.|  
|[CCustomInterpolator::InterpolateVelocity](../Topic/CCustomInterpolator::InterpolateVelocity.md)|Interpolieren die Geschwindigkeit an einem angegebenen Offset|  
|[CCustomInterpolator::SetDuration](../Topic/CCustomInterpolator::SetDuration.md)|Legt die Dauer des Interpolators fest.|  
|[CCustomInterpolator::SetInitialValueAndVelocity](../Topic/CCustomInterpolator::SetInitialValueAndVelocity.md)|Legt den Anfangswert und die Geschwindigkeit Interpolators fest.|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCustomInterpolator::m\_currentValue](../Topic/CCustomInterpolator::m_currentValue.md)|Der interpolierte Wert.|  
|[CCustomInterpolator::m\_currentVelocity](../Topic/CCustomInterpolator::m_currentVelocity.md)|Die interpolierte Geschwindigkeit.|  
|[CCustomInterpolator::m\_duration](../Topic/CCustomInterpolator::m_duration.md)|Die Dauer des Übergangs.|  
|[CCustomInterpolator::m\_finalValue](../Topic/CCustomInterpolator::m_finalValue.md)|Der letzte Wert einer Variablen am Ende des Übergangs.|  
|[CCustomInterpolator::m\_initialValue](../Topic/CCustomInterpolator::m_initialValue.md)|Der Wert der Variablen am Anfang des Übergangs.|  
|[CCustomInterpolator::m\_initialVelocity](../Topic/CCustomInterpolator::m_initialVelocity.md)|Die Geschwindigkeit der Variablen am Anfang des Übergangs.|  
  
## Hinweise  
 Leiten Sie eine Klasse von CCustomInterpolator und überschreiben Sie alle notwendigen Methoden, um einen benutzerdefinierten Interpolationsalgorithmus zu implementieren.  Ein Zeiger auf diese Klasse sollte als Parameter an CCustomTransition übergeben werden.  
  
## Vererbungshierarchie  
 [CCustomInterpolator](../../mfc/reference/ccustominterpolator-class.md)  
  
## Anforderungen  
 **Header:**  afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)