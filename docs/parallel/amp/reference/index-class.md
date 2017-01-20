---
title: "index-Klasse"
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
  - "amp/Concurrency::index"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Indexstruktur"
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
caps.handback.revision: "15"
ms.author: "mblome"
manager: "ghogen"
---
# index-Klasse
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Definiert einen *N*\-dimensionalen Indexpunkt.  
  
## Syntax  
  
```  
template <  
   int _Rank  
>  
class index;  
```  
  
#### Parameter  
 `_Rank`  
 Der Rang oder die Anzahl von Dimensionen.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[index::index\-Konstruktor](../Topic/index::index%20Constructor.md)|Initialisiert eine neue Instanz der `index`\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[index::operator\-\-\-Operator](../Topic/index::operator--%20Operator.md)|Dekrementiert jedes Element des `index`\-Objekts.|  
|[index::operator\(mod\)\=\-Operator](../Topic/index::operator\(mod\)=%20Operator.md)|Berechnet den Modul \(Rest\) jedes Elements im `index`\-Objekt, wenn dieses Element durch eine Zahl dividiert wird.|  
|[index::operator\*\=\-Operator](../Topic/index::operator*=%20Operator.md)|Multipliziert jedes Element des `index`\-Objekts mit einer Zahl.|  
|[index::operator\/\=\-Operator](../Topic/index::operator-=%20Operator2.md)|Dividiert jedes Element des `index`\-Objekts durch eine Zahl.|  
|[index::operatorOperator](../Topic/index::operatorOperator.md)|Gibt das Element am angegebenen Index zurück.|  
|[index::operator\+\+\-Operator](../Topic/index::operator++%20Operator.md)|Inkrementiert jedes Element des `index`\-Objekts.|  
|[index::operator\+\=\-Operator](../Topic/index::operator+=%20Operator.md)|Fügt die angegebene Zahl jedem Element des `index`\-Objekts hinzu.|  
|[index::operator\=\-Operator](../Topic/index::operator=%20Operator.md)|Kopiert den Inhalt des angegebenen `index`\-Objekts in dieses Objekt.|  
|[index::operator\-\=\-Operator](../Topic/index::operator-=%20Operator1.md)|Subtrahiert die angegebene Anzahl von jedem Element des `index`\-Objekts.|  
  
### Öffentliche Konstanten  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[index::rank\-Konstante](../Topic/index::rank%20Constant.md)|Speichert den Rang des `index`\-Objekts.|  
  
## Vererbungshierarchie  
 `index`  
  
## Hinweise  
 Die `index`\-Struktur stellt einen Koordinatenvektor von *N* ganzen Zahlen dar, der eine eindeutige Position in einem *N*\-dimensionalen Raum angibt.  Die Werte im Vektor sind vom wichtigsten zum am wenigsten wichtigen Wert sortiert.  Sie können die Werte der Komponenten mit [index::operator\=\-Operator](../Topic/index::operator=%20Operator.md) abrufen.  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)