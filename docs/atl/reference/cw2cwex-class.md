---
title: "CW2CWEX-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CW2CWEX"
  - "ATL::CW2CWEX"
  - "ATL.CW2CWEX"
  - "ATL.CW2CWEX<t_nBufferLength>"
  - "ATL::CW2CWEX<t_nBufferLength>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CW2CWEX-Klasse"
ms.assetid: d654b22b-05a6-410f-a0ec-9a2cbbb4cca7
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CW2CWEX-Klasse
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse wird durch Makros für Zeichenfolgenkonvertierung `CW2CTEX` und `CT2CWEX` und Typedef `CW2W` verwendet.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template<  
int t_nBufferLength= 128  
>  
class CW2CWEX  
```  
  
#### Parameter  
 `t_nBufferLength`  
 Die Größe des Puffers verwendet im Übersetzungsprozess.  Die Standardlänge ist 128 Bytes.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2CWEX::CW2CWEX](../Topic/CW2CWEX::CW2CWEX.md)|Der \-Konstruktor.|  
|[CW2CWEX::~CW2CWEX](../Topic/CW2CWEX::~CW2CWEX.md)|Der Destruktor.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CW2CWEX::operator LPCWSTR](../Topic/CW2CWEX::operator%20LPCWSTR.md)|Konvertierungsoperator.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CW2CWEX::m\_psz](../Topic/CW2CWEX::m_psz.md)|Der Datenmember, der die Quellzeichenfolge speichert.|  
  
## Hinweise  
 Es sei denn, zusätzlich, sind Funktionen erforderlich, verwendet `CW2CTEX`, `CT2CWEX` oder `CW2W` im Code.  
  
 Diese Klasse ist sicher, in Schleifen zu verwenden und nicht der Hookfunktion.  Standardmäßig verwenden die ATL\-Konvertierungsklassen und Makros die aktuelle ANSI\-Codepage des Threads für die Konvertierung.  
  
 Die folgenden Makros sind auf dieser Klasse:  
  
-   `CW2CTEX`  
  
-   `CT2CWEX`  
  
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
 [CW2WEX\-Klasse](../../atl/reference/cw2wex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)