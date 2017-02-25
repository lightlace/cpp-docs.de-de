---
title: "CD2DRectF-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DRectF"
  - "CD2DRectF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectF-Klasse"
ms.assetid: 87c12d87-9d18-4a19-ba14-0f51d6b6835a
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DRectF-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für `D2D1_RECT_F`.  
  
## Syntax  
  
```  
class CD2DRectF : public D2D1_RECT_F;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectF::CD2DRectF](../Topic/CD2DRectF::CD2DRectF.md)|Überladen.  Erstellt ein Objekt aus `CD2DRectF``D2D1_RECT_F`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectF::IsNull](../Topic/CD2DRectF::IsNull.md)|Gibt einen `boolean`\-Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten \(`null`\) enthält.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectF::operator CRect](../Topic/CD2DRectF::operator%20CRect.md)|Wird `CD2DRectF` zu `CRect`\-Objekt.|  
  
## Vererbungshierarchie  
 `D2D1_RECT_F`  
  
 [CD2DRectF](../../mfc/reference/cd2drectf-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)