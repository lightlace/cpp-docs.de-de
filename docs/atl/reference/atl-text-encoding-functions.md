---
title: ATL-Textcodierung Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ae1648b-2b87-4112-92aa-0069fcfd23da
caps.latest.revision: 3
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: 86433bebe3fe84a027d7725525e028d80b67e358
ms.lasthandoff: 02/24/2017

---
# <a name="atl-text-encoding-functions"></a>ATL-Textcodierung-Funktionen
Diese Funktionen unterstützen Text codieren und decodieren.

|||  
|-|-|  
|[AtlGetHexValue](#atlgethexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.|   
|[AtlGetVersion](#atlgetversion)|Rufen Sie diese Funktion, um die Version des ATL-Bibliothek abgerufen, die Sie verwenden.  |  
|[AtlHexDecode](#atlhexdecode)|Decodiert eine Zeichenfolge mit Daten, die durch einen vorherigen Aufruf als hexadezimaler Text codiert wurde [AtlHexEncode](#atlhexencode).|
|[AtlHexDecodeGetRequiredLength](#atlhexdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.|
|[AtlHexEncode](#atlhexencode)|Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.|
|[AtlHexEncodeGetRequiredLength](#atlhexencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[AtlHexValue](#atlhexvalue)|Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen. |
|[AtlUnicodeToUTF8](#atlunicodetoutf8)|Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren. |
|[BEncode](#bencode)|Mit dieser Funktion werden einige Daten mit "B"-Codierung konvertiert.|
|[BEncodeGetRequiredLength](#beencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|["Escapexml"](#escapexml)|Mit dieser Funktion werden für die Verwendung in XML unsichere Zeichen in sichere Zeichen konvertiert.|
|[GetExtendedChars](#getextendedchars)|Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.|
|[IsExtendedChar](#isextendedchar)|Mit dieser Funktion können Sie herausfinden, ob ein angegebenes Zeichen ein Sonderzeichen ist (kleiner als 32, größer als 126 und kein Tabstopp-, Zeilenvorschub- oder Wagenrücklaufzeichen)|
|[QEncode](#qencode)|Mit dieser Funktion werden einige Daten mit "Q"-Codierung konvertiert.  |
|[QEncodeGetRequiredLength](#qencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[QPDecode](#qpdecode)|Decodiert eine Zeichenfolge, die durch einen vorherigen Aufruf von quoted printable-Format wie z. B. codiert wurde [QPEncode](#qpencode).|
|[QPDecodeGetRequiredLength](#qpdecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.|
|[QPEncode](#qpencode)|Mit dieser Funktion können Sie Daten in ein druckbares Format mit Anführungszeichen codieren.|
|[QPEncodeGetRequiredLength](#qpencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|
|[UUDecode](#uudecode)|Decodiert eine Zeichenfolge, die Uuencoded wie z. B. durch einen vorherigen Aufruf wurde [UUEncode](#uuencode).|
|[UUDecodeGetRequiredLength](#uudecodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.|
|[UUEncode](#uuencode)|Mit dieser Funktion können Sie Daten in UUEncoded-Daten codieren. |
|[UUEncodeGetRequiredLength](#uuencodegetrequiredlength)|Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.|

## <a name="requirements"></a>Anforderungen  
 **Header:** atlenc.h  
 
## <a name="a-nameatlgethexvaluea-atlgethexvalue"></a><a name="atlgethexvalue"></a>AtlGetHexValue
Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.  
  
```    
inline char AtlGetHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `chIn`  
 Die hexadezimalen Zeichen '0'-'9', 'A'-'F' oder 'a'-'f'.  
  
### <a name="return-value"></a>Rückgabewert  
 Der numerische Wert des Eingabezeichens als eine hexadezimale Ziffer interpretiert. Z. B. eine Eingabe von "0" gibt den Wert 0 zurück, und die Eingabe von "A" gibt einen Wert von 10. Wenn das Eingabezeichen keine hexadezimale Ziffer ist, gibt diese Funktion-1 zurück.  
  
## <a name="a-nameatlgetversiona-atlgetversion"></a><a name="atlgetversion"></a>AtlGetVersion
Rufen Sie diese Funktion, um die Version des ATL-Bibliothek abgerufen, die Sie verwenden.  
  
```  
ATLAPI_(DWORD) AtlGetVersion(void* pReserved);  
```  
  
### <a name="parameters"></a>Parameter  
 `pReserved`  
 Ein reserviertes Zeiger.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine `DWORD` Ganzzahlwert, der die Version des ATL-Bibliothek, die Sie kompilieren oder ausführen.  
  
## <a name="example"></a>Beispiel  
 Die Funktion sollte wie folgt aufgerufen werden.  
  
 [!code-cpp[NVC_ATL_Utilities&#95;](../../atl/codesnippet/cpp/atl-text-encoding-functions_1.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
 **Header:** atlbase.h  

## <a name="a-nameatlhexdecodea-atlhexdecode"></a><a name="atlhexdecode"></a>AtlHexDecode
Decodiert eine Zeichenfolge mit Daten, die durch einen vorherigen Aufruf als hexadezimaler Text codiert wurde [AtlHexEncode](#atlhexencode).  
  
```    
inline BOOL AtlHexDecode(  
   LPCSTR pSrcData,  
   int nSrcLen,  
   LPBYTE pbDest,  
   int* pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `pSrcData`  
 Die Zeichenfolge, die mit den Daten, die decodiert werden.  
  
 `nSrcLen`  
 Die Länge in Zeichen des `pSrcData`.  
  
 `pbDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der entschlüsselte Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Bytes enthält `pbDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der in den Puffer geschriebenen Bytes. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
## <a name="a-nameatlhexdecodegetrequiredlengtha-atlhexdecodegetrequiredlength"></a><a name="atlhexdecodegetrequiredlength"></a>AtlHexDecodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer hexadezimal codierten Zeichenfolge der angegebenen Länge decodiert wurden.  
  
```  
inline int AtlHexDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Zeichen in die codierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte erforderlichen `nSrcLen` Zeichen.  
  
## <a name="a-nameatlhexencodea-atlhexencode"></a><a name="atlhexencode"></a>AtlHexEncode
Mit dieser Funktion werden einige Daten als Zeichenfolge mit hexadezimalem Text codiert.  
  
```  
inline BOOL AtlHexEncode(  
   const BYTE * pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
int * pnDestLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `pbSrcData`  
 Der Puffer mit den Daten codiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes der Daten, die codiert werden.  
  
 `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der codierten Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Byte der Quelldaten wird als 2 hexadezimalen Zeichen codiert.  
  
## <a name="a-nameatlhexencodegetrequiredlengtha-atlhexencodegetrequiredlength"></a><a name="atlhexencodegetrequiredlength"></a>AtlHexEncodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.  
  
```  
inline int AtlHexEncodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Bytes der Daten codiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erforderliche Anzahl von Zeichen für einen Puffer, der codierte Daten enthalten könnten `nSrcLen` Bytes.  
  
## <a name="a-nameatlhexvaluea-atlhexvalue"></a><a name="atlhexvalue"></a>AtlHexValue
Mit dieser Funktion wird der numerische Wert einer Hexadezimalziffer abgerufen.  
  
```  
inline short AtlHexValue(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `chIn`  
 Die hexadezimalen Zeichen '0'-'9', 'A'-'F' oder 'a'-'f'.  
  
### <a name="return-value"></a>Rückgabewert  
 Der numerische Wert des Eingabezeichens als eine hexadezimale Ziffer interpretiert. Z. B. eine Eingabe von "0" gibt den Wert 0 zurück, und die Eingabe von "A" gibt einen Wert von 10. Wenn das Eingabezeichen keine hexadezimale Ziffer ist, gibt diese Funktion-1 zurück.  
  
## <a name="a-nameatlunicodetoutf8a-atlunicodetoutf8"></a><a name="atlunicodetoutf8"></a>AtlUnicodeToUTF8
Mit dieser Funktion können Sie eine Unicode-Zeichenfolge in UTF-8 konvertieren.  
  
```  
ATL_NOINLINE inline int AtlUnicodeToUTF8(  
   LPCWSTR wszSrc,  
   int nSrc,  
   LPSTR szDest,  
   int nDest) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *wszSrc*  
 Die Unicode-Zeichenfolge konvertiert werden  
  
 `nSrc`  
 Die Länge in Zeichen der Unicode-Zeichenfolge.  
  
 `szDest`  
 Vom Aufrufer reservierten Puffer die konvertierte Zeichenfolge empfangen.  
  
 `nDest`  
 Die Länge in Bytes des Puffers.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Zeichen für die konvertierte Zeichenfolge zurück.  
  
### <a name="remarks"></a>Hinweise  
 Um zu bestimmen, die Größe des Puffers für die konvertierte Zeichenfolge erforderlich sind, rufen Sie diese Funktion übergeben 0 für `szDest` und `nDest`.  
  
## <a name="a-namebencodea-bencode"></a><a name="bencode"></a>BEncode  
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
 `pbSrcData`  
 Der Puffer mit den Daten codiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes der Daten, die codiert werden.  
  
 `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der codierten Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Zeichen.  
  
 `pszCharSet`  
 Der Zeichensatz, der für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Codierungsschema "B" ist in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-namebeencodegetrequiredlengtha-bencodegetrequiredlength"></a><a name="beencodegetrequiredlength"></a>BEncodeGetRequiredLength 
Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.  
  
```  
inline int BEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Bytes der Daten codiert werden.  
  
 `nCharsetLen`  
 Die Länge in Zeichen des Zeichensatzes, der für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erforderliche Anzahl von Zeichen für einen Puffer, der codierte Daten enthalten könnten `nSrcLen` Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Das Codierungsschema "B" ist in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameescapexmla-escapexml"></a><a name="escapexml"></a>"Escapexml"
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
 `szIn`  
 Die zu konvertierende Zeichenfolge.  
  
 *nSrclen*  
 Die Länge in Zeichen der Zeichenfolge konvertiert werden.  
  
 *szEsc*  
 Vom Aufrufer reservierten Puffer die konvertierte Zeichenfolge empfangen.  
  
 *nDestLen*  
 Die Länge des vom Aufrufer reservierten Puffers in Zeichen.  
  
 `dwFlags`  
 Flags, die beschreiben, wie die Konvertierung erfolgt, ausgeführt werden. Finden Sie unter [ATL_ESC Flags](http://msdn.microsoft.com/library/daf3aa3c-7498-4d63-9fb6-e05b4815c2b8).  
  
### <a name="return-value"></a>Rückgabewert  
 Die Länge in Zeichen der konvertierten Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Mögliche Konvertierungen, die von dieser Funktion werden in der Tabelle angezeigt:  
  
|Quelle|Ziel|  
|------------|-----------------|  
|\<|&lt;|  
|>|&gt;|  
|&|&amp;|  
|'|&apos;|  
|"|&quot;|  
  
## <a name="a-namegetextendedcharsa-getextendedchars"></a><a name="getextendedchars"></a>GetExtendedChars
Mit dieser Funktion können Sie die Anzahl von Sonderzeichen in einer Zeichenfolge abrufen.  
  
```  
inline int GetExtendedChars(LPCSTR szSrc, int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `szSrc`  
 Die Zeichenfolge, die analysiert werden.  
  
 `nSrcLen`  
 Die Länge der Zeichenfolge in Zeichen.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der erweiterten Zeichen in der Zeichenfolge, die laut [IsExtendedChar](#isextendedchar).  
  
## <a name="a-nameisextendedchara-isextendedchar"></a><a name="isextendedchar"></a>IsExtendedChar
Mit dieser Funktion können Sie herausfinden, ob ein angegebenes Zeichen ein Sonderzeichen ist (kleiner als 32, größer als 126 und kein Tabstopp-, Zeilenvorschub- oder Wagenrücklaufzeichen)  
  
```  
inline int IsExtendedChar(char ch) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *CH*  
 Die zu testende Zeichen  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn das Zeichen erweitert wird, **FALSE** andernfalls.  
  
## <a name="a-nameqencodea-qencode"></a><a name="qencode"></a>QEncode
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
 `pbSrcData`  
 Der Puffer mit den Daten codiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes der Daten, die codiert werden.  
  
 `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der codierten Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Zeichen.  
  
 `pszCharSet`  
 Der Zeichensatz, der für die Konvertierung verwendet.  
  
 *pnNumEncoded*  
 Ein Zeiger auf eine Variable, die bei der Rückgabe der Anzahl der unsicheren Zeichen enthält, die konvertiert werden musste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Das Codierungsschema "Q" wird in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqencodegetrequiredlengtha-qencodegetrequiredlength"></a><a name="qencodegetrequiredlength"></a>QEncodeGetRequiredLength 
Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.  
  
```  
inline int QEncodeGetRequiredLength(int nSrcLen, int nCharsetLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Bytes der Daten codiert werden.  
  
 `nCharsetLen`  
 Die Länge in Zeichen des Zeichensatzes, der für die Konvertierung verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erforderliche Anzahl von Zeichen für einen Puffer, der codierte Daten enthalten könnten `nSrcLen` Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Das Codierungsschema "Q" wird in RFC 2047 beschrieben ([http://www.ietf.org/rfc/rfc2047.txt](http://www.ietf.org/rfc/rfc2047.txt)).  
  
## <a name="a-nameqpdecodea-qpdecode"></a><a name="qpdecode"></a>QPDecode
Decodiert eine Zeichenfolge, die durch einen vorherigen Aufruf von quoted printable-Format wie z. B. codiert wurde [QPEncode](#qpencode).  
  
```  
inline BOOL QPDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   LPSTR szDest,  
   int* pnDestLen,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pbSrcData`  
 Der Puffer mit den Daten, die decodiert werden.  
  
 [in] `nSrcLen`  
 Die Länge in Bytes von `pbSrcData`.  
  
 [out] `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der entschlüsselte Daten.  
  
 [out] `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Bytes enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der in den Puffer geschriebenen Bytes. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes.  
  
 [in] `dwFlags`  
 Flags, die beschreiben, wie die Konvertierung erfolgt, ausgeführt werden. Finden Sie unter [ATLSMTP_QPENCODE Flags](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `TRUE` bei Erfolg bzw. `FALSE` bei einem Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Die quoted printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpdecodegetrequiredlengtha-qpdecodegetrequiredlength"></a><a name="qpdecodegetrequiredlength"></a>QPDecodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer Zeichenfolge der angegebenen Länge in einem druckbaren Format mit Anführungszeichen decodiert wurden.  
  
```  
inline int QPDecodeGetRequiredLength(int nSrcLen) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Zeichen in die codierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte erforderlichen `nSrcLen` Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Die quoted printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodea-qpencode"></a><a name="qpencode"></a>QPEncode
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
 `pbSrcData`  
 Der Puffer mit den Daten codiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes der Daten, die codiert werden.  
  
 `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der codierten Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Zeichen.  
  
 `dwFlags`  
 Flags, die beschreiben, wie die Konvertierung erfolgt, ausgeführt werden. Finden Sie unter [ATLSMTP_QPENCODE Flags](http://msdn.microsoft.com/library/6b15a3ab-8e57-49e4-8104-09b26ebb96c4).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Die quoted printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameqpencodegetrequiredlengtha-qpencodegetrequiredlength"></a><a name="qpencodegetrequiredlength"></a>QPEncodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.  
  
```  
inline int QPEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Bytes der Daten codiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erforderliche Anzahl von Zeichen für einen Puffer, der codierte Daten enthalten könnten `nSrcLen` Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Die quoted printable-Codierungsschema wird in RFC 2045 beschrieben ([http://www.ietf.org/rfc/rfc2045.txt](http://www.ietf.org/rfc/rfc2045.txt)).  
  
## <a name="a-nameuudecodea-uudecode"></a><a name="uudecode"></a>UUDecode
Decodiert eine Zeichenfolge, die Uuencoded wie z. B. durch einen vorherigen Aufruf wurde [UUEncode](#uuencode).  
  
```  
inline BOOL UUDecode(  
   BYTE* pbSrcData,  
   int nSrcLen,  
   BYTE* pbDest,  
   int* pnDestLen) throw ();  
```  
  
### <a name="parameters"></a>Parameter  
 `pbSrcData`  
 Die Zeichenfolge, die mit den Daten, die decodiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes von `pbSrcData`.  
  
 `pbDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der entschlüsselte Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Bytes enthält `pbDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der in den Puffer geschriebenen Bytes. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Implementierung Binärstreams in UUENCODE folgt der POSIX P1003.2b/D11-Spezifikation.  
  
## <a name="a-nameuudecodegetrequiredlengtha-uudecodegetrequiredlength"></a><a name="uudecodegetrequiredlength"></a>UUDecodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Bytes abrufen, der die Daten enthalten kann, die aus einer UUEncoded-Zeichenfolge der angegebenen Länge decodiert wurden.  
  
```  
inline int UUDecodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Zeichen in die codierte Zeichenfolge.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Bytes, die für einen Puffer, der eine decodierte Zeichenfolge enthalten könnte erforderlichen `nSrcLen` Zeichen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Implementierung Binärstreams in UUENCODE folgt der POSIX P1003.2b/D11-Spezifikation.  
  
## <a name="a-nameuuencodea-uuencode"></a><a name="uuencode"></a>UUEncode
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
 `pbSrcData`  
 Der Puffer mit den Daten codiert werden.  
  
 `nSrcLen`  
 Die Länge in Bytes der Daten, die codiert werden.  
  
 `szDest`  
 Vom Aufrufer reservierte Puffer zum Empfangen der codierten Daten.  
  
 `pnDestLen`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szDest`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge des Puffers in Zeichen.  
  
 *lpszFile*  
 Die Datei auf dem Header hinzugefügt werden, wenn ATLSMTP_UUENCODE_HEADER im angegebenen `dwFlags`.  
  
 `dwFlags`  
 Flags, die das Verhalten dieser Funktion steuern. Finden Sie unter [ATLSMTP_UUENCODE Flags](http://msdn.microsoft.com/library/ecb79b81-b764-4a48-a05c-a9dee6e7bbce).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Diese Implementierung Binärstreams in UUENCODE folgt der POSIX P1003.2b/D11-Spezifikation.  
  
## <a name="a-nameuuencodegetrequiredlengtha-uuencodegetrequiredlength"></a><a name="uuencodegetrequiredlength"></a>UUEncodeGetRequiredLength
Mit dieser Funktion können Sie die Größe eines Puffers in Zeichen abrufen, der eine Zeichenfolge enthalten kann, die aus Daten der angegebenen Größe codiert wurde.  
  
```  
inline int UUEncodeGetRequiredLength(int nSrcLen) throw ();  
```  
  
### <a name="parameters"></a>Parameter  
 `nSrcLen`  
 Die Anzahl der Bytes der Daten codiert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erforderliche Anzahl von Zeichen für einen Puffer, der codierte Daten enthalten könnten `nSrcLen` Bytes.  
  
### <a name="remarks"></a>Hinweise  
 Diese Implementierung Binärstreams in UUENCODE folgt der POSIX P1003.2b/D11-Spezifikation.  
  
### <a name="see-also"></a>Siehe auch  
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   
