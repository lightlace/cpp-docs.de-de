---
title: ATL-Codierungsreferenz
ms.date: 11/04/2016
helpviewer_keywords:
- encoding
- encoding, functions
ms.assetid: 82d4fdf3-3c4a-4fe2-b297-8ffb4714406f
ms.openlocfilehash: a9c7689e49efce0d65e945f1a032a680e2277594
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2019
ms.locfileid: "68375865"
---
# <a name="atl-encoding-reference"></a>ATL-Codierungsreferenz

Die Codierung in einem Bereich allgemeiner Internet Standards wie UUEncode, hexadezimal und UTF8 wird von dem in atlenc. h gefundenen Code unterstützt.

### <a name="functions"></a>Funktionen

|||
|-|-|
|[AtlGetHexValue](reference/atl-text-encoding-functions.md#atlgethexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|
|[AtlHexDecode](reference/atl-text-encoding-functions.md#atlhexdecode)|Decodiert eine Zeichenfolge von Daten, die als hexadezimal Text codiert wurde, z. b. durch einen vorherigen-Befehl von [atlhexencode](reference/atl-text-encoding-functions.md#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.|
|[AtlHexEncode](reference/atl-text-encoding-functions.md#atlhexencode)|Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.|
|[AtlHexEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#atlhexencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[AtlUnicodeToUTF8](reference/atl-text-encoding-functions.md#atlunicodetoutf8)|Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren.|
|[BEncode](reference/atl-text-encoding-functions.md#bencode)|Mit dieser Funktion werden einige Daten mit "B"-Codierung konvertiert.|
|[BEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#bencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|["Escapexml"](reference/atl-text-encoding-functions.md#escapexml)|Mit dieser Funktion werden für die Verwendung in XML unsichere Zeichen in sichere Zeichen konvertiert.|
|[GetExtendedChars](reference/atl-text-encoding-functions.md#getextendedchars)|Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.|
|[IsExtendedChar](reference/atl-text-encoding-functions.md#isextendedchar)|Mit dieser Funktion können Sie herausfinden, ob ein bestimmtes Zeichen ein erweitertes Zeichen ist (kleiner als 32, größer als 126 und keine Registerkarte, Zeilenvorschub oder Wagen Rücklauf).|
|[QEncode](reference/atl-text-encoding-functions.md#qencode)|Mit dieser Funktion werden einige Daten mit "Q"-Codierung konvertiert.|
|[QEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[QPDecode](reference/atl-text-encoding-functions.md#qpdecode)|Decodiert eine Zeichenfolge von Daten, die in einem druckbaren Format in Anführungszeichen codiert wurden, z. b. durch einen vorherigen [qtzcode](reference/atl-text-encoding-functions.md#qpencode)-Rückruf.|
|[QPDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.|
|[QPEncode](reference/atl-text-encoding-functions.md#qpencode)|Mit dieser Funktion können Sie Daten in ein druckbares Format mit Anführungszeichen codieren.|
|[QPEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#qpencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[UUDecode](reference/atl-text-encoding-functions.md#uudecode)|Decodiert eine Zeichenfolge von Daten, die uucodiert wurde, wie z. b. durch einen vorherigen-Befehl von [UUEncode](reference/atl-text-encoding-functions.md#uuencode).|
|[UUDecodeGetRequiredLength](reference/atl-text-encoding-functions.md#uudecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.|
|[UUEncode](reference/atl-text-encoding-functions.md#uuencode)|Mit dieser Funktion können Sie Daten in UUEncoded-Daten codieren.|
|[UUEncodeGetRequiredLength](reference/atl-text-encoding-functions.md#uuencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../atl/atl-com-desktop-components.md)
