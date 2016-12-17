---
title: "Grenzwerte f&#252;r Gleitkommakonstanten"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FLOAT.H-Headerdatei"
  - "Gleitkommakonstanten, Einschränkungen"
  - "Gleitkommazahlen, Grenzwerte für Gleitkommakonstanten"
  - "Einschränkungen, Gleitkommakonstanten"
  - "Bereiche, Gleitkommakonstanten"
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Grenzwerte f&#252;r Gleitkommakonstanten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 In der folgenden Tabelle sind die Limits für die Werte von Gleitkommakonstanten aufgeführt.  Diese Limits werden auch in der Standardheaderdatei FLOAT.H definiert.  
  
### Grenzwerte für Gleitkommakonstanten  
  
|Konstante|Bedeutung|Wert|  
|---------------|---------------|----------|  
|FLT\_DIG DBL\_DIG LDBL\_DIG|Anzahl von Ziffern q, sodass eine Gleitkommazahl mit q Dezimalstellen ohne Genauigkeitsverlust auf eine Gleitkommadarstellung und zurück gerundet werden kann.|6 15 15|  
|FLT\_EPSILON DBL\_EPSILON LDBL\_EPSILON|Kleinste positive Zahl x, sodass x \+ 1,0 ungleich 1,0 ist.|1.192092896e–07F 2.2204460492503131e–016 2.2204460492503131e–016|  
|FLT\_GUARD||0|  
|FLT\_MANT\_DIG DBL\_MANT\_DIG LDBL\_MANT\_DIG|Anzahl von Ziffern in der Basis, die von FLT\_RADIX in der Gleitkomma\-Mantisse angegeben wird.  Die Basis ist 2. Daher werden mit diesen Werten Bits angegeben.|24 53 53|  
|FLT\_MAX DBL\_MAX LDBL\_MAX|Darstellbare Höchstgleitkommazahl.|3.402823466e\+38F 1.7976931348623158e\+308 1.7976931348623158e\+308|  
|FLT\_MAX\_10\_EXP DBL\_MAX\_10\_EXP LDBL\_MAX\_10\_EXP|Maximale ganze Zahl, sodass 10 erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|38 308 308|  
|FLT\_MAX\_EXP DBL\_MAX\_EXP LDBL\_MAX\_EXP|Maximale ganze Zahl, sodass FLT\_RADIX erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|128 1024 1024|  
|FLT\_MIN DBL\_MIN LDBL\_MIN|Minimaler positiver Wert.|1.175494351e–38F 2.2250738585072014e–308 2.2250738585072014e–308|  
|FLT\_MIN\_10\_EXP DBL\_MIN\_10\_EXP LDBL\_MIN\_10\_EXP|Minimale negative Ganzzahl, sodass 10 erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|–37<br /><br /> –307<br /><br /> –307|  
|FLT\_MIN\_EXP DBL\_MIN\_EXP LDBL\_MIN\_EXP|Minimale negative Ganzzahl, sodass FLT\_RADIX erhöht auf diese Zahl eine darstellbare Gleitkommazahl ist.|–125<br /><br /> –1021<br /><br /> –1021|  
|FLT\_NORMALIZE||0|  
|FLT\_RADIX \_DBL\_RADIX \_LDBL\_RADIX|Basis der Exponentendarstellung.|2 2 2|  
|FLT\_ROUNDS\-\_DBL\_ROUNDS \_LDBL\_ROUNDS|Rundungsverhalten für Gleitkommaaddition.|1 \(Nähe\) 1 \(Nähe\) 1 \(Nähe\)|  
  
> [!NOTE]
>  Die Informationen in der Tabelle können sich in zukünftigen Versionen des Produkts unterscheiden.  
  
## END Microsoft\-spezifisch  
  
## Siehe auch  
 [Ganzzahlige Grenzen](../cpp/integer-limits.md)