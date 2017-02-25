---
title: "CW2AEX-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CW2AEX<t_nBufferLength>"
  - "CW2AEX"
  - "ATL.CW2AEX<t_nBufferLength>"
  - "ATL::CW2AEX"
  - "ATL.CW2AEX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2AEX-Klasse"
ms.assetid: 44dc2cf5-dd30-440b-a9b9-b21b43f49843
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CW2AEX-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird durch Makros für Zeichenfolgenkonvertierung `CT2AEX`, `CW2TEX`, `CW2CTEX` und `CT2CAEX` und Typedef **CW2A** verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2AEX  
```  
  
#### Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers verwendet im Übersetzungsprozess.  Die Standardlänge ist 128 Bytes.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2AEX::CW2AEX](../Topic/CW2AEX::CW2AEX.md)|Der \-Konstruktor.|  
|[CW2AEX::~CW2AEX](../Topic/CW2AEX::~CW2AEX.md)|Der Destruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2AEX::operator LPSTR](../Topic/CW2AEX::operator%20LPSTR.md)|Konvertierungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CW2AEX::m\_psz](../Topic/CW2AEX::m_psz.md)|Der Datenmember, der die Quellzeichenfolge speichert.|  
|[CW2AEX::m\_szBuffer](../Topic/CW2AEX::m_szBuffer.md)|Der statische Puffer, verwendet die konvertierte Zeichenfolge speichern.|  
  
## Hinweise  
 Es sei denn, zusätzlich, sind Funktionen erforderlich, verwendet `CT2AEX`, `CW2TEX`, `CW2CTEX`, `CT2CAEX` oder **CW2A** im Code.  
  
 Diese Klasse enthält einen statischen Puffer fester Größe, der verwendet wird, um das Ergebnis der Konvertierung zu speichern.  Wenn das Ergebnis zu groß ist, in den statischen Puffer passt, belegt die Klasse mithilfe `malloc` Speicher und gibt den Arbeitsspeicher frei, wenn das Objekt den Gültigkeitsbereich verlässt.  Dadurch wird sichergestellt, dass, anders als die Textkonvertierungsmakros, die in früheren Versionen von ATL verfügbar sind, diese Klasse sicher, in Schleifen zu verwenden ist und nicht der Stapel überschritten.  
  
 Wenn die Klasse versucht, auf dem Heap Speicher reserviert und fehlschlägt, ruft sie `AtlThrow` mit einem Argument von **E\_OUTOFMEMORY** auf.  
  
 Standardmäßig verwenden die ATL\-Konvertierungsklassen und Makros die aktuelle ANSI\-Codepage des Threads für die Konvertierung.  Wenn Sie dieses Verhalten für eine bestimmte Konvertierung überschreiben möchten, geben Sie die Codepage als zweiten Parameter an den Konstruktor für die Klasse.  
  
 Die folgenden Makros sind auf dieser Klasse:  
  
-   `CT2AEX`  
  
-   `CW2TEX`  
  
-   `CW2CTEX`  
  
-   `CT2CAEX`  
  
 Nachfolgende Typedef ist auf dieser Klasse:  
  
-   **CW2A**  
  
 Eine Erläuterung dieser Textkonvertierungsmakros, finden Sie unter [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md).  
  
## Beispiel  
 Siehe [ATL und Makros für MFC\-Zeichenfolgenkonvertierung](../Topic/ATL%20and%20MFC%20String%20Conversion%20Macros.md) als ein Beispiel für die Verwendung dieser Makros für Zeichenfolgenkonvertierung.  
  
## Anforderungen  
 **Header:** atlconv.h  
  
## Siehe auch  
 [CA2AEX\-Klasse](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX\-Klasse](../../atl/reference/ca2caex-class.md)   
 [CA2WEX\-Klasse](../../atl/reference/ca2wex-class.md)   
 [CW2CWEX\-Klasse](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX\-Klasse](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)