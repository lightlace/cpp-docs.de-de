---
title: "CStringData Class"
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
  - "CStringData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStringData class"
  - "shared classes, CStringData"
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
caps.latest.revision: 16
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CStringData Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt die Daten eines Zeichenfolgenobjekts dar.  
  
## Syntax  
  
```  
  
struct CStringData  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[AddRef](../Topic/CStringData::AddRef.md)|Inkrementiert den Verweiszähler des Zeichenfolgendatenobjekts.|  
|[data](../Topic/CStringData::data.md)|Ruft die Textdaten eines Zeichenfolgenobjekts ab.|  
|[IsLocked](../Topic/CStringData::IsLocked.md)|Bestimmt, ob der Puffer des zugeordneten Zeichenfolgenobjekts gesperrt ist.|  
|[IsShared](../Topic/CStringData::IsShared.md)|Bestimmt, ob der Puffer des zugeordneten Zeichenfolgenobjekts nur freigegeben wird.|  
|[Sperren](../Topic/CStringData::Lock.md)|Sperrt den Puffer des zugeordneten Zeichenfolgenobjekts.|  
|[Release](../Topic/CStringData::Release.md)|Gibt das angegebene Zeichenfolgenobjekt frei.|  
|[Entsperren Sie](../Topic/CStringData::Unlock.md)|Setzt den Puffer des zugeordneten Zeichenfolgenobjekts frei.|  
  
### Datenmember  
  
|||  
|-|-|  
|[nAllocLength](../Topic/CStringData::nAllocLength.md)|Länge zugeordnete Daten in `XCHAR` s nicht \(einschließlich endgültige NULL\-Zeichen\)|  
|[nDataLength](../Topic/CStringData::nDataLength.md)|Länge derzeit verwendete Daten in `XCHAR` s nicht \(einschließlich endgültige NULL\-Zeichen\)|  
|[nRefs](../Topic/CStringData::nRefs.md)|Der aktuelle Verweiszählerwert des Objekts.|  
|[pStringMgr](../Topic/CStringData::pStringMgr.md)|Ein Zeiger auf Zeichenfolgenmanager dieses Zeichenfolgenobjekts.|  
  
## Hinweise  
 Diese Klasse sollte von Entwicklern nur verwendet werden, die benutzerdefinierte Zeichenfolgenmanager implementieren.  Weitere Informationen zu benutzerdefinierten Zeichenfolgenmanager, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 Diese Klasse kapselt verschiedene Typen von Informationen und Daten, die mit einem höheren Zeichenfolgenobjekt, wie [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md) oder [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)\-Objekten zugeordnet sind.  Jedes höhere Zeichenfolgenobjekt enthält einen Zeiger auf dem zugeordneten `CStringData`\-Objekt und ermöglicht mehrere Zeichenfolgenobjekte zum Punkt zum gleichen Zeichenfolgendatenobjekt.  Diese Beziehung wird in den Verweiszähler \(`nRefs`\) des `CStringData`\-Objekts dargestellt.  
  
> [!NOTE]
>  In bestimmten Fällen gibt ein Zeichenfolgentyp \(z **CFixedString**\) kein Zeichenfolgendatenobjekt mit mehr als einem höheren Zeichenfolgenobjekt frei.  Weitere Informationen über dieses, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
 Diese Daten werden von zusammengesetzt:  
  
-   Der Speicher\-Manager \(des Typs\) [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md) der Zeichenfolge.  
  
-   Die aktuelle Länge \([nDataLength](../Topic/CStringData::nDataLength.md)\) der Zeichenfolge.  
  
-   Die zugeordnete Länge \([nAllocLength](../Topic/CStringData::nAllocLength.md)\) der Zeichenfolge.  Aus Leistungsgründen kann sich jedoch von der aktuellen Zeichenfolgenlänge unterscheiden  
  
-   Der aktuelle Verweiszähler \([nRefs](../Topic/CStringData::nRefs.md)\) `CStringData` des Objekts.  Dieser Wert wird verwendet, wenn Sie bestimmt, wie viele Zeichenfolgenobjekte dasselbe Objekt `CStringData` freigeben.  
  
-   Der tatsächliche Zeichenpuffer \([Daten](../Topic/CStringData::data.md)\) der Zeichenfolge.  
  
    > [!NOTE]
    >  Der tatsächliche Zeichenpuffer des String\-Objekts wird vom Zeichenfolgenmanager zugeordnet und wird in `CStringData`\-Objekt angefügt.  
  
## Anforderungen  
 **Header:** atlsimpstr.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)