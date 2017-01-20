---
title: "extent-Klasse (C++ AMP)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::extent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Extent-Struktur"
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# extent-Klasse (C++ AMP)
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Vektor von *N* ganzzahligen Werten dar, die die Grenzen eines *N*\-dimensionalen Raums mit dem Ursprung 0 angeben.  Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert.  
  
## Syntax  
  
```  
template <  
   int _Rank>  
class extent;  
```  
  
#### Parameter  
 `_Rank`  
 Der Rang des `extent`\-Objekts.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[extent::extent\-Konstruktor](../Topic/extent::extent%20Constructor.md)|Initialisiert eine neue Instanz der `extent`\-Klasse.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[extent::contains\-Methode](../Topic/extent::contains%20Method.md)|Überprüft, ob das angegebene `extent`\-Objekt über den angegebenen Rang verfügt.|  
|[extent::size\-Methode](../Topic/extent::size%20Method.md)|Gibt die lineare Gesamtgröße des Wertebereichs zurück \(in der Einheit Elemente\).|  
|[extent::tile\-Methode](../Topic/extent::tile%20Method.md)|Erzeugt ein `tiled_extent`\-Objekt mit den Kachelwertebereichen, die durch angegebene Dimensionen festgelegt werden.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[extent::operator\-\-Operator](../Topic/extent::operator-%20Operator.md)|Gibt ein neues `extent`\-Objekt zurück, das erstellt wird, indem die `index`\-Elemente von den entsprechenden `extent`\-Elementen subtrahiert werden.|  
|[extent::operator\-\-\-Operator](../Topic/extent::operator--%20Operator.md)|Dekrementiert jedes Element des `extent`\-Objekts.|  
|[extent::operator\(mod\)\=\-Operator](../Topic/extent::operator\(mod\)=%20Operator.md)|Berechnet den Modul \(Rest\) jedes Elements im `extent`\-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|  
|[extent::operator\*\=\-Operator](../Topic/extent::operator*=%20Operator.md)|Multipliziert jedes Element des `extent`\-Objekts mit einer Zahl.|  
|[extent::operator\/\=\-Operator](../Topic/extent::operator-=%20Operator1.md)|Dividiert jedes Element des `extent`\-Objekts durch eine Zahl.|  
|[extent::operatorOperator](../Topic/extent::operatorOperator.md)|Gibt das Element am angegebenen Index zurück.|  
|[extent::operator\+\-Operator](../Topic/extent::operator+%20Operator.md)|Gibt ein neues `extent`\-Objekt zurück, das durch Hinzufügen der entsprechenden `index`\- und `extent`\-Elemente erstellt wird.|  
|[extent::operator\+\+\-Operator](../Topic/extent::operator++%20Operator.md)|Inkrementiert jedes Element des `extent`\-Objekts.|  
|[extent::operator\+\=\-Operator](../Topic/extent::operator+=%20Operator.md)|Fügt die angegebene Zahl jedem Element des `extent`\-Objekts hinzu.|  
|[extent::operator\=\-Operator](../Topic/extent::operator=%20Operator.md)|Kopiert den Inhalt eines anderen `extent`\-Objekts in dieses Objekt.|  
|[extent::operator\-\=\-Operator](../Topic/extent::operator-=%20Operator2.md)|Subtrahiert die angegebene Anzahl von jedem Element des `extent`\-Objekts.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[extent::rank\-Konstante](../Topic/extent::rank%20Constant.md)|Ruft den Rang des `extent`\-Objekts ab.|  
  
## Vererbungshierarchie  
 `extent`  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)