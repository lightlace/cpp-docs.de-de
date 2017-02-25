---
title: "CAnimationValue-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxanimationcontroller/CAnimationValue"
  - "CAnimationValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationValue-Klasse"
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CAnimationValue-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert die Funktion eines Animationsobjekts, das über einen Wert verfügt.  
  
## Syntax  
  
```  
class CAnimationValue : public CAnimationBaseObject;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationValue::CAnimationValue](../Topic/CAnimationValue::CAnimationValue.md)|Überladen.  Erstellt ein CAnimationValue\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationValue::AddTransition](../Topic/CAnimationValue::AddTransition.md)|Fügt einen Übergang hinzu, der auf einen Wert angewendet werden soll.|  
|[CAnimationValue::GetValue](../Topic/CAnimationValue::GetValue.md)|Überladen.  Ruft den aktuellen Wert ab.|  
|[CAnimationValue::GetVariable](../Topic/CAnimationValue::GetVariable.md)|Bietet Zugriff auf gekapselte Animationsvariable.|  
|[CAnimationValue::SetDefaultValue](../Topic/CAnimationValue::SetDefaultValue.md)|Legt den Standardwert fest.|  
  
### Geschützte Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationValue::GetAnimationVariableList](../Topic/CAnimationValue::GetAnimationVariableList.md)|Fügt die gekapselte Animationsvariable in eine Liste ein.  \(Überschreibt [CAnimationBaseObject::GetAnimationVariableList](../Topic/CAnimationBaseObject::GetAnimationVariableList.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationValue::operator DOUBLE](../Topic/CAnimationValue::operator%20DOUBLE.md)|Stellt Konvertierung in CAnimationValue und DOUBLE bereit.|  
|[CAnimationValue::operator INT32](../Topic/CAnimationValue::operator%20INT32.md)|Stellt Konvertierung in CAnimationValue und INT32 bereit.|  
|[CAnimationValue::operator\=](../Topic/CAnimationValue::operator=.md)|Überladen.  Weist CAnimationValue einen INT32\-Wert zu.|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CAnimationValue::m\_value](../Topic/CAnimationValue::m_value.md)|Die gekapselte Animationsvariable, die Animationswert darstellt.|  
  
## Hinweise  
 Die CAnimationValue\-Klasse kapselt ein einzelnes CAnimationVariable\-Objekt und kann einen einzelnen animierten Wert in Anwendungen darstellen.  Sie können diese Klasse z. B. für animierte Transparenz \(Ausblendeffekt\), Winkel \(zum Drehen von Objekten\) oder für einen beliebigen anderen Fall verwenden, wenn Sie abhängig von einem einzelnen animierten Wert eine Animation erstellen müssen.  Um diese Klasse in der Anwendung verwenden zu können, instanziieren Sie einfach ein Objekt dieser Klasse, fügen Sie es mit CAnimationController::AddAnimationObject dem Animationscontroller hinzu, und rufen Sie AddTransition für jeden Übergang auf, der auf den Wert angewendet werden soll.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)  
  
 [CAnimationValue](../../mfc/reference/canimationvalue-class.md)  
  
## Anforderungen  
 **Header:** afxanimationcontroller.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)