---
title: "COleCurrency Class"
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
  - "CURRENCY"
  - "COleCurrency"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleCurrency class"
  - "CURRENCY"
  - "fixed-point numbers"
  - "Zahlen, fixed-point"
ms.assetid: 3a36e345-303f-46fb-a57c-858274378a8d
caps.latest.revision: 24
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# COleCurrency Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Kapselt den `CURRENCY` Datentyp der OLE\-Automatisierung.  
  
## Syntax  
  
```  
class COleCurrency  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[COleCurrency::COleCurrency](../Topic/COleCurrency::COleCurrency.md)|Erstellt ein `COleCurrency`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[COleCurrency::Format](../Topic/COleCurrency::Format.md)|Generiert eine formatierte Zeichenfolgendarstellung eines Objekts `COleCurrency`.|  
|[COleCurrency::GetStatus](../Topic/COleCurrency::GetStatus.md)|Ruft den Status \(Gültigkeit\) dieses `COleCurrency`\-Objekts ab.|  
|[COleCurrency::ParseCurrency](../Topic/COleCurrency::ParseCurrency.md)|Liest einen **CURRENCY**\-Wert einer Zeichenfolge und legt den Wert von `COleCurrency` fest.|  
|[COleCurrency::SetCurrency](../Topic/COleCurrency::SetCurrency.md)|Legt den Wert dieses `COleCurrency`\-Objekts fest.|  
|[COleCurrency::SetStatus](../Topic/COleCurrency::SetStatus.md)|Legt den Status \(Gültigkeit\) für dieses `COleCurrency`\-Objekt fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[Operator \=](../Topic/COleCurrency::operator%20=.md)|Kopiert einen `COleCurrency`\-Wert.|  
|[Operatoren \+, \-](../Topic/COleCurrency::operator%20+,%20-.md)|Fügt subtrahiert, und Änderungszeichen von `COleCurrency`\-Werten.|  
|[Operator \+\=, \- \=](../Topic/COleCurrency::operator%20+=,%20-=.md)|Fügt und subtrahiert `COleCurrency` einen Wert von diesem `COleCurrency`\-Objekt.|  
|[Operator \*,\/](../Topic/COleCurrency::operator%20*,%20-.md)|Skaliert einen `COleCurrency`\-Wert durch einen ganzzahligen Wert.|  
|[Operator \*\=,\/\=](../Topic/COleCurrency::operator%20*=,%20-=.md)|Skaliert diesen `COleCurrency`\-Wert durch einen ganzzahligen Wert.|  
|[Operator \<\<](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|Gibt einen Wert `COleCurrency` zu `CArchive` oder zu `CDumpContext` aus.|  
|[Operator \>\>](../Topic/COleCurrency::operator%20%3C%3C,%20%3E%3E.md)|Gibt ein Objekt aus `COleCurrency``CArchive` ein.|  
|[Operator WÄHRUNG](../Topic/COleCurrency::operator%20CURRENCY.md)|Konvertiert einen Wert in `COleCurrency`**CURRENCY**.|  
|[Operator \=\=, \<, \<\=, usw..](../Topic/COleCurrency%20Relational%20Operators.md)|Vergleicht zwei Werte `COleCurrency`.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[COleCurrency::m\_cur](../Topic/COleCurrency::m_cur.md)|Enthält zugrunde liegende **CURRENCY**`COleCurrency` für dieses Objekt.|  
|[COleCurrency::m\_status](../Topic/COleCurrency::m_status.md)|Enthält den Status dieses `COleCurrency`\-Objekts.|  
  
## Hinweise  
 **COleCurrency** hat keine Basisklasse.  
  
 **CURRENCY** wird als 8\-Byte, Two'sergänzung ganzzahliger Wert implementiert, der von 10.000 skaliert wird.  Dies gibt eine Festkommazahl mit 15 Ziffern links vom Dezimaltrennzeichen und 4 Ziffern rechts.  Der **CURRENCY** Datentyp ist für die Berechnungen sehr nützlich, die Kosten einbeziehen, oder für jede Festpunktrechnung, in der Genauigkeit wichtig ist.  Es ist einer der möglichen Typen für den `VARIANT` Datentyp der OLE\-Automatisierung.  
  
 **COleCurrency** implementiert auch einige grundlegende arithmetische Operationen für diesen Festkommatyp.  Die unterstützten Vorgänge ausgewählt wurden, um die Rundungsfehler zu steuern, die während der Festpunktrechnungen auftreten.  
  
## Vererbungshierarchie  
 `COleCurrency`  
  
## Anforderungen  
 **Header:**  afxdisp.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)