---
title: "CD2DSizeU-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DSizeU"
  - "afxrendertarget/CD2DSizeU"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DSizeU-Klasse"
ms.assetid: 6e679ba8-2112-43c3-8275-70b660856f02
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DSizeU-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "D2D1\_SIZE\_U".  
  
## Syntax  
  
```  
class CD2DSizeU : public D2D1_SIZE_U;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DSizeU::CD2DSizeU](../Topic/CD2DSizeU::CD2DSizeU.md)|Überladen.  Erstellt ein Objekt aus `CD2DSizeU``D2D1_SIZE_U`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DSizeU::IsNull](../Topic/CD2DSizeU::IsNull.md)|Gibt einen `boolean`\-Wert zurück, der angibt, ob ein Ausdruck keine gültigen Daten \(`null`\) enthält.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DSizeU::operator CSize](../Topic/CD2DSizeU::operator%20CSize.md)|Wird `CD2DSizeU` zu `CSize`\-Objekt.|  
  
## Vererbungshierarchie  
 `D2D1_SIZE_U`  
  
 [CD2DSizeU](../../mfc/reference/cd2dsizeu-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)