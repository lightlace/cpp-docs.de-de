---
title: "CD2DMesh-Klasse"
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
  - "afxrendertarget/CD2DMesh"
  - "CD2DMesh"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CD2DMesh-Klasse"
ms.assetid: 11a2c78a-1367-40e8-a34f-44aa0509a4c9
caps.latest.revision: 17
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# CD2DMesh-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein Wrapper für "ID2D1Mesh".  
  
## Syntax  
  
```  
class CD2DMesh : public CD2DResource;  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DMesh::CD2DMesh](../Topic/CD2DMesh::CD2DMesh.md)|Erstellt ein CD2DMesh\-Objekt.|  
|[CD2DMesh::~CD2DMesh](../Topic/CD2DMesh::~CD2DMesh.md)|Der Destruktor.  Aufgerufen, wenn ein D2D\-Gitterobjekt zerstört wird.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DMesh::Attach](../Topic/CD2DMesh::Attach.md)|Fügt vorhandene Ressourcenschnittstelle an das Objekt an|  
|[CD2DMesh::Create](../Topic/CD2DMesh::Create.md)|Erstellt ein CD2DMesh.  \(Überschreibungen [CD2DResource::Create](../Topic/CD2DResource::Create.md).\)|  
|[CD2DMesh::Destroy](../Topic/CD2DMesh::Destroy.md)|Zerstört ein CD2DMesh\-Objekt.  \(Überschreibungen [CD2DResource::Destroy](../Topic/CD2DResource::Destroy.md).\)|  
|[CD2DMesh::Detach](../Topic/CD2DMesh::Detach.md)|Trennt Ressourcenschnittstelle vom Objekt|  
|[CD2DMesh::Get](../Topic/CD2DMesh::Get.md)|Schnittstelle der EINGABETASTE ID2D1Mesh|  
|[CD2DMesh::IsValid](../Topic/CD2DMesh::IsValid.md)|Überprüfungsressourcengültigkeit \(Überschreibungen [CD2DResource::IsValid](../Topic/CD2DResource::IsValid.md).\)|  
|[CD2DMesh::Open](../Topic/CD2DMesh::Open.md)|Öffnet das Netz für Auffüllung.|  
  
### Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DMesh::operator ID2D1Mesh\*](../Topic/CD2DMesh::operator%20ID2D1Mesh*.md)|Schnittstelle der EINGABETASTE ID2D1Mesh|  
  
### Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CD2DMesh::m\_pMesh](../Topic/CD2DMesh::m_pMesh.md)|Ein Zeiger auf einen ID2D1Mesh.|  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CD2DResource](../../mfc/reference/cd2dresource-class.md)  
  
 [CD2DMesh](../../mfc/reference/cd2dmesh-class.md)  
  
## Anforderungen  
 **Header:**  afxrendertarget.h  
  
## Siehe auch  
 [Klassen](../../mfc/reference/mfc-classes.md)