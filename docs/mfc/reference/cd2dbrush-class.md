---
title: "CD2DBrush-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CD2DBrush"
  - "afxrendertarget/CD2DBrush"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DBrush-Klasse"
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CD2DBrush-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1Brush".  
  
## Syntax  
  
```  
class CD2DBrush : public CD2DResource;  
```  
  
## Mitglieder  
  
### Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBrush::CD2DBrush](../Topic/CD2DBrush::CD2DBrush.md)|Erstellt ein CD2DBrush\-Objekt.|  
|[CD2DBrush::~CD2DBrush](../Topic/CD2DBrush::~CD2DBrush.md)|Der Destruktor.  Aufgerufen, wenn ein D2D\-Pinselobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBrush::Attach](../Topic/CD2DBrush::Attach.md)|Fügt vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DBrush::Destroy](../Topic/CD2DBrush::Destroy.md)|Zerstört ein CD2DBrush\-Objekt.  \(Überschreibungen [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DBrush::Detach](../Topic/CD2DBrush::Detach.md)|Trennt Ressourcenschnittstelle vom Objekt|  
|[CD2DBrush::Get](../Topic/CD2DBrush::Get.md)|Schnittstelle der EINGABETASTE ID2D1Brush|  
|[CD2DBrush::GetOpacity](../Topic/CD2DBrush::GetOpacity.md)|Ruft den Grad der Durchlässigkeit dieses Pinsels ab|  
|[CD2DBrush::GetTransform](../Topic/CD2DBrush::GetTransform.md)|Ruft den aktuellen transformieren vom Renderziel ab|  
|[CD2DBrush::IsValid](../Topic/CD2DBrush::IsValid.md)|Überprüfungsressourcengültigkeit \(Überschreibungen [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DBrush::SetOpacity](../Topic/CD2DBrush::SetOpacity.md)|Legt den Grad der Durchlässigkeit dieses Pinsels fest|  
|[CD2DBrush::SetTransform](../Topic/CD2DBrush::SetTransform.md)|Wendet den angegebenen transformieren zum Renderingziel und ersetzt die vorhandene Transformation.  Alle folgenden Zeichenvorgänge treten im umgewandelten Platz auf|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBrush::operator ID2D1Brush\*](../Topic/CD2DBrush::operator%20ID2D1Brush*.md)|Schnittstelle der EINGABETASTE ID2D1Brush|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DBrush::m\_pBrush](../Topic/CD2DBrush::m_pBrush.md)|Speichert einen Zeiger auf einen ID2D1Brush\-Objekt.|  
|[CD2DBrush::m\_pBrushProperties](../Topic/CD2DBrush::m_pBrushProperties.md)|Pinseleigenschaften.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DBrush](../../mfc/reference/cd2dbrush-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)