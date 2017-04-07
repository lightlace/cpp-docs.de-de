---
title: CUrl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CUrl
- ATLUTIL/ATL::CUrl
- ATLUTIL/ATL::CUrl::CUrl
- ATLUTIL/ATL::CUrl::Canonicalize
- ATLUTIL/ATL::CUrl::Clear
- ATLUTIL/ATL::CUrl::CrackUrl
- ATLUTIL/ATL::CUrl::CreateUrl
- ATLUTIL/ATL::CUrl::GetExtraInfo
- ATLUTIL/ATL::CUrl::GetExtraInfoLength
- ATLUTIL/ATL::CUrl::GetHostName
- ATLUTIL/ATL::CUrl::GetHostNameLength
- ATLUTIL/ATL::CUrl::GetPassword
- ATLUTIL/ATL::CUrl::GetPasswordLength
- ATLUTIL/ATL::CUrl::GetPortNumber
- ATLUTIL/ATL::CUrl::GetScheme
- ATLUTIL/ATL::CUrl::GetSchemeName
- ATLUTIL/ATL::CUrl::GetSchemeNameLength
- ATLUTIL/ATL::CUrl::GetUrlLength
- ATLUTIL/ATL::CUrl::GetUrlPath
- ATLUTIL/ATL::CUrl::GetUrlPathLength
- ATLUTIL/ATL::CUrl::GetUserName
- ATLUTIL/ATL::CUrl::GetUserNameLength
- ATLUTIL/ATL::CUrl::SetExtraInfo
- ATLUTIL/ATL::CUrl::SetHostName
- ATLUTIL/ATL::CUrl::SetPassword
- ATLUTIL/ATL::CUrl::SetPortNumber
- ATLUTIL/ATL::CUrl::SetScheme
- ATLUTIL/ATL::CUrl::SetSchemeName
- ATLUTIL/ATL::CUrl::SetUrlPath
- ATLUTIL/ATL::CUrl::SetUserName
dev_langs:
- C++
helpviewer_keywords:
- CUrl class
ms.assetid: b3894d34-47b9-4961-9719-4197153793da
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: eda63a8dc704dd471d8078b848d95fc9fb44f58f
ms.lasthandoff: 02/24/2017

---
# <a name="curl-class"></a>CUrl-Klasse
Diese Klasse stellt eine URL. Damit können Sie jedes Element der URL unabhängig von den anderen bearbeiten, ob eine vorhandene URL Analyse Zeichenfolge oder eine Zeichenfolge von Grund auf neu erstellen.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member werden nicht in Anwendungen verwendet, die in der Windows-Runtime ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```
class CUrl
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUrl::CUrl](#curl)|Der Konstruktor.|  
|[CUrl:: ~ CUrl](#dtor)|Der Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUrl::Canonicalize](#canonicalize)|Rufen Sie diese Methode, um die URL-Zeichenfolge in die kanonische Form zu konvertieren.|  
|[CUrl::Clear](#clear)|Rufen Sie diese Methode, um alle Felder URL deaktivieren.|  
|[CUrl::CrackUrl](#crackurl)|Rufen Sie diese Methode zum Decodieren und analysieren die URL ein.|  
|[CUrl::CreateUrl](#createurl)|Rufen Sie diese Methode, um die URL zu erstellen.|  
|[CUrl::GetExtraInfo](#getextrainfo)|Rufen Sie diese Methode, um zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL.|  
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Rufen Sie diese Methode zum Abrufen der Länge eines der zusätzlichen Informationen (z. B. *Text* oder # *Text*) aus der URL abgerufen.|  
|[CUrl::GetHostName](#gethostname)|Rufen Sie diese Methode, um den Hostnamen aus der URL abzurufen.|  
|[CUrl::GetHostNameLength](#gethostnamelength)|Rufen Sie diese Methode, um die Länge des Hostnamens abgerufen werden.|  
|[CUrl::GetPassword](#getpassword)|Rufen Sie diese Methode, um das Kennwort aus der URL abzurufen.|  
|[CUrl::GetPasswordLength](#getpasswordlength)|Rufen Sie diese Methode, um die Länge des Kennworts abzurufen.|  
|[CUrl::GetPortNumber](#getportnumber)|Rufen Sie diese Methode, um die Portnummer im Hinblick auf ATL_URL_PORT abzurufen.|  
|[CUrl::GetScheme](#getscheme)|Rufen Sie diese Methode, um das URL-Schema abgerufen.|  
|[CUrl::GetSchemeName](#getschemename)|Rufen Sie diese Methode, um den URL-Schema-Namen abrufen.|  
|[CUrl::GetSchemeNameLength](#getschemenamelength)|Rufen Sie diese Methode, um die Länge der URL-Schema-Namen abrufen.|  
|[CUrl::GetUrlLength](#geturllength)|Rufen Sie diese Methode zum Abrufen der URL-Länge.|  
|[CUrl::GetUrlPath](#geturlpath)|Rufen Sie diese Methode, um den URL-Pfad abzurufen.|  
|[CUrl::GetUrlPathLength](#geturlpathlength)|Rufen Sie diese Methode, um die Länge der URL-Pfad abzurufen.|  
|[CUrl::GetUserName](#getusername)|Rufen Sie diese Methode, um den Benutzernamen aus der URL abzurufen.|  
|[CUrl::GetUserNameLength](#getusernamelength)|Rufen Sie diese Methode, um die Länge des Benutzernamens abzurufen.|  
|[CUrl::SetExtraInfo](#setextrainfo)|Rufen Sie diese Methode, um die zusätzlichen Informationen festgelegt (z. B. *Text* oder # *Text*) der URL.|  
|[CUrl::SetHostName](#sethostname)|Rufen Sie diese Methode, um den Hostnamen festgelegt.|  
|[CUrl::SetPassword](#setpassword)|Rufen Sie diese Methode, um das Kennwort festzulegen.|  
|[CUrl::SetPortNumber](#setportnumber)|Rufen Sie diese Methode, um die Portnummer im Hinblick auf ATL_URL_PORT festgelegt.|  
|[CUrl::SetScheme](#setscheme)|Rufen Sie diese Methode, um das URL-Schema festlegen.|  
|[CUrl::SetSchemeName](#setschemename)|Rufen Sie diese Methode, um den URL-Schema-Namen festlegen.|  
|[CUrl::SetUrlPath](#seturlpath)|Rufen Sie diese Methode, um den URL-Pfad festlegen.|  
|[CUrl::SetUserName](#setusername)|Rufen Sie diese Methode, um den Benutzernamen festgelegt.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CUrl::operator =](#operator_eq)|Weist dem angegebenen `CUrl` Objekt mit dem aktuellen `CUrl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 `CUrl`können Sie die Felder einer URL, z. B. den Pfad oder Port bearbeiten. `CUrl`Weiß URLs in der folgenden Form:  
  
 \<Schema >: / /\<Benutzername >:\<Kennwort > @\<HostName >:\<PortNumber > /\<UrlPath >\<ExtraInfo >  
  
 (Einige Felder sind optional.) Betrachten Sie z. B. diese URL:  
  
 http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents  
  
 [CUrl::CrackUrl](#crackurl) wie folgt analysiert:  
  
-   Schema: "http" oder [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)  
  
-   UserName: "someone"  
  
-   Kennwort: "Secret"  
  
-   HostName: "www.microsoft.com"  
  
-   Portnummer: 80  
  
-   UrlPath: "visualc/stuff.htm"  
  
-   ExtraInfo: "#contents"  
  
 Um das Feld UrlPath (z. B.) zu bearbeiten, verwenden Sie [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), und [SetUrlPath](#seturlpath). Verwenden Sie [CreateUrl](#createurl) die vollständige URL-Zeichenfolge erstellen.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlutil.h  
  
##  <a name="canonicalize"></a>CUrl::Canonicalize  
 Rufen Sie diese Methode, um die URL-Zeichenfolge in die kanonische Form zu konvertieren.  
  
```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Die Flags, Kanonisierung steuern. Wenn keine Optionen angegeben wurden ( `dwFlags` = 0), die-Methode konvertiert alle unsicheren Zeichen sowie Meta-Sequenzen (wie z. B. \\., \..., und \\...) zu escape-Sequenzen. `dwFlags`die folgenden Werte sind möglich:  
  
-   ATL_URL_BROWSER_MODE: Nicht codieren oder Decodieren von Zeichen nach dem "#" oder "" und entfernt keine nachgestellte Leerzeichen nach "". Wenn dieser Wert nicht angegeben wird, wird die gesamte URL und nachfolgendes Leerzeichen werden entfernt.  
  
-   ATL_URL _DECODE: konvertiert alle % XX Sequenzen in Zeichen, einschließlich Escapesequenzen, vor der Analyse der URL.  
  
-   ATL_URL _ENCODE_PERCENT: alle gefunden Prozentzeichen codiert. Standardmäßig werden die Prozentzeichen nicht codiert.  
  
-   ATL_URL _ENCODE_SPACES_ONLY: codiert nur aus Leerzeichen bestehen.  
  
-   ATL_URL _NO_ENCODE: keine unsichere Zeichen in Escapesequenzen konvertiert.  
  
-   ATL_URL _NO_META: entfernt keine Meta-Sequenzen (wie z. B. "."und"..") aus der URL.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Konvertieren in kanonische Form umgestellt unsicheren Zeichen sowie Leerzeichen in escape-Sequenzen.  
  
##  <a name="clear"></a>CUrl::Clear  
 Rufen Sie diese Methode, um alle Felder URL deaktivieren.  
  
```
inline void Clear() throw();
```  
  
##  <a name="crackurl"></a>CUrl::CrackUrl  
 Rufen Sie diese Methode zum Decodieren und analysieren die URL ein.  
  
```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszUrl`  
 Die URL.  
  
 `dwFlags`  
 Geben Sie ATL_URL_DECODE oder ATL_URL_ESCAPE konvertiert alle Escapezeichen in `lpszUrl` auf die tatsächlichen Werte nach der Analyse. (Vor Visual C++ 2005 konvertiert ATL_URL_DECODE alle Escapezeichen vor der Analyse.)  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="createurl"></a>CUrl::CreateUrl  
 Diese Methode erstellt eine URL-Zeichenfolge aus einem CUrl Objektfelder Komponente.  
  
```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszUrl*  
 Ein Zeichenfolgenpuffer, halten Sie die vollständige URL-Zeichenfolge.  
  
 `pdwMaxLength`  
 Die maximale Länge von der *LpszUrl* Zeichenfolgenpuffer.  
  
 `dwFlags`  
 Geben Sie ATL_URL_ESCAPE konvertiert alle Escapezeichen in *LpszUrl* die tatsächlichen Werte.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt die einzelnen Felder, um die vollständige URL-Zeichenfolge im folgenden Format zu erstellen:  
  
 **\<Schema >: / /\<Benutzer >:\<übergeben > @\<Domäne >:\<Port >\<Pfad >\<zusätzliche >**  
  
 Beim Aufrufen dieser Methode die `pdwMaxLength` -Parameter sollte die maximale Länge des Zeichenfolgenpuffers, auf die verwiesen wird anfänglich enthalten die *LpszUrl* Parameter. Der Wert der `pdwMaxLength` Parameter wird mit der tatsächlichen Länge der URL-Zeichenfolge aktualisiert werden.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Erstellung eines Objekts CUrl und Abrufen der URL-Zeichenfolge  
  
 [!code-cpp[NVC_ATL_Utilities&#133;](../../atl/codesnippet/cpp/curl-class_1.cpp)]  
  
##  <a name="curl"></a>CUrl::CUrl  
 Der Konstruktor.  
  
```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `urlThat`  
 Das `CUrl` Objekt zu kopieren, um die URL zu erstellen.  
  
##  <a name="dtor"></a>CUrl:: ~ CUrl  
 Der Destruktor.  
  
```
~CUrl() throw();
```  
  
##  <a name="getextrainfo"></a>CUrl::GetExtraInfo  
 Rufen Sie diese Methode, um zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL.  
  
```
inline LPCTSTR GetExtraInfo() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt eine Zeichenfolge, die die zusätzliche Informationen enthält.  
  
##  <a name="getextrainfolength"></a>CUrl::GetExtraInfoLength  
 Rufen Sie diese Methode zum Abrufen der Länge eines der zusätzlichen Informationen (z. B. *Text* oder # *Text*) aus der URL abgerufen.  
  
```
inline DWORD GetExtraInfoLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge der Zeichenfolge, die die zusätzliche Informationen enthält.  
  
##  <a name="gethostname"></a>CUrl::GetHostName  
 Rufen Sie diese Methode, um den Hostnamen aus der URL abzurufen.  
  
```
inline LPCTSTR GetHostName() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Hostnamen zurück.  
  
##  <a name="gethostnamelength"></a>CUrl::GetHostNameLength  
 Rufen Sie diese Methode, um die Länge des Hostnamens abgerufen werden.  
  
```
inline DWORD GetHostNameLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge zurück.  
  
##  <a name="getpassword"></a>CUrl::GetPassword  
 Rufen Sie diese Methode, um das Kennwort aus der URL abzurufen.  
  
```
inline LPCTSTR GetPassword() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt das Kennwort zurück.  
  
##  <a name="getpasswordlength"></a>CUrl::GetPasswordLength  
 Rufen Sie diese Methode, um die Länge des Kennworts abzurufen.  
  
```
inline DWORD GetPasswordLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge des zurück.  
  
##  <a name="getportnumber"></a>CUrl::GetPortNumber  
 Rufen Sie diese Methode, um die Portnummer abzurufen.  
  
```
inline ATL_URL_PORT GetPortNumber() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Portnummer an.  
  
##  <a name="getscheme"></a>CUrl::GetScheme  
 Rufen Sie diese Methode, um das URL-Schema abgerufen.  
  
```
inline ATL_URL_SCHEME GetScheme() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die [ATL_URL_SCHEME](atl-url-scheme-enum.md) -Wert, der das Schema der URL.  
  
##  <a name="getschemename"></a>CUrl::GetSchemeName  
 Rufen Sie diese Methode, um den URL-Schema-Namen abrufen.  
  
```
inline LPCTSTR GetSchemeName() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Namen des URL-Schema (z. B. "http" oder "ftp").  
  
##  <a name="getschemenamelength"></a>CUrl::GetSchemeNameLength  
 Rufen Sie diese Methode, um die Länge der URL-Schema-Namen abrufen.  
  
```
inline DWORD GetSchemeNameLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge des URL-Schema.  
  
##  <a name="geturllength"></a>CUrl::GetUrlLength  
 Rufen Sie diese Methode zum Abrufen der URL-Länge.  
  
```
inline DWORD GetUrlLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die URL-Länge zurückgegeben.  
  
##  <a name="geturlpath"></a>CUrl::GetUrlPath  
 Rufen Sie diese Methode, um den URL-Pfad abzurufen.  
  
```
inline LPCTSTR GetUrlPath() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den URL-Pfad.  
  
##  <a name="geturlpathlength"></a>CUrl::GetUrlPathLength  
 Rufen Sie diese Methode, um die Länge der URL-Pfad abzurufen.  
  
```
inline DWORD GetUrlPathLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge der URL-Pfad zurück.  
  
##  <a name="getusername"></a>CUrl::GetUserName  
 Rufen Sie diese Methode, um den Benutzernamen aus der URL abzurufen.  
  
```
inline LPCTSTR GetUserName() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt den Benutzernamen zurück.  
  
##  <a name="getusernamelength"></a>CUrl::GetUserNameLength  
 Rufen Sie diese Methode, um die Länge des Benutzernamens abzurufen.  
  
```
inline DWORD GetUserNameLength() const throw();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Länge für den Benutzernamen zurück.  
  
##  <a name="operator_eq"></a>CUrl::operator =  
 Weist dem angegebenen `CUrl` Objekt mit dem aktuellen `CUrl` Objekt.  
  
```
CUrl& operator= (const CUrl& urlThat) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `urlThat`  
 Die `CUrl` -Objekt, in das aktuelle Objekt kopiert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Verweis auf das aktuelle Objekt zurück.  
  
##  <a name="setextrainfo"></a>CUrl::SetExtraInfo  
 Rufen Sie diese Methode, um die zusätzlichen Informationen festgelegt (z. B. *Text* oder # *Text*) der URL.  
  
```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszInfo*  
 Die Zeichenfolge, die zusätzliche Informationen in der URL enthalten.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="sethostname"></a>CUrl::SetHostName  
 Rufen Sie diese Methode, um den Hostnamen festgelegt.  
  
```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszHost`  
 Der Hostname.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="setpassword"></a>CUrl::SetPassword  
 Rufen Sie diese Methode, um das Kennwort festzulegen.  
  
```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszPass*  
 Das Kennwort.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="setportnumber"></a>CUrl::SetPortNumber  
 Rufen Sie diese Methode, um die Portnummer festgelegt.  
  
```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *nPrt*  
 Die Portnummer.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="setscheme"></a>CUrl::SetScheme  
 Rufen Sie diese Methode, um das URL-Schema festlegen.  
  
```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `nScheme`  
 Eines der [ATL_URL_SCHEME](atl-url-scheme-enum.md) Werte für das Schema.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Sie können auch das Schema nach Namen festlegen (siehe [CUrl::SetSchemeName](#setschemename)).  
  
##  <a name="setschemename"></a>CUrl::SetSchemeName  
 Rufen Sie diese Methode, um den URL-Schema-Namen festlegen.  
  
```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszSchm*  
 Der Name des URL-Schema.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Schema auch festlegen, mit einer [ATL_URL_SCHEME](atl-url-scheme-enum.md) konstant (finden Sie unter [CUrl::SetScheme](#setscheme)).  
  
##  <a name="seturlpath"></a>CUrl::SetUrlPath  
 Rufen Sie diese Methode, um den URL-Pfad festlegen.  
  
```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPath`  
 Der URL-Pfad.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
##  <a name="setusername"></a>CUrl::SetUserName  
 Rufen Sie diese Methode, um den Benutzernamen festgelegt.  
  
```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```  
  
### <a name="parameters"></a>Parameter  
 *lpszUser*  
 Der Benutzername.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt TRUE zurück, bei Erfolg, bei einem Fehler FALSE.  
  
## <a name="see-also"></a>Siehe auch  
 [Klassen](../../atl/reference/atl-classes.md)

