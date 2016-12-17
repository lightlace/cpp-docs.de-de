---
title: "CD2DResource-Klasse"
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
  - "afxrendertarget/CD2DResource"
  - "CD2DResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DResource-Klasse"
ms.assetid: 34e3ee18-aab6-4c39-9294-de869e1f7820
caps.latest.revision: 18
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DResource-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine abstrakte Klasse, die eine Schnittstelle zum Erstellen und Verwalten von D2D\-Ressourcen \(wie Pinsel, Ebenen und Texte\) bereitstellt.  
  
## Syntax  
  
```  
class CD2DResource : public CObject;  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DResource::CD2DResource](../Topic/CD2DResource::CD2DResource.md)|Erstellt ein CD2DResource\-Objekt.|  
|[CD2DResource::~CD2DResource](../Topic/CD2DResource::~CD2DResource.md)|Der Destruktor.  Aufgerufen, wenn ein D2D\-Ressourcenobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DResource::Create](../Topic/CD2DResource::Create.md)|Erstellt ein CD2DResource.|  
|[CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md)|Zerstört ein CD2DResource\-Objekt.|  
|[CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md)|Überprüft Ressourcengültigkeit|  
  
### Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DResource::IsAutoDestroy](../Topic/CD2DResource::IsAutoDestroy.md)|Überprüfungsflag der automatischen zerstörung.|  
|[CD2DResource::ReCreate](../Topic/CD2DResource::ReCreate.md)|Erstellt ein CD2DResource neu.|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DResource::m\_bIsAutoDestroy](../Topic/CD2DResource::m_bIsAutoDestroy.md)|Ressource destoyed vom Besitzer \(CRenderTarget\)|  
|[CD2DResource::m\_pParentTarget](../Topic/CD2DResource::m_pParentTarget.md)|Zeiger auf den Elementen CRenderTarget\)|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)