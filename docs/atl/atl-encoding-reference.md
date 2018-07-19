---
title: ATL-Codierungsreferenz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1d8cbb23c390a47b1bbfb7b1a78b327f07b06869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32358627"
---
# <a name="atl-encoding-reference"></a>ATL-Codierungsreferenz
In einem Bereich von allgemeinen Internetstandards wie Uuencode Hexadezimal, und die UTF8-Codierung wird vom Code, der in atlenc.h unterstützt.  
  
### <a name="functions"></a>Funktionen  
  
|||  
|-|-|  
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|  
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|Decodiert eine Zeichenfolge, die als hexadezimaler Text z. B. durch einen vorherigen Aufruf codiert wurde [AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode).|  
|[AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.|  
|[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)|Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.|  
|[AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|  
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren.|  
|[BEncode](reference/atl-text-encoding-functions.md#bencode)|Mit dieser Funktion werden einige Daten mit "B"-Codierung konvertiert.|  
|[BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|  
|[EscapeXML](reference/atl-text-encoding-functions.md#escapexml)|Mit dieser Funktion werden für die Verwendung in XML unsichere Zeichen in sichere Zeichen konvertiert.|  
|[GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars)|Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.|  
|[IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar)|Mit dieser Funktion können Sie herausfinden, ob ein angegebenes Zeichen ein Sonderzeichen ist (kleiner als 32, größer als 126 und kein Tabstopp-, Zeilenvorschub- oder Wagenrücklaufzeichen)|  
|[QEncode](reference/atl-text-encoding-functions.md#qencode)|Mit dieser Funktion werden einige Daten mit "Q"-Codierung konvertiert.|  
|[QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|  
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|Decodiert eine Zeichenfolge, die im quoted-printable-Format wie z. B. durch einen vorherigen Aufruf codiert wurde [QPEncode](reference/atl-text-encoding-functions.md#qpencode).|  
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.|  
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|Mit dieser Funktion können Sie Daten in ein druckbares Format mit Anführungszeichen codieren.|  
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|  
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|Decodiert eine Zeichenfolge, die Uuencoded z. B. durch einen vorherigen Aufruf wurde [UUEncode](reference/atl-text-encoding-functions.md#uuencode).|  
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.|  
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Mit dieser Funktion können Sie Daten in UUEncoded-Daten codieren.|  
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)

