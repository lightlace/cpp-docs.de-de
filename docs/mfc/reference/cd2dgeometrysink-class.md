---
title: "CD2DGeometrySink-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "afxrendertarget/CD2DGeometrySink"
  - "CD2DGeometrySink"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometrySink-Klasse"
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CD2DGeometrySink-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1GeometrySink".  
  
## Syntax  
  
```  
class CD2DGeometrySink;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometrySink::CD2DGeometrySink](../Topic/CD2DGeometrySink::CD2DGeometrySink.md)|Erstellt ein CD2DGeometrySink\-Objekt aus CD2DPathGeometry\-Objekt.|  
|[CD2DGeometrySink::~CD2DGeometrySink](../Topic/CD2DGeometrySink::~CD2DGeometrySink.md)|Der Destruktor.  Wird aufgerufen, wenn ein D2D\-Geometriesenkenobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometrySink::AddArc](../Topic/CD2DGeometrySink::AddArc.md)|Fügt der Pfadgeometrie einen einzelnen Bogen hinzu|  
|[CD2DGeometrySink::AddBezier](../Topic/CD2DGeometrySink::AddBezier.md)|Erstellt eine kubische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddBeziers](../Topic/CD2DGeometrySink::AddBeziers.md)|Erstellt eine Sequenz kubischer Bézierkurven und fügt sie der Geometriesenke hinzu.|  
|[CD2DGeometrySink::AddLine](../Topic/CD2DGeometrySink::AddLine.md)|Erstellt zwischen dem aktuellen Punkt und dem angegebenen Endpunkt ein Liniensegment und fügt es der Geometriesenke hinzu.|  
|[CD2DGeometrySink::AddLines](../Topic/CD2DGeometrySink::AddLines.md)|Erstellt mit den angegebenen Punkten eine Sequenz von Linien und fügt sie der Geometriesenke hinzu.|  
|[CD2DGeometrySink::AddQuadraticBezier](../Topic/CD2DGeometrySink::AddQuadraticBezier.md)|Erstellt eine quadratische Bézierkurve zwischen dem aktuellen Punkt und dem angegebenen Endpunkt.|  
|[CD2DGeometrySink::AddQuadraticBeziers](../Topic/CD2DGeometrySink::AddQuadraticBeziers.md)|Fügt eine Sequenz quadratischer Béziersegmente als Array in einem einzelnen Aufruf hinzu.|  
|[CD2DGeometrySink::BeginFigure](../Topic/CD2DGeometrySink::BeginFigure.md)|Startet am angegebenen Punkt eine neue Abbildung.|  
|[CD2DGeometrySink::Close](../Topic/CD2DGeometrySink::Close.md)|Schließt die Geometriesenke|  
|[CD2DGeometrySink::EndFigure](../Topic/CD2DGeometrySink::EndFigure.md)|Beendet die aktuelle Abbildung; schließt sie optional.|  
|[CD2DGeometrySink::Get](../Topic/CD2DGeometrySink::Get.md)|Gibt die ID2D1GeometrySink\-Schnittstelle zurück|  
|[CD2DGeometrySink::IsValid](../Topic/CD2DGeometrySink::IsValid.md)|Überprüft die Geometriesenkengültigkeit|  
|[CD2DGeometrySink::SetFillMode](../Topic/CD2DGeometrySink::SetFillMode.md)|Gibt die Methode an, die verwendet wurde, um zu bestimmen, welche Punkte innerhalb und außerhalb der von dieser Geometriesenke beschriebenen Geometrie liegen.|  
|[CD2DGeometrySink::SetSegmentFlags](../Topic/CD2DGeometrySink::SetSegmentFlags.md)|Gibt Strich\- und Joinoptionen an, die auf neue der Geometriesenke hinzugefügte Segmente angewendet werden sollen.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometrySink::operator ID2D1GeometrySink\*](../Topic/CD2DGeometrySink::operator%20ID2D1GeometrySink*.md)|Gibt die ID2D1GeometrySink\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometrySink::m\_pSink](../Topic/CD2DGeometrySink::m_pSink.md)|Ein Zeiger auf eine ID2D1GeometrySink.|  
  
## Vererbungshierarchie  
 [CD2DGeometrySink](../../mfc/reference/cd2dgeometrysink-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)