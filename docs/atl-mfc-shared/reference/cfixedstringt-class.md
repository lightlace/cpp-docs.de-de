---
title: "CFixedStringT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFixedStringT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFixedStringT class"
  - "shared classes, CFixedStringT"
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CFixedStringT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt ein Zeichenfolgenobjekt mit einem festen Zeichenpuffer dar.  
  
## Syntax  
  
```  
  
      template< class   
      StringType  
      , int   
      t_nChars  
       >    
class CFixedStringT : private CFixedStringMgr, public StringType  
```  
  
#### Parameter  
 `StringType`  
 Wenn die Basisklasse für das fixed\-Schlüsselwort Zeichenfolgenobjekt und sein verwendet kann entweder er\-basiert Typ `CStringT`.  Einige Beispiele sind `CString`, `CStringA` und `CStringW`.  
  
 *t\_nChars*  
 Die Anzahl der Zeichen im Puffer gespeichert.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFixedStringT::CFixedStringT](../Topic/CFixedStringT::CFixedStringT.md)|Der Konstruktor für das Zeichenfolgenobjekt.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CFixedStringT::operator \=](../Topic/CFixedStringT::operator%20=.md)|Weist einen neuen Wert zu einem `CFixedStringT`\-Objekt zu.|  
  
## Hinweise  
 Diese Klasse ist ein Beispiel einer benutzerdefinierten Zeichenfolgenklasse auf Grundlage `CStringT`.  Obwohl vergleichbar, unterscheiden sich die zwei Klassen in der Implementierung.  Die Hauptunterschiede zwischen `CFixedStringT` und `CStringT` sind:  
  
-   Der Puffer des ersten Zeichens wird als Teil des Objekts zugeordnet und Größe *t\_nChars* verfügt.  Dies ermöglicht dem **CFixedString**\-Objekt, um einen zusammenhängenden Arbeitsspeicherblock zu aus Gründen der Leistung gelegentlich einnimmt.  Wenn der Inhalt eines `CFixedStringT`\-Objekts über *t\_nChars hinaus* vergrößert, wird der Puffer dynamisch zugeordnet.  
  
-   Der Zeichenpuffer für ein `CFixedStringT`\-Objekt ist immer die gleiche Länge \(*t\_nChars*\).  Es gibt keine Einschränkung auf Puffergröße für `CStringT`\-Objekte.  
  
-   Der Speicher\-Manager für `CFixedStringT` wird so angepasst, dass [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) Verwerfen eines Objekts zwischen zwei oder mehr `CFixedStringT` objectsis nicht zulässig.  `CStringT`\-Objekte haben diese Einschränkung nicht.  
  
 Weitere Informationen über die Anpassung von `CFixedStringT` und Speicherverwaltung für Zeichenfolgenobjekte im Allgemeinen, finden Sie unter [Speicherverwaltung und CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## Vererbungshierarchie  
 `IAtlStringMgr`  
  
 `StringType`  
  
 `CFixedStringMgr`  
  
 `CFixedStringT`  
  
## Anforderungen  
 **Header:** cstringt.h  
  
## Siehe auch  
 [CStringT Class](../../atl-mfc-shared/reference/cstringt-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)