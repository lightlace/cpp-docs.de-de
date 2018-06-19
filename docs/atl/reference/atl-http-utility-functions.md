---
title: ATL-HTTP-Hilfsfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 476ca29de5a44e8ebb20d53ec0b88834c7b03eea
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363783"
---
# <a name="atl-http-utility-functions"></a>ATL-HTTP-Hilfsfunktionen

Diese Funktionen unterstützen die Bearbeitung von URLs.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Kanonisiert eine URL inklusive unsicheren Zeichen sowie Leerzeichen in Escapesequenzen konvertiert.|  
|[AtlCombineUrl](#atlcombineurl)|Kombiniert eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL an.|  
|[AtlEscapeUrl](#atlescapeurl)|Konvertiert alle unsichere Zeichen in Escapesequenzen.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Ruft die Standard-Portnummer, die einem bestimmten Internetprotokoll oder-Schema zugeordnet.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bestimmt, ob ein Zeichen für die Verwendung in einer URL sicher ist.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Konvertiert das Escapezeichen zurück in ihre ursprünglichen Werte.|  
|[RGBToHtml](#rgbtohtml)|Konvertiert eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert in den entsprechenden auf diesem Farbwert HTML-Text.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|

## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  

## <a name="atlcanonicalizeurl"></a> AtlCanonicalizeUrl
Mit dieser Funktion wird eine URL kanonisiert, wobei unsichere Zeichen und Leerzeichen in Escapesequenzen konvertiert werden.  
  
```    
inline BOOL AtlCanonicalizeUrl(  
   LPCTSTR szUrl,  
   LPTSTR szCanonicalized,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `szUrl`  
 Die URL, die in kanonische Form gebracht werden.  
  
 `szCanonicalized`  
 Vom Aufrufer reservierte Puffer zum Empfangen der kanonisierten URL.  
  
 `pdwMaxLength`  
 Zeiger auf eine Variable, die die Länge in Zeichen von enthält `szCanonicalized`. Wenn die Funktion erfolgreich ausgeführt wird, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, empfängt die Variable die erforderliche Länge in Byte des Puffers, einschließlich Platz für das abschließende Nullzeichen.  
  
 `dwFlags`  
 ATL_URL-Flags, die Steuerung des Verhaltens dieser Funktion. 

- `ATL_URL_BROWSER_MODE` Nicht codieren oder Decodieren von Zeichen nach "#" oder "?", und wird nicht entfernt nachgestellte Leerzeichen nach "?". Wenn dieser Wert nicht angegeben wird, wird die gesamte URL codiert, und nachfolgendes Leerzeichen entfernt.
- `ATL_URL_DECODE` Konvertiert alle % XX Sequenzen und Zeichen, Escapesequenzen, bevor die URL analysiert wird.
- `ATL_URL_ENCODE_PERCENT` Codiert alle Prozentzeichen gefunden. Standardmäßig werden die Prozentzeichen nicht codiert.
- `ATL_URL_ENCODE_SPACES_ONLY` Codiert nur aus Leerzeichen bestehen.
- `ATL_URL_ESCAPE` Konvertiert alle Escapezeichen ("% XX") auf den entsprechenden Zeichen.
- `ATL_URL_NO_ENCODE` Keine unsichere Zeichen in Escapesequenzen konvertiert werden.
- `ATL_URL_NO_META` Entfernt Metadaten Sequenzen nicht (wie z. B. "."und"..") aus der URL. 
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) jedoch keine zu installierenden WinInet oder der Internet Explorer erforderlich ist.  
  
### <a name="see-also"></a>Siehe auch  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="atlcombineurl"></a> AtlCombineUrl
 Mit dieser Funktion wird eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL zusammengefasst.  
  
```    
inline BOOL AtlCombineUrl(  
   LPCTSTR szBaseUrl,  
   LPCTSTR szRelativeUrl,  
   LPTSTR szBuffer,  
   DWORD* pdwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *szBaseUrl*  
 Die Basis-URL.  
  
 *szRelativeUrl*  
 Die URL relativ zum Basis-URL.  
  
 `szBuffer`  
 Vom Aufrufer reservierte Puffer zum Empfangen der kanonisierten URL.  
  
 `pdwMaxLength`  
 Zeiger auf eine Variable, die die Länge in Zeichen von enthält `szBuffer`. Wenn die Funktion erfolgreich ausgeführt wird, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, empfängt die Variable die erforderliche Länge in Byte des Puffers, einschließlich Platz für das abschließende Nullzeichen.  
  
 `dwFlags`  
 Flags, die Steuerung des Verhaltens dieser Funktion. Finden Sie unter [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) jedoch keine zu installierenden WinInet oder der Internet Explorer erforderlich ist.  
  
## <a name="atlescapeurl"></a> AtlEscapeUrl
 Mit dieser Funktion werden alle unsicheren Zeichen in Escapesequenzen konvertiert.  
  
```    
inline BOOL AtlEscapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
   
inline BOOL AtlEscapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   DWORD* pdwStrLen,  
   DWORD dwMaxLength,  
   DWORD dwFlags = 0) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszStringIn`  
 Die URL, die konvertiert werden.  
  
 `lpszStringOut`  
 Vom Aufrufer reservierte Puffer, der der konvertierte URL geschrieben wird.  
  
 `pdwStrLen`  
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ausgeführt wird, `pdwStrLen` empfängt die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, empfängt die Variable die erforderliche Länge in Byte des Puffers, einschließlich Platz für das abschließende Nullzeichen. Bei Verwendung der Breitzeichen-Version dieser Methode `pdwStrLen` empfängt die Anzahl von Zeichen erforderlich sind, nicht die Anzahl von Bytes.  
  
 `dwMaxLength`  
 Die Größe des Puffers `lpszStringOut`.  
  
 `dwFlags`  
 ATL_URL-Flags, die Steuerung des Verhaltens dieser Funktion. Finden Sie unter [ATLCanonicalizeUrl](#atlcanonicalizeurl) mögliche Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
## <a name="atlgetdefaulturlport"></a> 
 Mit dieser Funktion wird die Standardportnummer abgerufen, die einem bestimmten Internetprotokoll oder -schema zugeordnet ist.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *m_nScheme*  
 Die [ATL_URL_SCHEME](atl-url-scheme-enum.md) -Wert, der das Schema für die Sie die Nummer des Ports abrufen möchten.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [ATL_URL_PORT](atl-typedefs.md#atl_url_port) dem angegebenen Schema oder ATL_URL_INVALID_PORT_NUMBER zugeordnet, wenn das Schema nicht erkannt wird.  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `chIn`  
 Das Zeichen auf typsicherheit geprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** ist das eingegebene Zeichen unsicher, **"false"** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zeichen, die nicht in URLs verwendet werden sollte mit dieser Funktion getestet werden können und mit konvertiert [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="atlunescapeurl"></a> AtlUnescapeUrl
 Mit dieser Funktion können Sie Escapezeichen zurück in ihre ursprünglichen Werte konvertieren.  
  
```    
inline BOOL AtlUnescapeUrl(  
   LPCSTR szStringIn,  
   LPSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  

inline BOOL AtlUnescapeUrl(  
   LPCWSTR szStringIn,  
   LPWSTR szStringOut,  
   LPDWORD pdwStrLen,  
   DWORD dwMaxLength) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `lpszStringIn`  
 Die URL, die konvertiert werden.  
  
 `lpszStringOut`  
 Vom Aufrufer reservierte Puffer, der der konvertierte URL geschrieben wird.  
  
 `pdwStrLen`  
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ausgeführt wird, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, empfängt die Variable die erforderliche Länge in Byte des Puffers, einschließlich Platz für das abschließende Nullzeichen.  
  
 `dwMaxLength`  
 Die Größe des Puffers `lpszStringOut`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Kehrt den Konvertierungsprozess angewendet, indem [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a> RGBToHtml
Konvertiert eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert in den entsprechenden auf diesem Farbwert HTML-Text.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Parameter  
 `color`  
 Ein Wert für den RGB-Farbe.  
  
 `pbOut`  
 Vom Aufrufer reservierte Puffer zum Empfangen des Texts für den HTML-Farbwert. Der Puffer muss Speicherplatz für mindestens 8 Zeichen einschließlich Leerzeichen für das Nullabschlusszeichen aufweisen).  
  
 *nBuffer*  
 Die Größe des Puffers (einschließlich Platz für den null-Terminator) in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **"true"** bei Erfolg **"false"** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein HTML-Farbwert ist ein Nummernzeichen gefolgt von einem hexadezimalen Ziffern 6-Wert mit 2 Ziffern für den Rot-, Grün- und blauen-Komponenten der Farbe (z. B. #FFFFFF ist weiß).  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Parameter  
 `st`  
 Die Systemzeit als eine HTTP-Formatzeichenfolge abgerufen werden soll.  
  
 *strTime*  
 Ein Verweis auf eine Zeichenfolgenvariable, die HTTP Datum-Zeit empfangen, wie in RFC 2616 definiert ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) und RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   

