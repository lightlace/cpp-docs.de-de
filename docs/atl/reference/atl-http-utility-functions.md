---
title: ATL HTTP-Hilfsfunktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 4db57ef2-31fa-4696-bbeb-79a9035033ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 224f4d78aec432a27b2a0258d0d6b3d4a8f2174d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209507"
---
# <a name="atl-http-utility-functions"></a>ATL HTTP-Hilfsfunktionen

Diese Funktionen unterstützen die Bearbeitung von URLs.

|||  
|-|-|  
|[AtlCanonicalizeUrl](#atlcanonicalizeurl)|Kanonisiert eine URL, einschließlich unsicheren Zeichen sowie Leerzeichen in Escapesequenzen konvertiert.|  
|[AtlCombineUrl](#atlcombineurl)|Kombiniert eine Basis-URL und eine relative URL in einer einzelnen kanonischen URL an.|  
|[AtlEscapeUrl](#atlescapeurl)|Konvertiert alle unsichere Zeichen in Escapesequenzen.|  
|[AtlGetDefaultUrlPort](#atlgetdefaulturlport)|Ruft die Standard-Portnummer, die einem bestimmten Internetprotokoll oder-Schema zugeordnet.|  
|[AtlIsUnsafeUrlChar](#atlisunsafeurlchar)|Bestimmt, ob ein Zeichen für die Verwendung in einer URL sicher ist.|  
|[AtlUnescapeUrl](#atlunescapeurl)|Konvertiert Escapezeichen wieder auf ihre ursprünglichen Werte.|  
|[RGBToHtml](#rgbtohtml)|Konvertiert eine [COLORREF](/windows/desktop/gdi/colorref) Wert, der HTML-Text, dieser Wert entspricht.|
|[SystemTimeToHttpDate](#systemtimetohttpdate)|Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.|

## <a name="requirements"></a>Anforderungen  
 **Header:** "atlutil.h"  

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
 *szUrl*  
 Die URL, die in kanonische Form gebracht werden.  
  
 *szCanonicalized*  
 Vom Aufrufer reservierte Puffer zum Empfangen von der vereinheitlichten URL.  
  
 *pdwMaxLength*  
 Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzCanonicalized*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Bytes im Puffer, einschließlich des Speicherplatzes für das abschließende Nullzeichen.  
  
 *dwFlags*  
 ATL_URL-Flags, die Steuerung des Verhaltens dieser Funktion. 

- ATL_URL_BROWSER_MODE nicht codieren oder Decodieren von Zeichen nach "#" oder "?", und wird nicht entfernt nachgestellte Leerzeichen nach "?". Wenn dieser Wert nicht angegeben ist, wird die gesamte URL codiert und nachgestellte Leerzeichen entfernt.
- ATL_URL_DECODE konvertiert alle % XX Sequenzen in Zeichen, einschließlich der Escape-Sequenzen, bevor die URL analysiert wird.
- ATL_URL_ENCODE_PERCENT codiert werden alle Prozentzeichen gefunden. Standardmäßig werden die Prozentzeichen nicht codiert.
- ATL_URL_ENCODE_SPACES_ONLY codiert Leerzeichen.
- ATL_URL_ESCAPE konvertiert alle escape-Zeichensequenzen (% XX) in ihre entsprechenden Zeichen.
- ATL_URL_NO_ENCODE ist, werden nicht unsichere Zeichen in Escapesequenzen konvertiert.
- Meta-Sequenzen ATL_URL_NO_META wird nicht entfernt werden (z. B. "."und"..") aus der URL. 
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla) erfordert aber keine WinInet oder Internet Explorer installiert sein.  
  
### <a name="see-also"></a>Siehe auch  
 [InternetCanonicalizeUrl](/windows/desktop/api/wininet/nf-wininet-internetcanonicalizeurla)

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
  
 *szBuffer*  
 Vom Aufrufer reservierte Puffer zum Empfangen von der vereinheitlichten URL.  
  
 *pdwMaxLength*  
 Zeiger auf eine Variable, die die Länge in Zeichen des enthält *SzBuffer*. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Bytes im Puffer, einschließlich des Speicherplatzes für das abschließende Nullzeichen.  
  
 *dwFlags*  
 Flags, die Steuerung des Verhaltens dieser Funktion. Finden Sie unter [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
### <a name="remarks"></a>Hinweise  
 Verhält sich wie die aktuelle Version des [InternetCombineUrl](/windows/desktop/api/wininet/nf-wininet-internetcombineurla) erfordert aber keine WinInet oder Internet Explorer installiert sein.  
  
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
 *lpszStringIn*  
 Die URL, die konvertiert werden.  
  
 *lpszStringOut*  
 Vom Aufrufer reservierte Puffer, der die konvertierte URL geschrieben wird.  
  
 *pdwStrLen*  
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ist, *PdwStrLen* empfängt die Anzahl von Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Bytes im Puffer, einschließlich des Speicherplatzes für das abschließende Nullzeichen. Bei Verwendung der Breitzeichen-Version von dieser Methode *PdwStrLen* empfängt die Anzahl von Zeichen erforderlich sind, nicht die Anzahl von Bytes.  
  
 *dwMaxLength*  
 Die Größe des Puffers *LpszStringOut*.  
  
 *dwFlags*  
 ATL_URL-Flags, die Steuerung des Verhaltens dieser Funktion. Finden Sie unter [ATLCanonicalizeUrl](#atlcanonicalizeurl) mögliche Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
## <a name="atlgetdefaulturlport"></a> AtlGetDefaultUrlPort
 Mit dieser Funktion wird die Standardportnummer abgerufen, die einem bestimmten Internetprotokoll oder -schema zugeordnet ist.  
  
```  
inline ATL_URL_PORT AtlGetDefaultUrlPort(ATL_URL_SCHEME m_nScheme) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *m_nScheme*  
 Die [ATL_URL_SCHEME](atl-url-scheme-enum.md) -Wert, der das Schema für die Nummer des Ports abgerufen werden sollen.  
  
### <a name="return-value"></a>Rückgabewert  
 Die [ATL_URL_PORT](atl-typedefs.md#atl_url_port) der Angaben für Schema oder ATL_URL_INVALID_PORT_NUMBER zugeordnet, wenn das Schema nicht erkannt wird.  

## <a name="atlisunsafeurlchar"></a> AtlIsUnsafeUrlChar
 Mit dieser Funktion finden Sie heraus, ob die Verwendung eines bestimmten Zeichens in einer URL sicher ist.  
  
```  
inline BOOL AtlIsUnsafeUrlChar(char chIn) throw();  
```  
  
### <a name="parameters"></a>Parameter  
 *chIn*  
 Das Zeichen, die Sicherheit überprüft werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, wenn das Eingabezeichen unsicher, andernfalls FALSE ist.  
  
### <a name="remarks"></a>Hinweise  
 Zeichen, die nicht in URLs verwendet werden soll, kann mit dieser Funktion getestet werden, und mit konvertiert [AtlCanonicalizeUrl](#atlcanonicalizeurl).  
  
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
 *lpszStringIn*  
 Die URL, die konvertiert werden.  
  
 *lpszStringOut*  
 Vom Aufrufer reservierte Puffer, der die konvertierte URL geschrieben wird.  
  
 *pdwStrLen*  
 Zeiger auf ein DWORD-Variable. Wenn die Funktion erfolgreich ist, erhält die Variable die Anzahl der Zeichen, die in den Puffer, einschließlich des abschließenden Null-Zeichens geschrieben. Wenn die Funktion fehlschlägt, erhält die Variable die erforderliche Länge in Bytes im Puffer, einschließlich des Speicherplatzes für das abschließende Nullzeichen.  
  
 *dwMaxLength*  
 Die Größe des Puffers *LpszStringOut*.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
### <a name="remarks"></a>Hinweise  
 Kehrt den Konvertierungsprozess angewendet, indem [AtlEscapeUrl](#atlescapeurl).  
  
## <a name="rgbtohtml"></a> RGBToHtml
Konvertiert eine [COLORREF](/windows/desktop/gdi/colorref) Wert, der HTML-Text, dieser Wert entspricht.  
  
```  
bool inline RGBToHtml(  
   COLORREF color,  
   LPTSTR pbOut,  
   long nBuffer);  
```  
  
### <a name="parameters"></a>Parameter  
 *Farbe*  
 Ein RGB-Farbwert.  
  
 *pbOut*  
 Vom Aufrufer reservierte Puffer zum Empfangen von des Texts für den Wert des HTML-Farbe. Der Puffer muss für mindestens 8 Zeichen umfassen, einschließlich des Speicherplatzes für die null-Terminator verfügbar sein).  
  
 *nBuffer*  
 Die Größe in Bytes im Puffer (einschließlich des Speicherplatzes für die null-Abschlusszeichen).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "true" bei Erfolg bei "false".  
  
### <a name="remarks"></a>Hinweise  
 Ein HTML-Farbwert ist ein Rautenzeichen, gefolgt von einem 6 Ziffern hexadezimal-Wert mit 2 Ziffern für jede der Komponenten der Farbe roten, grünen und blauen (z. B. #FFFFFF ist weiß).  
  
## <a name="systemtimetohttpdate"></a> SystemTimeToHttpDate
Mit dieser Funktion konvertieren Sie die Systemzeit in eine Zeichenfolge, deren Format sich für die Verwendung in HTTP-Headern eignet.  
  
```  
inline void SystemTimeToHttpDate( 
   const SYSTEMTIME& st,  
   CStringA& strTime);  
```  
  
### <a name="parameters"></a>Parameter  
 *St*  
 Die Systemzeit als eine HTTP-Formatzeichenfolge abgerufen werden sollen.  
  
 *strTime*  
 Ein Verweis auf eine Zeichenfolgenvariable, in der HTTP-Empfangsadapter Datum Uhrzeit wie in RFC 2616 definiert ([http://www.ietf.org/rfc/rfc2616.txt](http://www.ietf.org/rfc/rfc2616.txt)) und RFC 1123 ([http://www.ietf.org/rfc/rfc1123.txt](http://www.ietf.org/rfc/rfc1123.txt)).  
  
## <a name="see-also"></a>Siehe auch  
 [Konzepte](../../atl/active-template-library-atl-concepts.md)   
 [ATL-COM-Desktop-Komponenten](../../atl/atl-com-desktop-components.md)   

