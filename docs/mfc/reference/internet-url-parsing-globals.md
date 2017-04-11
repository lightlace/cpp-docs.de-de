---
title: Analysieren von Internet-URLs und Hilfsprogramme | Microsoft Docs
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.isapi
dev_langs:
- C++
helpviewer_keywords:
- parsing, URLs
- URLs, parsing
ms.assetid: 46c6384f-e4a6-4dbd-9196-219c19040ec5
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: 947ef992d58895e4638d9ffe77fca973cea8eada
ms.lasthandoff: 04/04/2017

---
# <a name="internet-url-parsing-globals-and-helpers"></a>Analysieren von Internet-URLs und -Hilfsprogramme
Wenn ein Client eine Abfrage an den IIS-Server sendet, können Sie eine der Analyse von Globals URLs zum Extrahieren von Informationen über den Client verwenden. Die Hilfsfunktionen bieten andere Internetfunktionalität.
  
## <a name="internet-url-parsing-globals"></a>Globale Variablen zur Analyse von Internet-URLs  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten.|  
|[AfxParseURLEx](#afxparseurlex)|Analysiert eine URL-Zeichenfolge und gibt den Typ der Dienst und seine Komponenten, sowie den Benutzernamen und Ihr Kennwort eingeben.|  

## <a name="other-internet-helpers"></a>Andere Internet-Hilfsprogramme
|||
|-|-|
|[AfxThrowInternetException](#afxthrowinternetexception)|Löst eine Ausnahme im Zusammenhang mit der Internet-Verbindung.|
|[AfxGetInternetHandleType](#afxgetinternethandletype)|Bestimmt den Typ eines Internet-Handles.|
  
##  <a name="afxparseurl"></a>AfxParseURL  
 Diese globale dient [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURL(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort); 
```  
  
### <a name="parameters"></a>Parameter  
 *pstrURL*  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL, die analysiert werden.  
  
 `dwServiceType`  
 Gibt den Typ des Internet-Diensts an. Folgende Werte sind möglich:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Das erste Segment der URL, die nach der Diensttyp.  
  
 `strObject`  
 Ein Objekt, das auf die URL verweist (möglicherweise leere).  
  
 `nPort`  
 Bestimmt, von dem Server oder Objekt Teile der URL, soweit vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die URL wurde erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keinen bekannten Internet Diensttyp.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten.  
  
 Beispielsweise `AfxParseURL` URLs des Formulars analysiert **Service://server/dir/dir/object.ext:port** und gibt seine Komponenten wie folgt gespeichert:  
  
 `strServer`"Server" ==  
  
 `strObject`== "/ dir/dir/object/object.ext"  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxinet.h  
  
##  <a name="afxparseurlex"></a>AfxParseURLEx  
 Diese globale Funktion ist die erweiterte Version des [AfxParseURL](#afxparseurl) und werden in [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
```   
BOOL AFXAPI AfxParseURLEx(
    LPCTSTR pstrURL,  
    DWORD& dwServiceType,  
    CString& strServer,  
    CString& strObject,  
    INTERNET_PORT& nPort,  
    CString& strUsername,  
    CString& strPassword,  
    DWORD dwFlags = 0); 
```  
  
### <a name="parameters"></a>Parameter  
 *pstrURL*  
 Ein Zeiger auf eine Zeichenfolge, enthält die URL, die analysiert werden.  
  
 `dwServiceType`  
 Gibt den Typ des Internet-Diensts an. Folgende Werte sind möglich:  
  
-   AFX_INET_SERVICE_FTP  
  
-   AFX_INET_SERVICE_HTTP  
  
-   AFX_INET_SERVICE_HTTPS  
  
-   AFX_INET_SERVICE_GOPHER  
  
-   AFX_INET_SERVICE_FILE  
  
-   AFX_INET_SERVICE_MAILTO  
  
-   AFX_INET_SERVICE_NEWS  
  
-   AFX_INET_SERVICE_NNTP  
  
-   AFX_INET_SERVICE_TELNET  
  
-   AFX_INET_SERVICE_WAIS  
  
-   AFX_INET_SERVICE_MID  
  
-   AFX_INET_SERVICE_CID  
  
-   AFX_INET_SERVICE_PROSPERO  
  
-   AFX_INET_SERVICE_AFS  
  
-   AFX_INET_SERVICE_UNK  
  
 `strServer`  
 Das erste Segment der URL, die nach der Diensttyp.  
  
 `strObject`  
 Ein Objekt, das auf die URL verweist (möglicherweise leere).  
  
 `nPort`  
 Bestimmt, von dem Server oder Objekt Teile der URL, soweit vorhanden.  
  
 *strUsername*  
 Ein Verweis auf ein `CString` Objekt, das den Namen des Benutzers enthält.  
  
 `strPassword`  
 Ein Verweis auf eine `CString` -Objekt, das Kennwort des Benutzers enthält.  
  
 `dwFlags`  
 Die Flags, wie die URL analysiert steuern. Eine Kombination der folgenden Werte ist möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**ICU_DECODE**|% XX Escape-Sequenzen in Zeichen konvertiert.|  
|**ICU_NO_ENCODE**|Unsichere Zeichen in escape-Sequenz nicht konvertiert werden.|  
|**ICU_NO_META**|Bauen Sie nicht Meta-Sequenzen (z. B. "\". und "\...") von der URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Codieren Sie nur aus Leerzeichen bestehen.|  
|**ICU_BROWSER_MODE**|Nicht codieren oder Decodieren von Zeichen nach "#" oder ", und entfernen Sie nicht nachgestellte Leerzeichen nach". Wenn dieser Wert nicht angegeben wird, wird die gesamte URL codiert, und nachfolgendes Leerzeichen entfernt.|  
  
 Bei Verwendung von MFC-Standard, d. h. keine Flags, die Funktion konvertiert alle unsicheren Zeichen sowie Meta-Sequenzen (z. B. \\., \.., und \\...) als Escapesequenz für Sequenzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die URL wurde erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keinen bekannten Internet Diensttyp.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten sowie Name und Kennwort des Benutzers bereitstellen. Die Flags geben an, wie unsichere Zeichen behandelt werden.  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  

### <a name="requirements"></a>Anforderungen  
  **Header** afxinet.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
 
## <a name="afxgetinternethandletype"></a>AfxGetInternetHandleType
Verwenden Sie diese globale Funktion zum Bestimmen des Typs eines Internet-Handles.  
   
### <a name="syntax"></a>Syntax  
  ```
DWORD AFXAPI AfxGetInternetHandleType(  HINTERNET hQuery );  
```
### <a name="parameters"></a>Parameter  
 `hQuery`  
 Ein Handle für eine Internet-Abfrage.  
   
### <a name="return-value"></a>Rückgabewert  
 Alle von der Internet-Diensttypen durch WININET definiert. H. Finden Sie im Abschnitt "Hinweise" eine Liste dieser Internetdienste aus. Wenn das Handle NULL ist oder nicht erkannt wird, gibt die Funktion AFX_INET_SERVICE_UNK zurück.  
   
### <a name="remarks"></a>Hinweise  
 Die folgende Liste enthält mögliche Internet Typen zurückgegebenes `AfxGetInternetHandleType`.  
  
-   INTERNET_HANDLE_TYPE_INTERNET  
  
-   INTERNET_HANDLE_TYPE_CONNECT_FTP  
  
-   INTERNET_HANDLE_TYPE_CONNECT_GOPHER  
  
-   INTERNET_HANDLE_TYPE_CONNECT_HTTP  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND  
  
-   INTERNET_HANDLE_TYPE_FTP_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE  
  
-   INTERNET_HANDLE_TYPE_FTP_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FIND_HTML  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE  
  
-   INTERNET_HANDLE_TYPE_GOPHER_FILE_HTML  
  
-   INTERNET_HANDLE_TYPE_HTTP_REQUEST  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [AfxParseURL](internet-url-parsing-globals.md#afxparseurl)
 
## <a name="afxthrowinternetexception"></a>AfxThrowInternetException
Eine Internet-Ausnahme ausgelöst.  
   
### <a name="syntax"></a>Syntax    
```
   void AFXAPI AfxThrowInternetException(  DWORD dwContext,  DWORD dwError = 0 );  
```
### <a name="parameters"></a>Parameter  
 `dwContext`  
 Der Kontextbezeichner für den Vorgang, der den Fehler verursacht hat. Der Standardwert von `dwContext` ursprünglich im angegebenen [CInternetSession](cinternetsession-class.md) und an Sie übergeben [CInternetConnection](cinternetconnection-class.md)- und [CInternetFile](cinternetfile-class.md)-abgeleitete Klassen. Für bestimmte Vorgänge, die für eine Verbindung oder eine Datei ausgeführt werden, überschreiben Sie in der Regel die Standardeinstellung für die ein `dwContext` Ihrer Wahl. Dieser Wert wird dann an zurückgegeben [CInternetSession:: OnStatusCallback](cinternetsession-class.md#onstatuscallback) um den spezifischen Status des Vorgangs zu identifizieren. 
  
 `dwError`  
 Der Fehler, der die Ausnahme verursacht hat.  
   
### <a name="remarks"></a>Hinweise  
 Sie sind verantwortlich für die Ursache anhand der Betriebssystem-Fehlercode ermitteln.  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)   
 [CInternetException-Klasse](cinternetexception-class.md)   
 [THROW](#throw)
 


