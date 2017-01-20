---
title: "CD2DLayer-Klasse"
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
  - "afxrendertarget/CD2DLayer"
  - "CD2DLayer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DLayer-Klasse"
ms.assetid: 2f96378e-66bb-40d1-9661-6afe324de3c1
caps.latest.revision: 18
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DLayer-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1Layer".  
  
## Syntax  
  
```  
class CD2DLayer : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DLayer::CD2DLayer](../Topic/CD2DLayer::CD2DLayer.md)|Erstellt ein CD2DLayer\-Objekt.|  
|[CD2DLayer::~CD2DLayer](../Topic/CD2DLayer::~CD2DLayer.md)|Der Destruktor.  Aufgerufen, wenn ein D2D\-Ebenenobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DLayer::Attach](../Topic/CD2DLayer::Attach.md)|Fügt vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DLayer::Create](../Topic/CD2DLayer::Create.md)|Erstellt ein CD2DLayer.  \(Überschreibungen [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DLayer::Destroy](../Topic/CD2DLayer::Destroy.md)|Zerstört ein CD2DLayer\-Objekt.  \(Überschreibungen [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DLayer::Detach](../Topic/CD2DLayer::Detach.md)|Trennt Ressourcenschnittstelle vom Objekt|  
|[CD2DLayer::Get](../Topic/CD2DLayer::Get.md)|Schnittstelle der EINGABETASTE ID2D1Layer|  
|[CD2DLayer::GetSize](../Topic/CD2DLayer::GetSize.md)|Gibt die Größe des Renderingziels in den geräteunabhängige Pixel zurück|  
|[CD2DLayer::IsValid](../Topic/CD2DLayer::IsValid.md)|Überprüfungsressourcengültigkeit \(Überschreibungen [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DLayer::operator ID2D1Layer\*](../Topic/CD2DLayer::operator%20ID2D1Layer*.md)|Schnittstelle der EINGABETASTE ID2D1Layer|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DLayer::m\_pLayer](../Topic/CD2DLayer::m_pLayer.md)|Speichert einen Zeiger auf einen ID2D1Layer\-Objekt.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DLayer](../../mfc/reference/cd2dlayer-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)