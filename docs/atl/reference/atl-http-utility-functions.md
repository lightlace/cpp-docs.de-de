---
title: ATL-HTTP-Utility-Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
caps.latest.revision: 4
author: mikeblome
ms.author: mblome
translationtype: Machine Translation
ms.sourcegitcommit: 9ab4b38b2ba14aca2240d12fff966d36750a3229
ms.openlocfilehash: dd8b3a279148e2a5b72d96724c329e49cd5d3e5f
ms.lasthandoff: 02/24/2017

---
# <a name="atl-http-utility-functions"></a>ATL-HTTP-Hilfsfunktionen

Diese Funktionen unterstützen die Bearbeitung von URLs.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Kanonisiert eine URL, einschließlich unsicheren Zeichen sowie Leerzeichen in Escapesequenzen konvertiert.|  
|[AtlCombineUrl](#atlcombineurl)|Kombiniert eine Basis-URL und eine relative URL zu einer einzelnen kanonischen URL.|  
|[AtlEscapeUrl](#atlescapeurl)|Konvertiert alle unsichere Zeichen in Escapesequenzen.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Ruft die Standard-Portnummer, die einem bestimmten Internetprotokoll oder-Schema zugeordnet.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bestimmt, ob ein Zeichen für die Verwendung in einer URL sicher ist.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Konvertiert Escapezeichen zurück in ihre ursprünglichen Werte.|  
|[RGBToHtml](#rgbtohtml)|Konvertiert eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der den HTML-Text, den Wert der Farbe entspricht.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|

## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  

## <a name="a-nameatlcanonicalizeurla-atlcanonicalizeurl"></a><a name="atlcanonicalizeurl"></a>AtlCanonicalizeUrl
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
 Die URL für die kanonische Form gebracht werden.  
  
 `szCanonicalized`  
 Vom Aufrufer reservierten Puffer die kanonisierte URL empfangen.  
  
 `pdwMaxLength`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szCanonicalized`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer nicht einschließlich des abschließenden Zeichens Null geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge der Speicherplatz für das abschließende Nullzeichen einschließlich Puffers in Bytes.  
  
 `dwFlags`  
 Flags, die das Verhalten dieser Funktion steuern. Finden Sie unter [ATL_URL Flags](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342) erfordert aber nicht WinInet oder Internet Explorer installiert sein.  
  
### <a name="see-also"></a>Siehe auch  
 [InternetCanonicalizeUrl](http://msdn.microsoft.com/library/windows/desktop/aa384342)

 ## <a name="a-nameatlcombineurla-atlcombineurl"></a><a name="atlcombineurl"></a>AtlCombineUrl
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
 Vom Aufrufer reservierten Puffer die kanonisierte URL empfangen.  
  
 `pdwMaxLength`  
 Zeiger auf eine Variable, die die Länge in Zeichen enthält `szBuffer`. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer nicht einschließlich des abschließenden Zeichens Null geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge der Speicherplatz für das abschließende Nullzeichen einschließlich Puffers in Bytes.  
  
 `dwFlags`  
 Flags, die das Verhalten dieser Funktion steuern. Finden Sie unter [ATL_URL Flags](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCombineUrl](http://msdn.microsoft.com/library/windows/desktop/aa384355) erfordert aber nicht WinInet oder Internet Explorer installiert sein.  
  
## <a name="a-nameatlescapeurla-atlescapeurl"></a><a name="atlescapeurl"></a>AtlEscapeUrl
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
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ist, `pdwStrLen` empfängt die Anzahl der Zeichen, die in den Puffer, nicht einschließlich des abschließenden Zeichens Null geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge der Speicherplatz für das abschließende Nullzeichen einschließlich Puffers in Bytes. Bei Verwendung der Breitzeichen-Version dieser Methode `pdwStrLen` empfängt die Anzahl von Zeichen erforderlich sind, nicht die Anzahl der Bytes.  
  
 `dwMaxLength`  
 Die Größe des Puffers `lpszStringOut`.  
  
 `dwFlags`  
 Flags, die das Verhalten dieser Funktion steuern. Finden Sie unter [ATL_URL Flags](http://msdn.microsoft.com/library/76e8cc5c-4e17-4eb1-ac29-a94d5256c4a7).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
## <a name="atlgetdefaulturlport"></a> 
 Mit dieser Funktion wird die Standardportnummer abgerufen, die einem bestimmten Internetprotokoll oder -schema zugeordnet ist.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *m_nScheme*  
 Die [ATL_URL_SCHEME](atl-url-scheme-enum.md) -Wert, der das Schema für die Nummer des Ports abgerufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [ATL_URL_PORT](atl-typedefs.md#atl_url_port) dem angegebenen Schema oder ATL_URL_INVALID_PORT_NUMBER zugeordnet, wenn das Schema nicht erkannt wird.  

## <a name="a-nameatlisunsafeurlchara-atlisunsafeurlchar"></a><a name="atlisunsafeurlchar"></a>AtlIsUnsafeUrlChar
 Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 `chIn`  
 Das Zeichen, aus Sicherheitsgründen getestet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** ist das Eingabezeichen unsicher, **FALSE** andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Zeichen, die nicht in URLs verwendet werden soll, kann mit dieser Funktion getestet werden und konvertiert [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
## <a name="a-nameatlunescapeurla-atlunescapeurl"></a><a name="atlunescapeurl"></a>AtlUnescapeUrl
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
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ist, empfängt die Variable die Anzahl der Zeichen, die in den Puffer nicht einschließlich des abschließenden Zeichens Null geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge der Speicherplatz für das abschließende Nullzeichen einschließlich Puffers in Bytes.  
  
 `dwMaxLength`  
 Die Größe des Puffers `lpszStringOut`.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Kehrt die Konvertierung angewendet, indem [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="a-namergbtohtmla-rgbtohtml"></a><a name="rgbtohtml"></a>RGBToHtml
Konvertiert eine [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der den HTML-Text, den Wert der Farbe entspricht.  
  
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
 Vom Aufrufer reservierte Puffer, den Text für den HTML-Farbwert zu erhalten. Der Puffer muss Speicherplatz für mindestens 8 Zeichen einschließlich Leerzeichen für das null-Abschlusszeichen verfügen).  
  
 *nBuffer*  
 Die Größe des Puffers (einschließlich Platz für das null-Abschlusszeichen) in Bytes.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt **TRUE** bei Erfolg **FALSE** bei einem Fehler.  
  
### <a name="remarks"></a>Hinweise  
 Ein HTML-Farbwert ist ein Rautenzeichen, gefolgt von einem hexadezimalen Ziffern 6-Wert mit 2 Ziffern für den Rot-, Grün- und blauen-Komponenten der Farbe (z. B. #FFFFFF ist weiß).  
  
## <a name="a-namesystemtimetohttpdatea-systemtimetohttpdate"></a><a name="systemtimetohttpdate"></a>SystemTimeToHttpDate
Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Parameter  
 `st`  
 Die Systemzeit als eine HTTP-Zeichenfolge abgerufen werden sollen.  
  
 *strTime*  
 Ein Verweis auf eine String-Variable zu der HTTP-Empfangsadapter Datum Uhrzeit gemäß RFC 2616 ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) und RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   


