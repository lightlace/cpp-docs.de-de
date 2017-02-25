---
title: "CW2WEX-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CW2WEX"
  - "ATL.CW2WEX<t_nBufferLength>"
  - "ATL::CW2WEX"
  - "ATL.CW2WEX"
  - "ATL::CW2WEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2WEX-Klasse"
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CW2WEX-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird durch Makros für Zeichenfolgenkonvertierung `CW2TEX` und `CT2WEX` und Typedef `CW2W` verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2WEX  
```  
  
#### Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers verwendet im Übersetzungsprozess.  Die Standardlänge ist 128 Bytes.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](../Topic/CW2WEX::CW2WEX.md)|Der \-Konstruktor.|  
|[CW2WEX::~CW2WEX](../Topic/CW2WEX::~CW2WEX.md)|Der Destruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](../Topic/CW2WEX::operator%20LPWSTR.md)|Konvertierungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CW2WEX::m\_psz](../Topic/CW2WEX::m_psz.md)|Der Datenmember, der die Quellzeichenfolge speichert.|  
|[CW2WEX::m\_szBuffer](../Topic/CW2WEX::m_szBuffer.md)|Der statische Puffer, verwendet die konvertierte Zeichenfolge speichern.|  
  
## Hinweise  
 Es sei denn, zusätzlich, sind Funktionen erforderlich, verwendet `CW2TEX`, `CT2WEX` oder `CW2W` im Code.  
  
 Diese Klasse enthält einen statischen Puffer fester Größe, der verwendet wird, um das Ergebnis der Konvertierung zu speichern.  Wenn das Ergebnis zu groß ist, in den statischen Puffer passt, belegt die Klasse mithilfe `malloc` Speicher und gibt den Arbeitsspeicher frei, wenn das Objekt den Gültigkeitsbereich verlässt.  Dadurch wird sichergestellt, dass, anders als die Textkonvertierungsmakros, die in früheren Versionen von ATL verfügbar sind, diese Klasse sicher, in Schleifen zu verwenden ist und nicht der Stapel überschritten.  
  
 Wenn die Klasse versucht, auf dem Heap Speicher reserviert und fehlschlägt, ruft sie `AtlThrow` mit einem Argument von **E\_OUTOFMEMORY** auf.  
  
 Standardmäßig verwenden die ATL\-Konvertierungsklassen und Makros die aktuelle ANSI\-Codepage des Threads für die Konvertierung.  
  
 Die folgenden Makros sind auf dieser Klasse:  
  
-   `CW2TEX`  
  
-   `CT2WEX`  
  
 Nachfolgende Typedef ist auf dieser Klasse:  
  
-   `CW2W`  
  
 Eine Erläuterung dieser Textkonvertierungsmakros, finden Sie unter [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Beispiel  
 Siehe [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) als ein Beispiel für die Verwendung dieser Makros für Zeichenfolgenkonvertierung.  
  
## Anforderungen  
 **Header:** atlconv.h  
  
## Siehe auch  
 [CA2AEX\-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX\-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX\-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2AEX\-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX\-Klasse](../../atl/reference/cw2cwex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)