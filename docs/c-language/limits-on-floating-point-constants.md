---
title: "Grenzwerte f&#252;r Gleitkommakonstanten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Konstanten, Gleitkomma"
  - "FLOAT.H-Headerdatei"
  - "Gleitkommakonstanten, Einschränkungen"
  - "Gleitkommazahlen, Grenzwerte für Gleitkommakonstanten"
  - "Einschränkungen, Gleitkommakonstanten"
  - "Bereiche, Gleitkommakonstanten"
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Grenzwerte f&#252;r Gleitkommakonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 In der folgenden Tabelle sind die Beschränkungen für die Werte von Gleitkommakonstanten aufgeführt.  Die Headerdatei FLOAT.H enthält diese Informationen.  
  
### Grenzwerte für Gleitkommakonstanten  
  
|Konstante|Bedeutung|Wert|  
|---------------|---------------|----------|  
|**FLT\_DIGDBL\_DIGLDBL\_DIG**|Anzahl von Ziffern, *q*, sodass eine Gleitkommazahl mit *q* Dezimalstellen ohne Genauigkeitsverlust auf eine Gleitkommadarstellung und zurück gerundet werden kann.|6 15 15|  
|**FLT\_EPSILONDBL\_EPSILONLDBL\_EPSILON**|Kleinste positive Zahl *x*, sodass *x* \+ 1,0 ungleich 1,0 ist.|1.192092896e–07F 2.2204460492503131e–016 2.2204460492503131e–016|  
|**FLT\_GUARD**||0|  
|**FLT\_MANT\_DIGDBL\_MANT\_DIGLDBL\_MANT\_DIG**|Anzahl von Ziffern in der Basis, die von **FLT\_RADIX** im Gleitkommasignifikanden angegeben wird.  Die Basis ist 2, daher werden mit diesen Werten Bits angegeben.|24 53 53|  
|**FLT\_MAXDBL\_MAXLDBL\_MAX**|Darstellbare Höchstgleitkommazahl.|3.402823466e\+38F 1.7976931348623158e\+308 1.7976931348623158e\+308|  
|**FLT\_MAX\_10\_EXPDBL\_MAX\_10\_EXPLDBL\_MAX\_10\_EXP**|Maximale ganze Zahl, sodass 10 erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|38 308 308|  
|**FLT\_MAX\_EXPDBL\_MAX\_EXPLDBL\_MAX\_EXP**|Maximale ganze Zahl, sodass **FLT\_RADIX** erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|128 1024 1024|  
|**FLT\_MINDBL\_MINLDBL\_MIN**|Minimaler positiver Wert.|1.175494351e–38F 2.2250738585072014e–308 2.2250738585072014e–308|  
|**FLT\_MIN\_10\_EXPDBL\_MIN\_10\_EXPLDBL\_MIN\_10\_EXP**|Minimale negative Ganzzahl, sodass 10 erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|–37<br /><br /> –307<br /><br /> –307|  
|**FLT\_MIN\_EXPDBL\_MIN\_EXPLDBL\_MIN\_EXP**|Minimale negative Ganzzahl, sodass **FLT\_RADIX** erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|–125<br /><br /> –1021<br /><br /> –1021|  
|**FLT\_NORMALIZE**||0|  
|**FLT\_RADIX\_DBL\_RADIX\_LDBL\_RADIX**|Basis der Exponentendarstellung.|2 2 2|  
|**FLT\_ROUNDS\_DBL\_ROUNDS\_LDBL\_ROUNDS**|Rundungsverhalten für Gleitkommaaddition.|1 \(Nähe\) 1 \(Nähe\) 1 \(Nähe\)|  
  
 Beachten Sie, dass sich die Informationen in der obigen Tabelle in zukünftige Implementierungen möglicherweise unterscheiden.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [C\-Gleitkommakonstanten](../c-language/c-floating-point-constants.md)