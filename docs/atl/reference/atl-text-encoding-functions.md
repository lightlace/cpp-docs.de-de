---
title: ATL-Textcodierung-Funktionen
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlGetHexValue
- atlbase/ATL::AtlGetVersion
- atlenc/ATL::AtlHexDecode
- atlenc/ATL::AtlHexDecodeGetRequiredLength
- atlenc/ATL::AtlHexEncode
- atlenc/ATL::AtlHexEncodeGetRequiredLength
- atlenc/ATL::AtlHexValue
- atlenc/ATL::BEncode
- atlenc/ATL::BEncodeGetRequiredLength
- atlenc/ATL::EscapeXML
- atlenc/ATL::GetExtendedChars
- atlenc/ATL::IsExtendedChar
- atlenc/ATL::QEncode
- atlenc/ATL::QEncodeGetRequiredLength
- atlenc/ATL::QPDecode
- atlenc/ATL::QPDecodeGetRequiredLength
- atlenc/ATL::QPEncode
- atlenc/ATL::QPEncodeGetRequiredLength
- atlenc/ATL::UUDecode
- atlenc/ATL::UUDecodeGetRequiredLength
- atlenc/ATL::UUEncode
- atlenc/ATL::UUEncodeGetRequiredLength
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
ms.openlocfilehash: 2a076b666577920c940413fba4951f7de5f24fc6
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55850258"
---
# <a name="atl-text-encoding-functions"></a>ATL-Textcodierung-Funktionen

Diese Funktionen unterstützen, Text, Codierung und Decodierung durchführen.

|||
|-|-|
|[AtlGetHexValue](#atlgethexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|
|[AtlGetVersion](#atlgetversion)|Rufen Sie diese Funktion zum Abrufen der Version der ATL-Bibliothek, die Sie verwenden.  |
|[AtlHexDecode](#atlhexdecode)|Decodiert eine Zeichenfolge mit Daten, die als hexadezimaler Text wie z. B. durch einen vorherigen Aufruf von codiert wurde [AtlHexEncode](#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.|
|[AtlHexEncode](#atlhexencode)|Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[AtlHexValue](#atlhexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren. |
|[BEncode](#bencode)|Mit dieser Funktion werden einige Daten mit "B"-Codierung konvertiert.|
|[BEncodeGetRequiredLength](#bencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[EscapeXML](#escapexml)|Mit dieser Funktion werden für die Verwendung in XML unsichere Zeichen in sichere Zeichen konvertiert.|
|[GetExtendedChars](#getextendedchars)|Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.|
|[IsExtendedChar](#isextendedchar)|Mit dieser Funktion können Sie herausfinden, ob ein angegebenes Zeichen ein Sonderzeichen ist (kleiner als 32, größer als 126 und kein Tabstopp-, Zeilenvorschub- oder Wagenrücklaufzeichen)|
|[QEncode](#qencode)|Mit dieser Funktion werden einige Daten mit "Q"-Codierung konvertiert.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[QPDecode](#qpdecode)|Decodiert eine Zeichenfolge, die in in ein druckbares Format z. B. durch einen vorherigen Aufruf von codiert wurde [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.|
|[QPEncode](#qpencode)|Mit dieser Funktion können Sie Daten in ein druckbares Format mit Anführungszeichen codieren.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[UUDecode](#uudecode)|Decodiert eine Zeichenfolge, die mit UUENCODE wie z. B. durch einen vorherigen Aufruf von [UUEncode](#uuencode).|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.|
|[UUEncode](#uuencode)|Mit dieser Funktion können Sie Daten in UUEncoded-Daten codieren. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|

## <a name="requirements"></a>Anforderungen

**Header:** atlenc.h

## <a name="atlgethexvalue"></a> AtlGetHexValue

Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.

```
inline char AtlGetHexValue(char chIn) throw();
```

### <a name="parameters"></a>Parameter

*chIn*<br/>
Das hexadezimale Zeichen "0"-"9", "A"-"F" bzw. "a"-"f".

### <a name="return-value"></a>Rückgabewert

Der numerische Wert, der das eingegebene Zeichen, die als eine hexadezimale Ziffer interpretiert werden soll. Z. B. eine Eingabe von "0" gibt den Wert 0 zurück, und eine Eingabe von "A" gibt einen Wert von 10 zurück. Wenn das eingegebene Zeichen nicht um eine hexadezimale Ziffer ist, gibt diese Funktion-1 zurück.

## <a name="atlgetversion"></a> AtlGetVersion

Rufen Sie diese Funktion zum Abrufen der Version der ATL-Bibliothek, die Sie verwenden.

```
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);
```

### <a name="parameters"></a>Parameter

*pReserved*<br/>
Ein reserviertes Zeiger.

### <a name="return-value"></a>Rückgabewert

Gibt einen DWORD-Integer-Wert, der Version der ATL-Bibliothek, die Sie kompilieren oder ausführen.

## <a name="example"></a>Beispiel

Die Funktion sollte wie folgt aufgerufen werden.

[!code-cpp[NVC_ATL_Utilities#95](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** atlbase.h

## <a name="atlhexdecode"></a> AtlHexDecode

Decodiert eine Zeichenfolge mit Daten, die als hexadezimaler Text wie z. B. durch einen vorherigen Aufruf von codiert wurde [AtlHexEncode](#atlhexencode).

```
inline BOOL AtlHexDecode(
   LPCSTR pSrcData,
   int nSrcLen,
   LPBYTE pbDest,
   int* pnDestLen) throw();
```

### <a name="parameters"></a>Parameter

*pSrcData*<br/>
Die Zeichenfolge, die mit den Daten, die decodiert werden.

*nSrcLen*<br/>
Die Länge in Zeichen des *pSrcData*.

*pbDest*<br/>
Vom Aufrufer reservierte Puffer zum Empfangen von der decodierten Daten.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Bytes enthält *PbDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Bytes, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes an.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

## <a name="atlhexdecodegetrequiredlength"></a> AtlHexDecodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.

```
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Zeichen in die codierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte, erforderliche *nSrcLen* Zeichen.

## <a name="atlhexencode"></a> AtlHexEncode

Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.

```
inline BOOL AtlHexEncode(
   const BYTE * pbSrcData,
   int nSrcLen,
   LPSTR szDest,
int * pnDestLen) throw();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Der Puffer mit den Daten codiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der Daten, die codiert werden.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, um die codierten Daten empfangen.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Zeichen des Puffers.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Jedes Byte der Quelldaten wird als 2 hexadezimalen Zeichen codiert.

## <a name="atlhexencodegetrequiredlength"></a> AtlHexEncodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.

```
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Bytes an Daten codiert werden.

### <a name="return-value"></a>Rückgabewert

Die erforderliche Anzahl von Zeichen für einen Puffer, die codierte Daten enthalten könnten *nSrcLen* Bytes.

## <a name="atlhexvalue"></a> AtlHexValue

Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.

```
inline short AtlHexValue(char chIn) throw();
```

### <a name="parameters"></a>Parameter

*chIn*<br/>
Das hexadezimale Zeichen "0"-"9", "A"-"F" bzw. "a"-"f".

### <a name="return-value"></a>Rückgabewert

Der numerische Wert, der das eingegebene Zeichen, die als eine hexadezimale Ziffer interpretiert werden soll. Z. B. eine Eingabe von "0" gibt den Wert 0 zurück, und eine Eingabe von "A" gibt einen Wert von 10 zurück. Wenn das eingegebene Zeichen nicht um eine hexadezimale Ziffer ist, gibt diese Funktion-1 zurück.

## <a name="atlunicodetoutf8"></a> AtlUnicodeToUTF8

Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren.

```
ATL_NOINLINE inline int AtlUnicodeToUTF8(
   LPCWSTR wszSrc,
   int nSrc,
   LPSTR szDest,
   int nDest) throw();
```

### <a name="parameters"></a>Parameter

*wszSrc*<br/>
Die Unicode-Zeichenfolge konvertiert werden

*nSrc*<br/>
Die Länge in Zeichen, die Unicode-Zeichenfolge.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, in der konvertierten Zeichenfolge.

*nDest*<br/>
Die Länge in Byte des Puffers.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Zeichen für die konvertierte Zeichenfolge zurück.

### <a name="remarks"></a>Hinweise

Um zu bestimmen, die Größe des Puffers für die konvertierte Zeichenfolge erforderlich, die mit dieser Funktion werden Übergabewert von 0 für *SzDest* und *nDest*.

## <a name="bencode"></a> BEncode

Mit dieser Funktion werden einige Daten mit "B"-Codierung konvertiert.

```
inline BOOL BEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet) throw();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Der Puffer mit den Daten codiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der Daten, die codiert werden.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, um die codierten Daten empfangen.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Zeichen des Puffers.

*pszCharSet*<br/>
Der Zeichensatz, der für die Konvertierung verwendet.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Das Codierungsschema "B" ist in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="bencodegetrequiredlength"></a> BEncodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.

```
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Bytes an Daten codiert werden.

*nCharsetLen*<br/>
Die Länge in Zeichen des Zeichensatzes, der für die Konvertierung verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Die erforderliche Anzahl von Zeichen für einen Puffer, die codierte Daten enthalten könnten *nSrcLen* Bytes.

### <a name="remarks"></a>Hinweise

Das Codierungsschema "B" ist in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="escapexml"></a> "Escapexml"

Mit dieser Funktion werden für die Verwendung in XML unsichere Zeichen in sichere Zeichen konvertiert.

```
inline int EscapeXML(
   const wchar_t * szIn,
   int nSrcLen,
   wchar_t * szEsc,
   int nDestLen,
   DWORD dwFlags = ATL_ESC_FLAG_NONE) throw();
```

### <a name="parameters"></a>Parameter

*szIn*<br/>
Die zu konvertierende Zeichenfolge.

*nSrclen*<br/>
Die Länge in Zeichen der Zeichenfolge, die konvertiert werden.

*szEsc*<br/>
Vom Aufrufer reservierte Puffer, in der konvertierten Zeichenfolge.

*nDestLen*<br/>
Die Länge in Zeichen, die vom Aufrufer reservierte Puffer.

*dwFlags*<br/>
ATL_ESC-Flags, die beschreibt, wie die Konvertierung ist, ausgeführt werden.

- ATL_ESC_FLAG_NONE Standardverhalten. Anführungszeichen sind Markierungen und Apostrophe nicht konvertiert.
- Markierungen ATL_ESC_FLAG_ATTR zitieren und Apostrophe werden in konvertiert `&quot;` und `&apos;` bzw.

### <a name="return-value"></a>Rückgabewert

Die Länge des konvertierten Zeichenfolge in Zeichen.

### <a name="remarks"></a>Hinweise

Mögliche Konvertierungen, die von dieser Funktion werden in der Tabelle angezeigt:

|Source|Ziel|
|------------|-----------------|
|\<|&lt;|
|>|&gt;|
|&|&amp;|
|'|&apos;|
|"|&quot;|

## <a name="getextendedchars"></a> GetExtendedChars

Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.

```
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();
```

### <a name="parameters"></a>Parameter

*szSrc*<br/>
Die Zeichenfolge analysiert werden.

*nSrcLen*<br/>
Die Länge der Zeichenfolge in Zeichen.

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl von Sonderzeichen finden Sie in der Zeichenfolge, die laut [IsExtendedChar](#isextendedchar).

## <a name="isextendedchar"></a> IsExtendedChar

Mit dieser Funktion können Sie herausfinden, ob ein angegebenes Zeichen ein Sonderzeichen ist (kleiner als 32, größer als 126 und kein Tabstopp-, Zeilenvorschub- oder Wagenrücklaufzeichen)

```
inline int IsExtendedChar(char ch) throw();
```

### <a name="parameters"></a>Parameter

*ch*<br/>
Das Zeichen, das getestet werden

### <a name="return-value"></a>Rückgabewert

TRUE, wenn das Zeichen erweitert wird, andernfalls "false".

## <a name="qencode"></a> QEncode

Mit dieser Funktion werden einige Daten mit "Q"-Codierung konvertiert.

```
inline BOOL QEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCSTR pszCharSet,
   int* pnNumEncoded = NULL) throw();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Der Puffer mit den Daten codiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der Daten, die codiert werden.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, um die codierten Daten empfangen.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Zeichen des Puffers.

*pszCharSet*<br/>
Der Zeichensatz, der für die Konvertierung verwendet.

*pnNumEncoded*<br/>
Ein Zeiger auf eine Variable, die bei der Rückgabe die Anzahl der unsicheren Zeichen enthält, die konvertiert werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Das Codierungsschema "Q" wird in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="qencodegetrequiredlength"></a> QEncodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.

```
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Bytes an Daten codiert werden.

*nCharsetLen*<br/>
Die Länge in Zeichen des Zeichensatzes, der für die Konvertierung verwendet werden soll.

### <a name="return-value"></a>Rückgabewert

Die erforderliche Anzahl von Zeichen für einen Puffer, die codierte Daten enthalten könnten *nSrcLen* Bytes.

### <a name="remarks"></a>Hinweise

Das Codierungsschema "Q" wird in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).

## <a name="qpdecode"></a> QPDecode

Decodiert eine Zeichenfolge, die in in ein druckbares Format z. B. durch einen vorherigen Aufruf von codiert wurde [QPEncode](#qpencode).

```
inline BOOL QPDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
[in] Der Puffer mit den Daten, die decodiert werden.

*nSrcLen*<br/>
[in] Die Länge in Bytes der *PbSrcData*.

*szDest*<br/>
[out] Vom Aufrufer reservierte Puffer zum Empfangen von der decodierten Daten.

*pnDestLen*<br/>
[out] Zeiger auf eine Variable, die die Länge in Bytes enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Bytes, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes an.

*dwFlags*<br/>
[in] ATLSMTP_QPENCODE-Flags, die beschreibt, wie die Konvertierung ist, ausgeführt werden.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die quoted-printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpdecodegetrequiredlength"></a> QPDecodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.

```
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Zeichen in die codierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte, erforderliche *nSrcLen* Zeichen.

### <a name="remarks"></a>Hinweise

Die quoted-printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpencode"></a> QPEncode

Mit dieser Funktion können Sie Daten in ein druckbares Format mit Anführungszeichen codieren.

```
inline BOOL QPEncode(
   BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Der Puffer mit den Daten codiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der Daten, die codiert werden.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, um die codierten Daten empfangen.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Zeichen des Puffers.

*dwFlags*<br/>
ATLSMTP_QPENCODE-Flags, die beschreibt, wie die Konvertierung ist, ausgeführt werden.

- ATLSMTP_QPENCODE_DOT, wenn ein Punkt angezeigt wird, am Anfang einer Zeile, wird der Ausgabe hinzugefügt sowie codiert.

- Fügt der ATLSMTP_QPENCODE_TRAILING_SOFT `=\r\n` auf die codierte Zeichenfolge.

Die quoted-printable-Codierungsschema finden Sie im [RFC 2045](http://www.ietf.org/rfc/rfc2045.txt).

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Die quoted-printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="qpencodegetrequiredlength"></a> QPEncodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.

```
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Bytes an Daten codiert werden.

### <a name="return-value"></a>Rückgabewert

Die erforderliche Anzahl von Zeichen für einen Puffer, die codierte Daten enthalten könnten *nSrcLen* Bytes.

### <a name="remarks"></a>Hinweise

Die quoted-printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).

## <a name="uudecode"></a> UUDecode

Decodiert eine Zeichenfolge, die mit UUENCODE wie z. B. durch einen vorherigen Aufruf von [UUEncode](#uuencode).

```
inline BOOL UUDecode(
   BYTE* pbSrcData,
   int nSrcLen,
   BYTE* pbDest,
   int* pnDestLen) throw ();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Die Zeichenfolge, die mit den Daten, die decodiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der *PbSrcData*.

*pbDest*<br/>
Vom Aufrufer reservierte Puffer zum Empfangen von der decodierten Daten.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Bytes enthält *PbDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Bytes, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes an.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Implementierung Binärstreams in UUENCODE folgt der POSIX-P1003.2b/D11-Spezifikation.

## <a name="uudecodegetrequiredlength"></a> UUDecodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.

```
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Zeichen in die codierte Zeichenfolge.

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte, erforderliche *nSrcLen* Zeichen.

### <a name="remarks"></a>Hinweise

Diese Implementierung Binärstreams in UUENCODE folgt der POSIX-P1003.2b/D11-Spezifikation.

## <a name="uuencode"></a> UUEncode

Mit dieser Funktion können Sie Daten in UUEncoded-Daten codieren.

```
inline BOOL UUEncode(
   const BYTE* pbSrcData,
   int nSrcLen,
   LPSTR szDest,
   int* pnDestLen,
   LPCTSTR lpszFile = _T("file"),
   DWORD dwFlags = 0) throw ();
```

### <a name="parameters"></a>Parameter

*pbSrcData*<br/>
Der Puffer mit den Daten codiert werden.

*nSrcLen*<br/>
Die Länge in Bytes der Daten, die codiert werden.

*szDest*<br/>
Vom Aufrufer reservierte Puffer, um die codierten Daten empfangen.

*pnDestLen*<br/>
Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzDest*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Zeichen des Puffers.

*lpszFile*<br/>
Datei, die dem Header hinzugefügt werden, wenn ATLSMTP_UUENCODE_HEADER in angegebenen *DwFlags*.

*dwFlags*<br/>
Flags, die Steuerung des Verhaltens dieser Funktion.

- ATLSMTP_UUENCODE_HEADE der Header wird codiert werden.

- ATLSMTP_UUENCODE_END am Ende wird codiert werden.

- ATLSMTP_UUENCODE_DOT Daten helfen werden ausgeführt.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Implementierung Binärstreams in UUENCODE folgt der POSIX-P1003.2b/D11-Spezifikation.

## <a name="uuencodegetrequiredlength"></a> UUEncodeGetRequiredLength

Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.

```
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();
```

### <a name="parameters"></a>Parameter

*nSrcLen*<br/>
Die Anzahl der Bytes an Daten codiert werden.

### <a name="return-value"></a>Rückgabewert

Die erforderliche Anzahl von Zeichen für einen Puffer, die codierte Daten enthalten könnten *nSrcLen* Bytes.

### <a name="remarks"></a>Hinweise

Diese Implementierung Binärstreams in UUENCODE folgt der POSIX-P1003.2b/D11-Spezifikation.

## <a name="see-also"></a>Siehe auch

[Konzepte](../active-template-library-atl-concepts.md)<br/>
[ATL-COM-Desktop-Komponenten](../atl-com-desktop-components.md)
