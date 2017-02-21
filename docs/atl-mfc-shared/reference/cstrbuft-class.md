---
title: "CStrBufT Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CStrBufT<TCharType>"
  - "ATL.CStrBufT"
  - "CStrBufT"
  - "ATL::CStrBufT"
  - "ATL.CStrBufT<TCharType>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CStrBufT class"
  - "shared classes, CStrBufT"
  - "Zeichenfolgen [C++], custom memory management"
ms.assetid: 6b50fa8f-87e8-4ed4-a229-157ce128710f
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 18
---
# CStrBufT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt automatische Aufgaben zur Systembereinigung für `GetBuffer` und `ReleaseBuffer`\-Aufrufe auf einem vorhandenen `CStringT`\-Objekt bereit.  
  
## Syntax  
  
```  
  
      template<  
   typename TCharType  
>  
class CStrBufT  
```  
  
#### Parameter  
 *TCharType*  
 Der Zeichentyp der `CStrBufT`\-Klasse.  Einer der folgenden Werte ist möglich:  
  
-   `char` \(für ANSI\-Zeichenfolgen\)  
  
-   `wchar_t` \(für Unicode\-Zeichenfolgen\)  
  
-   **TCHAR** \(für ANSI und Unicode\-Zeichenfolgen\)  
  
## Mitglieder  
  
### Öffentliche Typedefs  
  
|Name|Description|  
|----------|-----------------|  
|`PCXSTR`|Ein Zeiger auf eine Konstantenzeichenfolge.|  
|`PXSTR`|Ein Zeiger auf eine Zeichenfolge.|  
|`StringType`|Der Zeichenfolgentyp, dessen Puffer durch Spezialisierungen dieser Klassenvorlage bearbeitet werden soll.|  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStrBufT::CStrBufT](../Topic/CStrBufT::CStrBufT.md)|Der Konstruktor für das Zeichenfolgenpufferobjekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CStrBufT::SetLength](../Topic/CStrBufT::SetLength.md)|Legt die Zeichenpufferlänge des zugeordneten Zeichenfolgenobjekts fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CStrBufT::operator PCXSTR](../Topic/CStrBufT::operator%20PCXSTR.md)|Ruft einen Zeiger auf **const** Zeichenpuffer des zugeordneten Zeichenfolgenobjekts ab.|  
|[CStrBufT::operator PXSTR](../Topic/CStrBufT::operator%20PXSTR.md)|Ruft einen Zeiger auf das Zeichenpuffer des zugeordneten Zeichenfolgenobjekts ab.|  
  
### Öffentliche Konstanten  
  
|Name|Description|  
|----------|-----------------|  
|[CStrBufT::AUTO\_LENGTH](../Topic/CStrBufT::AUTO_LENGTH.md)|Bestimmen Sie automatisch die neue Länge der Zeichenfolge an der Version.|  
|[CStrBufT::SET\_LENGTH](../Topic/CStrBufT::SET_LENGTH.md)|Legen Sie die Länge des String\-Objekts an GetBuffer\-Zeit fest|  
  
## Hinweise  
 Diese Klasse wird als Wrapperklasse für das Ersetzen der Aufrufe [GetBuffer](../Topic/CSimpleStringT::GetBuffer.md) und [ReleaseBuffer](../Topic/CSimpleStringT::ReleaseBuffer.md) oder [GetBufferSetLength](../Topic/CSimpleStringT::GetBufferSetLength.md) und `ReleaseBuffer` verwendet.  
  
 Hauptsächlich entworfen als Hilfsklasse, `CStrBufT` stellt eine praktische Möglichkeit dar, sodass ein Entwickler mit dem Zeichenpuffer eines Zeichenfolgenobjekts funktioniert, ohne wie oder wann verloren gehen `ReleaseBuffer` aufruft.  Dies ist möglich, da das Wrapperobjekt im Bereich natürlich im Falle einer Ausnahme oder einem Vielfachen verlässt, die Codepfade beenden; Beenden des Destruktors, die Zeichenfolgenressource freizugeben.  
  
## Anforderungen  
 **Header:** atlsimpstr.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [ATL\/MFC Shared Classes](../../atl-mfc-shared/atl-mfc-shared-classes.md)