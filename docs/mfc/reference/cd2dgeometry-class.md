---
title: "CD2DGeometry-Klasse"
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
  - "CD2DGeometry"
  - "afxrendertarget/CD2DGeometry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DGeometry-Klasse"
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DGeometry-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1Geometry".  
  
## Syntax  
  
```  
class CD2DGeometry : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometry::CD2DGeometry](../Topic/CD2DGeometry::CD2DGeometry.md)|Erstellt ein CD2DGeometry\-Objekt.|  
|[CD2DGeometry::~CD2DGeometry](../Topic/CD2DGeometry::~CD2DGeometry.md)|Der Destruktor.  Wird aufgerufen, wenn ein D2D\-Geometrieobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometry::Attach](../Topic/CD2DGeometry::Attach.md)|Hängt die vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DGeometry::CombineWithGeometry](../Topic/CD2DGeometry::CombineWithGeometry.md)|Kombiniert diese Geometrie mit der angegebenen Geometrie und speichert das Ergebnis in einer ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::CompareWithGeometry](../Topic/CD2DGeometry::CompareWithGeometry.md)|Beschreibt die Schnittmenge zwischen dieser Geometrie und der angegebenen Geometrie.  Der Vergleich wird mit der angegebenen vereinfachenden Toleranz ausgeführt.|  
|[CD2DGeometry::ComputeArea](../Topic/CD2DGeometry::ComputeArea.md)|Berechnet den Bereich der Geometrie, nachdem sie von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht wurde.|  
|[CD2DGeometry::ComputeLength](../Topic/CD2DGeometry::ComputeLength.md)|Berechnet die Länge der Geometrie, als ob jedes Segment in eine Linie abgerollt wurde.|  
|[CD2DGeometry::ComputePointAtLength](../Topic/CD2DGeometry::ComputePointAtLength.md)|Berechnet den Punkt und Tangensvektor bei der angegebenen Entfernung entlang der Geometrie, nachdem sie von der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht wurde.|  
|[CD2DGeometry::Destroy](../Topic/CD2DGeometry::Destroy.md)|Zerstört ein CD2DGeometry\-Objekt.  \(Überschreibt [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DGeometry::Detach](../Topic/CD2DGeometry::Detach.md)|Trennt die Ressourcenschnittstelle vom Objekt|  
|[CD2DGeometry::FillContainsPoint](../Topic/CD2DGeometry::FillContainsPoint.md)|Gibt an, ob der von der Geometrie ausgefüllte Bereich mit der angegebenen Vereinfachungstoleranz den angegebenen Punkt enthalten würde.|  
|[CD2DGeometry::Get](../Topic/CD2DGeometry::Get.md)|Gibt die ID2D1Geometry\-Schnittstelle zurück|  
|[CD2DGeometry::GetBounds](../Topic/CD2DGeometry::GetBounds.md)||  
|[CD2DGeometry::GetWidenedBounds](../Topic/CD2DGeometry::GetWidenedBounds.md)|Ruft die Grenzen der Geometrie ab, nachdem sie mit der angegebenen Strichbreite und dem angegebenen Stil erweitert und anhand der angegebenen Matrix transformiert wurde.|  
|[CD2DGeometry::IsValid](../Topic/CD2DGeometry::IsValid.md)|Überprüft die Ressourcengültigkeit \(Überschreibt [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DGeometry::Outline](../Topic/CD2DGeometry::Outline.md)|Berechnet die Konturen der Geometrie und schreibt das Ergebnis in einen ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::Simplify](../Topic/CD2DGeometry::Simplify.md)|Erstellt eine vereinfachte Version der Geometrie, die nur Linien und \(optional\) kubische Bézierkurven enthält, und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink.|  
|[CD2DGeometry::StrokeContainsPoint](../Topic/CD2DGeometry::StrokeContainsPoint.md)|Bestimmt, ob der Strich der Geometrie den angegebenen Punkt enthält, bei angegebener Strichstärke, Format und Transformation.|  
|[CD2DGeometry::Tessellate](../Topic/CD2DGeometry::Tessellate.md)|Erstellt einen Satz von im Uhrzeigersinn gedrehten Dreiecken, die die Geometrie bedecken, nachdem sie mit der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht wurde.|  
|[CD2DGeometry::Widen](../Topic/CD2DGeometry::Widen.md)|Erweitert die Geometrie um den angegebenen Strich und schreibt das Ergebnis in eine ID2D1SimplifiedGeometrySink, nachdem es mit der angegebenen Matrix transformiert und mit der angegebenen Toleranz vereinfacht wurde.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometry::operator ID2D1Geometry\*](../Topic/CD2DGeometry::operator%20ID2D1Geometry*.md)|Gibt die ID2D1Geometry\-Schnittstelle zurück|  
  
### Geschützte Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CD2DGeometry::m\_pGeometry](../Topic/CD2DGeometry::m_pGeometry.md)|Ein Zeiger auf eine ID2D1Geometry.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)  
  
## Anforderungen  
 **Header:** afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)