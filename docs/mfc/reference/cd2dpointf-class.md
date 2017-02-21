---
title: "CD2DPointF-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DPointF"
  - "CD2DPointF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DPointF-Klasse"
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DPointF-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für `D2D1_POINT_2F`.  
  
## Syntax  
  
```  
class CD2DPointF : public D2D1_POINT_2F;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DPointF::CD2DPointF](../Topic/CD2DPointF::CD2DPointF.md)|Überladen.  Erstellt ein `CD2DPointF`\-Objekt aus `D2D1_POINT_2F`\-Objekt.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DPointF::operator CPoint](../Topic/CD2DPointF::operator%20CPoint.md)|Konvertiert `CD2DPointF` zu `CPoint`\-Objekt.|  
  
## Vererbungshierarchie  
 `D2D1_POINT_2F`  
  
 [CD2DPointF](../../mfc/reference/cd2dpointf-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)