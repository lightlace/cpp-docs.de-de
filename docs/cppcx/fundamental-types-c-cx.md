---
title: "Grundlegende Typen (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c9f82907-25f2-440b-91d6-afb8dbd46ea6
caps.latest.revision: 14
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 14
---
# Grundlegende Typen (C++/CX)
Zusätzlich zu den standardmäßig integrierten C\+\+\-Typen, unterstützt [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) das von der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Architektur definierte Typsystem, indem Typdefinitionen für die grundlegenden [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen bereitgestellt werden, die den C\+\+\-Standardtypen zugeordnet sind.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] implementiert boolesche, Zeichen\- und grundlegende numerische Typen. Dieser Typdefinitionen werden im `default`\-Namespace definiert, der nicht explizit angegeben werden muss. Darüber hinaus bietet [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] Wrapper und konkrete Implementierungen für bestimmte [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen und \-Schnittstellen.  
  
## Boolesche und Zeichentypen  
 Die folgende Tabelle enthält die integrierten booleschen und Zeichentypen sowie deren C\+\+\-Standardentsprechungen.  
  
|Namespace|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Name|Definition|C\+\+\-Standardname|Wertebereich|  
|---------------|------------------------------------------------------------------------|----------------|-------------------------|------------------|  
|Plattform|Boolesch|Ein 8\-Bit\-boolescher Wert.|bool|`true` \(ungleich null\) und `false` \(null\)|  
|default|char16|Ein nicht numerischer 16\-Bit\-Wert, der einen Unicode\-Codepunkt \(UTF\-16\) darstellt.|wchar\_t<br /><br /> \- oder \-<br /><br /> L'c'|\(Angegeben durch den Unicode\-Standard\)|  
  
## Numerische Typen  
 In der folgenden Tabelle sind die integrierten numerischen Typen aufgeführt. Die numerischen Typen sind im `default`\-Namespace deklariert und stellen Typdefinitionen für den entsprechenden integrierten C\+\+\-Typ dar. Nicht alle integrierten C\+\+\-Typen \(z. B. „long“\) werden in der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] unterstützt. Es wird hinsichtlich Konsistenz und Übersichtlichkeit empfohlen, dass Sie den [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Namen verwenden.  
  
|[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\-Name|Definition|C\+\+\-Standardname|Wertebereich|  
|------------------------------------------------------------------------|----------------|-------------------------|------------------|  
|int8|Eine numerischer 8\-Bit\-Wert mit Vorzeichen.|char mit Vorzeichen|–128 bis 127|  
|uint8|Eine numerischer 8\-Bit\-Wert ohne Vorzeichen.|unsigned char|0 bis 255|  
|int16|Eine 16\-Bit\-Ganzzahl mit Vorzeichen.|short|–32.768 bis 32.767|  
|uint16|Eine 16\-Bit\-Ganzzahl ohne Vorzeichen.|unsigned short|0 bis 65.535|  
|int32|Eine 32\-Bit\-Ganzzahl mit Vorzeichen.|int|–2.147.483.648 bis 2.147.483.647|  
|uint32|Eine 32\-Bit\-Ganzzahl ohne Vorzeichen.|unsigned int|0 bis 4.294.967.295|  
|int64|Eine 64\-Bit\-Ganzzahl mit Vorzeichen.|long long \- oder \- \_\_int64|–9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807|  
|uint64|Eine 64\-Bit\-Ganzzahl ohne Vorzeichen.|unsigned long long \- oder \- unsigned \_\_int64|0 bis 18.446.744.073.709.551.615|  
|float32|Eine 32\-Bit\-IEEE 754\-Gleitkommazahl.|float|3.4E \+\/\- 38 \(7 Stellen\)|  
|float64|Eine 64\-Bit\-IEEE 754\-Gleitkommazahl.|double|1.7E \+\/\- 308 \(15 Stellen\)|  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typen  
 Die folgende Tabelle enthält einige weitere Typen, die von der [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Architektur definiert werden und in [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] integriert sind. „Object“ und „String“ sind Referenztypen. Die anderen sind Werttypen. Alle diese Typen werden im `Platform`\-Namespace deklariert. Eine vollständige Liste finden Sie unter [Plattformnamespace](../cppcx/platform-namespace-c-cx.md).  
  
|Name|Definition|  
|----------|----------------|  
|Objekt|Stellt einen beliebigen [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]\-Typ dar.|  
|Zeichenfolge|Eine Reihe von Zeichen, die Text darstellen.|  
|Rect|Eine Gruppe von vier Gleitkommazahlen, die die Position und Größe eines Rechtecks angeben.|  
|SizeT|Ein geordnetes Paar von Gleitkommazahlen, die eine Höhe und Breite angeben.|  
|Punkt|Ein geordnetes Paar von Gleitkommazahlen für x\- und y\-Koordinaten, die einen Punkt in einer zweidimensionalen Ebene definieren.|  
|Guid|Ein nicht numerischer 128\-Bit\-Wert, der als eindeutiger Bezeichner verwendet wird.|  
|UIntPtr|\(Nur für interne Verwendung.\) Ein 64\-Bit\-Wert ohne Vorzeichen, der als Zeiger verwendet wird.|  
|IntPtr|\(Nur für interne Verwendung.\)  Ein 64\-Bit\-Wert mit Vorzeichen, der als Zeiger verwendet wird.|  
  
## Siehe auch  
 [Typsystem](../cppcx/type-system-c-cx.md)