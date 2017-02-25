---
title: "CA2WEX-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATLCONV/CA2WEX"
  - "ATL.CA2WEX"
  - "ATL.CA2WEX<t_nBufferLength>"
  - "ATL::CA2WEX"
  - "ATL::CA2WEX<t_nBufferLength>"
  - "CA2WEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CA2WEX-Klasse"
ms.assetid: 317d9ffb-e84f-47e8-beda-57e28fb19124
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CA2WEX-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird durch Makros für Zeichenfolgenkonvertierung `CA2TEX`, `CA2CTEX`, `CT2WEX` und `CT2CWEX` und Typedef **CA2W** verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CA2WEX  
```  
  
#### Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers verwendet im Übersetzungsprozess.  Die Standardlänge ist 128 Bytes.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CA2WEX::CA2WEX](../Topic/CA2WEX::CA2WEX.md)|Der \-Konstruktor.|  
|[CA2WEX::~CA2WEX](../Topic/CA2WEX::~CA2WEX.md)|Der Destruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CA2WEX::operator LPWSTR](../Topic/CA2WEX::operator%20LPWSTR.md)|Konvertierungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CA2WEX::m\_psz](../Topic/CA2WEX::m_psz.md)|Der Datenmember, der die Quellzeichenfolge speichert.|  
|[CA2WEX::m\_szBuffer](../Topic/CA2WEX::m_szBuffer.md)|Der statische Puffer, verwendet die konvertierte Zeichenfolge speichern.|  
  
## Hinweise  
 Es sei denn, zusätzlich, sind Funktionen erforderlich, verwendet `CA2TEX`, `CA2CTEX`, `CT2WEX`, `CT2CWEX` oder **CA2W** im Code.  
  
 Diese Klasse enthält einen statischen Puffer fester Größe, der verwendet wird, um das Ergebnis der Konvertierung zu speichern.  Wenn das Ergebnis zu groß ist, in den statischen Puffer passt, belegt die Klasse mithilfe `malloc` Speicher und gibt den Arbeitsspeicher frei, wenn das Objekt den Gültigkeitsbereich verlässt.  Dadurch wird sichergestellt, dass, anders als die Textkonvertierungsmakros, die in früheren Versionen von ATL verfügbar sind, diese Klasse sicher, in Schleifen zu verwenden ist und nicht der Stapel überschritten.  
  
 Wenn die Klasse versucht, auf dem Heap Speicher reserviert und fehlschlägt, ruft sie `AtlThrow` mit einem Argument von **E\_OUTOFMEMORY** auf.  
  
 Standardmäßig verwenden die ATL\-Konvertierungsklassen und Makros die aktuelle ANSI\-Codepage des Threads für die Konvertierung.  Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter an den Konstruktor für die Klasse.  
  
 Die folgenden Makros sind auf dieser Klasse:  
  
-   `CA2TEX`  
  
-   `CA2CTEX`  
  
-   `CT2WEX`  
  
-   `CT2CWEX`  
  
 Nachfolgende Typedef ist auf dieser Klasse:  
  
-   **CA2W**  
  
 Eine Erläuterung dieser Textkonvertierungsmakros, finden Sie unter [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Beispiel  
 Siehe [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) als ein Beispiel für die Verwendung dieser Makros für Zeichenfolgenkonvertierung.  
  
## Anforderungen  
 **Header:** atlconv.h  
  
## Siehe auch  
 [CA2AEX\-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX\-Klasse](../../atl/reference/ca2caex-class.md)   
 [CW2AEX\-Klasse](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX\-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX\-Klasse](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)