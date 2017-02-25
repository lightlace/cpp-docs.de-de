---
title: "CD2DRectU-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DRectU"
  - "afxrendertarget/CD2DRectU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DRectU-Klasse"
ms.assetid: a62f17d1-011d-4867-8f51-fd7e7c00561d
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DRectU-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für `D2D1_RECT_U`.  
  
## Syntax  
  
```  
class CD2DRectU : public D2D1_RECT_U;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectU::CD2DRectU](../Topic/CD2DRectU::CD2DRectU.md)|Überladen.  Erstellt ein Objekt aus `CD2DRectU``D2D1_RECT_U`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectU::IsNull](../Topic/CD2DRectU::IsNull.md)|Gibt einen `boolean`\-Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten \(`null`\) enthält.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DRectU::operator CRect](../Topic/CD2DRectU::operator%20CRect.md)|Wird `CD2DRectU` zu `CRect`\-Objekt.|  
  
## Vererbungshierarchie  
 `D2D1_RECT_U`  
  
 [CD2DRectU](../../mfc/reference/cd2drectu-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)