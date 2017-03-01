---
title: "Globals für das Analysieren von Internet-URL | Microsoft-Dokumentation"
ms.custom: 
ms.date: 11/04/2016
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 3aec259acae2f5e9c9b65ac4e5c898ca57ff3d52
ms.lasthandoff: 02/24/2017

---
# <a name="internet-url-parsing-globals"></a>Globale Variablen zur Analyse von Internet-URLs
Wenn ein Client eine Abfrage an den IIS-Server sendet, können Sie eine der URLs analysieren Globals zum Extrahieren von Informationen über den Client verwenden.  
  
### <a name="internet-url-parsing-globals"></a>Globale Variablen zur Analyse von Internet-URLs  
  
|||  
|-|-|  
|[AfxParseURL](#afxparseurl)|Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten.|  
|[AfxParseURLEx](#afxparseurlex)|Analysiert eine URL-Zeichenfolge und gibt den Typ der Dienst und seine Komponenten sowie den Benutzernamen und das Kennwort bereitstellen.|  
  
##  <a name="a-nameafxparseurla--afxparseurl"></a><a name="afxparseurl"></a>AfxParseURL  
 Diese globale werden in [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
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
 Ein Zeiger auf eine Zeichenfolge mit der URL, die analysiert werden.  
  
 `dwServiceType`  
 Gibt den Typ des Internet-Dienst an. Folgende Werte sind möglich:  
  
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
 Das erste Segment der URL nach der Diensttyp.  
  
 `strObject`  
 Ein Objekt, das an die URL verweist (möglicherweise leere).  
  
 `nPort`  
 Durch den Server oder Objekt Teile der URL bestimmt, soweit vorhanden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die URL erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keine bekannten Internet Service Typ.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten.  
  
 Beispielsweise `AfxParseURL` analysiert URLs in der Form **Service://server/dir/dir/object.ext:port** und gibt seine Komponenten wie folgt gespeichert:  
  
 `strServer`== "Server"  
  
 `strObject`== "/ dir/dir/object/object.ext"  
  
 `nPort`== #port  
  
 `dwServiceType`== #service  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxinet.h  
  
##  <a name="a-nameafxparseurlexa--afxparseurlex"></a><a name="afxparseurlex"></a>AfxParseURLEx  
 Diese globale Funktion ist die erweiterte Version des [AfxParseURL](#afxparseurl) und im [OpenURL](../../mfc/reference/cinternetsession-class.md#openurl).  
  
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
 Ein Zeiger auf eine Zeichenfolge mit der URL, die analysiert werden.  
  
 `dwServiceType`  
 Gibt den Typ des Internet-Dienst an. Folgende Werte sind möglich:  
  
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
 Das erste Segment der URL nach der Diensttyp.  
  
 `strObject`  
 Ein Objekt, das an die URL verweist (möglicherweise leere).  
  
 `nPort`  
 Durch den Server oder Objekt Teile der URL bestimmt, soweit vorhanden.  
  
 *"strUserName"*  
 Ein Verweis auf ein `CString` Objekt, das den Namen des Benutzers enthält.  
  
 `strPassword`  
 Ein Verweis auf ein `CString` -Objekt, das Kennwort des Benutzers enthält.  
  
 `dwFlags`  
 Die Flags steuern die URL zu analysieren. Eine Kombination der folgenden Werte sind möglich:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**ICU_DECODE**|Konvertieren Sie % XX Escape-Sequenzen in Zeichen.|  
|**ICU_NO_ENCODE**|Unsichere Zeichen in escape-Sequenz nicht konvertiert werden.|  
|**ICU_NO_META**|Entfernen Sie nicht Meta-Sequenzen (z. B. "\." und "\"..) von der URL.|  
|**ICU_ENCODE_SPACES_ONLY**|Codieren Sie nur aus Leerzeichen bestehen.|  
|**ICU_BROWSER_MODE**|Nicht codieren oder Decodieren von Zeichen nach dem "#" oder ", und entfernen Sie nicht nachgestellte Leerzeichen nach ''. Wenn dieser Wert nicht angegeben wird, wird die gesamte URL codiert, und nachfolgendes Leerzeichen werden entfernt.|  
  
 Bei Verwendung von MFC-Standard, d. h. keine Flags, die Funktion konvertiert alle unsicheren Zeichen sowie Meta-Sequenzen (wie z. B. \\., \..., und \\...), escape-Sequenzen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die URL erfolgreich analysiert wurde; andernfalls 0, wenn er leer ist oder enthält keine bekannten Internet Service Typ.  
  
### <a name="remarks"></a>Hinweise  
 Analysiert eine URL-Zeichenfolge und gibt den Typ des Diensts und seiner Komponenten sowie Namen und das Kennwort des Benutzers bereitstellen. Die Flags geben an, wie unsichere Zeichen behandelt werden.  
  
> [!NOTE]
>  Um diese Funktion aufzurufen, muss das Projekt CFILEFIND umfassen. H.  

### <a name="requirements"></a>Anforderungen  
  **Header** afxinet.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)

