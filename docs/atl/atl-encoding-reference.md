---
title: "ATL-Codierungsreferenz"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Codierung"
  - "Codierung, Funktionen"
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
caps.latest.revision: 8
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Codierungsreferenz
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Codierung in einem Bereich von allgemeinen Webstandards wie uuencode, Hexadezimal\- und UTF8\-Codierung wird vom Code unterstützt, der in atlenc.h gefunden wird.  
  
### Funktionen  
  
|||  
|-|-|  
|[AtlGetHexValue](../Topic/AtlGetHexValue.md)|Rufen Sie diese Funktion auf, um den numerischen Wert einer Hexadezimalziffer abzurufen.|  
|[AtlHexDecode](../Topic/AtlHexDecode.md)|Decodiert eine Zeichenfolge von Daten, die als hexadezimaler Text wie von eines vorherigen Aufruf [AtlHexEncode](../Topic/AtlHexEncode.md) codiert wurde.|  
|[AtlHexDecodeGetRequiredLength](../Topic/AtlHexDecodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Bytes eines Puffers abzurufen, der die Daten enthalten kann, die von einer Hexadezimal\-codierten Zeichenfolge der angegebenen Länge decodiert wurden.|  
|[AtlHexEncode](../Topic/AtlHexEncode.md)|Rufen Sie diese Funktion, um einige Daten als Zeichenfolge des hexadezimalen Text zu codieren.|  
|[AtlHexEncodeGetRequiredLength](../Topic/AtlHexEncodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Zeichen eines Puffers abzurufen, der eine Zeichenfolge enthalten kann, die von Daten des angegebenen Größe codiert wurde.|  
|[AtlUnicodeToUTF8](../Topic/AtlUnicodeToUTF8.md)|Rufen Sie diese Funktion auf, um eine Unicode\-Zeichenfolge in UTF\-8\-Codierung zu konvertieren.|  
|[BEncode](../Topic/BEncode.md)|Rufen Sie diese Funktion, um einige Daten mithilfe der "B " Codierung zu konvertieren.|  
|[BEncodeGetRequiredLength](../Topic/BEncodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Zeichen eines Puffers abzurufen, der eine Zeichenfolge enthalten kann, die von Daten des angegebenen Größe codiert wurde.|  
|[EscapeXML](../Topic/EscapeXML.md)|Rufen Sie diese Funktion, um Zeichen zu konvertieren, die für die Verwendung in XML zu ihren Entsprechungen sicheren unsicher sind.|  
|[GetExtendedChars](../Topic/GetExtendedChars.md)|Rufen Sie diese Funktion, um die Anzahl von Sonderzeichen in einer Zeichenfolge abzurufen.|  
|[IsExtendedChar](../Topic/IsExtendedChar.md)|Rufen Sie diese Funktion, um festzustellen, ob ein angegebenes Zeichen ein Sonderzeichen ist \(weniger als 32, größer als 126 und keine Registerkarte, ein Zeilenvorschub oder ein Wagenrücklauf\)|  
|[QEncode](../Topic/QEncode.md)|Rufen Sie diese Funktion, um einige Daten mithilfe der "Q\-" Codierung zu konvertieren.|  
|[QEncodeGetRequiredLength](../Topic/QEncodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Zeichen eines Puffers abzurufen, der eine Zeichenfolge enthalten kann, die von Daten des angegebenen Größe codiert wurde.|  
|[QPDecode](../Topic/QPDecode.md)|Decodiert eine Zeichenfolge von Daten, die im zitieren\-druckbaren Format wie von einem früheren Aufruf [QPEncode](../Topic/QPEncode.md) codiert wurde.|  
|[QPDecodeGetRequiredLength](../Topic/QPDecodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Bytes eines Puffers abzurufen, der die Daten enthalten kann, die von zitieren\-druckbar\-codierter Zeichenfolge der angegebenen Länge decodiert wurden.|  
|[QPEncode](../Topic/QPEncode.md)|Rufen Sie diese Funktion, um einige Daten im zitieren\-druckbaren Format zu codieren.|  
|[QPEncodeGetRequiredLength](../Topic/QPEncodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Zeichen eines Puffers abzurufen, der eine Zeichenfolge enthalten kann, die von Daten des angegebenen Größe codiert wurde.|  
|[Uudecode](../Topic/UUDecode.md)|Decodiert eine Zeichenfolge von Daten, die wie von eines vorherigen Aufruf [Uuencode](../Topic/UUEncode.md) uuencoded.|  
|[UUDecodeGetRequiredLength](../Topic/UUDecodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Bytes eines Puffers abzurufen, der die Daten enthalten kann, die von einer uuencoded Zeichenfolge der angegebenen Länge decodiert wurden.|  
|[Uuencode](../Topic/UUEncode.md)|Rufen Sie diese Funktion zu uuencode einige Daten auf.|  
|[UUEncodeGetRequiredLength](../Topic/UUEncodeGetRequiredLength.md)|Rufen Sie diese Funktion auf, um die Größe in Zeichen eines Puffers abzurufen, der eine Zeichenfolge enthalten kann, die von Daten des angegebenen Größe codiert wurde.|  
  
### Makros  
  
|||  
|-|-|  
|[ATL\_ESC\-Flags](../Topic/ATL_ESC%20Flags.md)|Diese Flags werden verwendet, um das Verhalten von [EscapeXML](../Topic/EscapeXML.md) zu steuern.|  
|[ATLSMTP\_QPENCODE\-Flags](../Topic/ATLSMTP_QPENCODE%20Flags.md)|Diese Flags beschreiben, wie zitieren\-druckbare Codierung durch [QPEncode](../Topic/QPEncode.md) ausgeführt werden soll.|  
|[ATLSMTP\_UUENCODE\-Flags](../Topic/ATLSMTP_UUENCODE%20Flags.md)|Diese Flags beschreiben, wie das Uuencoding durch [Uuencode](../Topic/UUEncode.md) ausgeführt werden soll.|  
  
## Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [ATL COM Desktop Components](../atl/atl-com-desktop-components.md)