---
title: "CCustomTransition-Klasse"
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
  - "afxanimationcontroller/CCustomTransition"
  - "CCustomTransition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCustomTransition-Klasse"
ms.assetid: 5bd3f492-940f-4290-a38b-fa68eb8f8401
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CCustomTransition-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert einen benutzerdefinierten Übergang.  
  
## Syntax  
  
```  
class CCustomTransition : public CBaseTransition;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CCustomTransition::CCustomTransition](../Topic/CCustomTransition::CCustomTransition.md)|Erstellt ein benutzerdefiniertes Übergangsobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CCustomTransition::Create](../Topic/CCustomTransition::Create.md)|Ruft die Übergangsbibliothek auf, um ein gekapseltes COM\-Übergangsobjekt zu erstellen.  \(Überschreibt [CBaseTransition::Create](../Topic/CBaseTransition::Create.md).\)|  
|[CCustomTransition::SetInitialValue](../Topic/CCustomTransition::SetInitialValue.md)|Legt einen Anfangswert fest, der für eine diesem Übergang zugeordnete Animationsvariable übernommen wird.|  
|[CCustomTransition::SetInitialVelocity](../Topic/CCustomTransition::SetInitialVelocity.md)|Legt eine Anfangsgeschwindigkeit fest, die für eine diesem Übergang zugeordnete Animationsvariable übernommen wird.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CCustomTransition::m\_bInitialValueSpecified](../Topic/CCustomTransition::m_bInitialValueSpecified.md)|Gibt an, ob der Anfangswert mit SetInitialValue angegeben wurde.|  
|[CCustomTransition::m\_bInitialVelocitySpecified](../Topic/CCustomTransition::m_bInitialVelocitySpecified.md)|Gibt an, ob die ursprüngliche Geschwindigkeit mit SetInitialVelocity angegeben wurde.|  
|[CCustomTransition::m\_initialValue](../Topic/CCustomTransition::m_initialValue.md)|Speichert den Anfangswert.|  
|[CCustomTransition::m\_initialVelocity](../Topic/CCustomTransition::m_initialVelocity.md)|Speichert die ursprüngliche Geschwindigkeit.|  
|[CCustomTransition::m\_pInterpolator](../Topic/CCustomTransition::m_pInterpolator.md)|Speichert einen Zeiger auf einen benutzerdefinierten Interpolator.|  
  
## Hinweise  
 Die CCustomTransitions\-Klasse ermöglicht es Entwicklern, benutzerdefinierte Übergänge zu implementieren.  Sie wird erstellt und als Standardübergang verwendet, aber ihr Konstruktor akzeptiert einen Zeiger auf einen benutzerdefinierten Interpolator als Parameter.  Führen Sie die folgenden Schritten zu Verwendung benutzerdefinierte Übergänge aus: 1.  Leiten Sie eine Klasse von CCustomInterpolator ab, und implementieren Sie mindestens InterpolateValue\-Methode.  2.  Stellen Sie sicher, dass die Lebensdauer des benutzerdefinierten Interpolatorobjekts länger ist als Lebensdauer der Animation, in der es verwendet wird.  3.  Instanziieren Sie \(mit dem Operator new\) ein CCustomTransitions\-Objekt, und übergeben Sie im Konstruktor einen Zeiger an benutzerdefinierten Interpolator.  4.  Rufen Sie CCustomTransition::SetInitialValue und CCustomTransition::SetInitialVelocity auf, wenn diese Parameter für benutzerdefinierte Interpolation erforderlich sind.  5.  Übergeben Sie den Zeiger auf den benutzerdefinierten Übergang an die AddTransitions\-Methode des Animationsobjekts, dessen Wert mit dem benutzerdefinierten Algorithmus animiert werden soll.  6.  Wenn sich der Wert des Animationsobjekts ändert, ruft die Windows\-Animations\-API InterpolateValue und andere relevante Methoden\) in CCustomInterpolator auf.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CBaseTransition](../../mfc/reference/cbasetransition-class.md)  
  
 [CCustomTransition](../../mfc/reference/ccustomtransition-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)