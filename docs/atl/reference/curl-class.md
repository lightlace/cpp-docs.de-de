---
title: CUrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0babb0932fc059a91fd8da79f649039bcaebc457
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43753729"
---
# <a name="curl-class"></a>CUrl-Klasse

Diese Klasse stellt eine URL an. Sie können jedes Element der unabhängig von den anderen-URL ändern, ob eine vorhandene URL analysieren Zeichenfolge oder eine Zeichenfolge von Grund auf neu erstellen.

> [!IMPORTANT]
>  Diese Klasse und ihre Member können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.

## <a name="syntax"></a>Syntax

```
class CUrl
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CUrl::CUrl](#curl)|Der Konstruktor.|
|[CUrl:: ~ CUrl](#dtor)|Der Destruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CUrl::Canonicalize](#canonicalize)|Rufen Sie diese Methode, um die URL-Zeichenfolge in kanonischer Form konvertieren.|
|[CUrl::Clear](#clear)|Rufen Sie diese Methode, um alle von der URL-Felder zu deaktivieren.|
|[CUrl::CrackUrl](#crackurl)|Rufen Sie diese Methode zum Decodieren und analysieren die URL ein.|
|[CUrl::CreateUrl](#createurl)|Rufen Sie diese Methode, um die URL zu erstellen.|
|[CUrl::GetExtraInfo](#getextrainfo)|Rufen Sie diese Methode, um zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL.|
|[CUrl::GetExtraInfoLength](#getextrainfolength)|Rufen Sie diese Methode, um die Länge der zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL abrufen.|
|[CUrl::GetHostName](#gethostname)|Rufen Sie diese Methode, um den Namen des Hosts aus der URL zu erhalten.|
|[CUrl::GetHostNameLength](#gethostnamelength)|Rufen Sie diese Methode, um die Länge des Hostnamens abgerufen werden.|
|[CUrl::GetPassword](#getpassword)|Rufen Sie diese Methode zum Abrufen des Kennworts aus der URL.|
|[CUrl::GetPasswordLength](#getpasswordlength)|Rufen Sie diese Methode, um die Länge des Kennworts abgerufen werden.|
|[CUrl::GetPortNumber](#getportnumber)|Rufen Sie diese Methode, um die Portnummer im Hinblick auf ATL_URL_PORT abzurufen.|
|[CUrl::GetScheme](#getscheme)|Rufen Sie diese Methode, um das URL-Schema abgerufen.|
|[CUrl::GetSchemeName](#getschemename)|Rufen Sie diese Methode zum Abrufen des Namens der URL-Schema.|
|[CUrl::GetSchemeNameLength](#getschemenamelength)|Rufen Sie diese Methode, um die Länge des URL-Schema namens abgerufen werden.|
|[CUrl::GetUrlLength](#geturllength)|Rufen Sie diese Methode, um die URL-Länge abgerufen werden.|
|[CUrl::GetUrlPath](#geturlpath)|Rufen Sie diese Methode, um den URL-Pfad abzurufen.|
|[CUrl::GetUrlPathLength](#geturlpathlength)|Rufen Sie diese Methode, um die Länge der URL-Pfad abgerufen werden.|
|[CUrl::GetUserName](#getusername)|Rufen Sie diese Methode, um den Benutzernamen aus der URL abzurufen.|
|[CUrl::GetUserNameLength](#getusernamelength)|Rufen Sie diese Methode, um die Länge des Benutzernamens abgerufen werden.|
|[CUrl::SetExtraInfo](#setextrainfo)|Rufen Sie diese Methode, um die zusätzlichen Informationen festzulegen (z. B. *Text* oder # *Text*) der URL.|
|[CUrl::SetHostName](#sethostname)|Rufen Sie diese Methode, um den Hostnamen fest.|
|[CUrl::SetPassword](#setpassword)|Rufen Sie diese Methode, um das Kennwort festzulegen.|
|[CUrl::SetPortNumber](#setportnumber)|Rufen Sie diese Methode, um die Portnummer im Hinblick auf ATL_URL_PORT festgelegt.|
|[CUrl::SetScheme](#setscheme)|Rufen Sie diese Methode, um das URL-Schema festlegen.|
|[CUrl::SetSchemeName](#setschemename)|Rufen Sie diese Methode, um den URL-Schemanamen festgelegt.|
|[CUrl::SetUrlPath](#seturlpath)|Rufen Sie diese Methode zum Festlegen des URL-Pfads.|
|[CUrl::SetUserName](#setusername)|Rufen Sie diese Methode, um den Benutzernamen festgelegt.|

### <a name="public-operators"></a>Öffentliche Operatoren

|Name|Beschreibung|
|----------|-----------------|
|[CUrl::operator =](#operator_eq)|Weist dem angegebenen `CUrl` -Objekt mit dem aktuellen `CUrl` Objekt.|

## <a name="remarks"></a>Hinweise

`CUrl` können Sie die Felder einer URL, z. B. den Pfad oder Port ändern. `CUrl` versteht URLs im folgenden Format an:

\<Schema > ://\<UserName >:\<Kennwort > @\<HostName >:\<PortNumber > /\<UrlPath >\<ExtraInfo >

(Einige Felder sind optional.) Betrachten Sie beispielsweise diese URL ein:

http://someone:secret@www.microsoft.com:80/visualc/stuff.htm#contents

[CUrl::CrackUrl](#crackurl) wie folgt analysiert:

- Schema: "http" oder [ATL_URL_SCHEME_HTTP](atl-url-scheme-enum.md)

- Benutzername: "someone"

- Kennwort: "geheimer Schlüssel"

- HostName: "www.microsoft.com"

- Portnummer: 80

- UrlPath: "visualc/stuff.htm"

- ExtraInfo: "#contents"

Um die UrlPath-Feld (beispielsweise) zu bearbeiten, verwenden Sie [GetUrlPath](#geturlpath), [GetUrlPathLength](#geturlpathlength), und [SetUrlPath](#seturlpath). Verwenden Sie [CreateUrl](#createurl) um die vollständige URL-Zeichenfolge zu erstellen.

## <a name="requirements"></a>Anforderungen

**Header:** "atlutil.h"

##  <a name="canonicalize"></a>  CUrl::Canonicalize

Rufen Sie diese Methode, um die URL-Zeichenfolge in kanonischer Form konvertieren.

```
inline BOOL Canonicalize(DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parameter

*dwFlags*  
Die Flags, die Kanonisierung steuern. Wenn keine Flags angegeben werden (*DwFlags* = 0), die Methode konvertiert alle unsicheren Zeichen sowie Metadaten Sequenzen (z. B. \\., \.., und \\...) Sequenzen mit Escapezeichen versehen. *DwFlags* kann eine der folgenden Werte:

- ATL_URL_BROWSER_MODE: Nicht codieren oder Decodieren von Zeichen nach "#" oder "" und wird nicht entfernt nachgestellte Leerzeichen nach "". Wenn dieser Wert nicht angegeben ist, wird die gesamte URL codiert und nachgestellte Leerzeichen entfernt.

- ATL_URL _DECODE: konvertiert alle % XX Sequenzen in Zeichen, einschließlich der Escape-Sequenzen, bevor die URL analysiert wird.

- ATL_URL _ENCODE_PERCENT: alle gefunden Prozentzeichen codiert. Standardmäßig werden die Prozentzeichen nicht codiert.

- ATL_URL _ENCODE_SPACES_ONLY: codiert nur aus Leerzeichen bestehen.

- ATL_URL _NO_ENCODE: nicht unsichere Zeichen in Escapesequenzen konvertiert.

- ATL_URL _NO_META: Meta-Sequenzen werden nicht entfernt (wie z. B. "."und"..") aus der URL.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Konvertieren in kanonischer Form umgestellt unsicheren Zeichen sowie Leerzeichen in escape-Sequenzen.

##  <a name="clear"></a>  CUrl::Clear

Rufen Sie diese Methode, um alle von der URL-Felder zu deaktivieren.

```
inline void Clear() throw();
```

##  <a name="crackurl"></a>  CUrl::CrackUrl

Rufen Sie diese Methode zum Decodieren und analysieren die URL ein.

```
BOOL CrackUrl(LPCTSTR lpszUrl, DWORD dwFlags = 0) throw();
```

### <a name="parameters"></a>Parameter

*lpszUrl*  
Die URL.

*dwFlags*  
Geben Sie ATL_URL_DECODE oder ATL_URL_ESCAPE, um alle Escapezeichen in konvertieren *LpszUrl* auf die tatsächlichen Werte nach der Analyse. (Vor Visual C++ 2005 konvertiert ATL_URL_DECODE alle Escape-Zeichen vor der Analyse.)

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="createurl"></a>  CUrl::CreateUrl

Diese Methode erstellt eine URL-Zeichenfolge aus einer CUrl Objektfelder Komponente.

```
inline BOOL CreateUrl(
    LPTSTR lpszUrl,
    DWORD* pdwMaxLength,
    DWORD dwFlags = 0) const throw();
```

### <a name="parameters"></a>Parameter

*lpszUrl*  
Einen Zeichenfolgenpuffer, die die vollständige URL-Zeichenfolge enthalten soll.

*pdwMaxLength*  
Die maximale Länge von der *LpszUrl* Zeichenfolgenpuffer.

*dwFlags*  
Geben Sie ATL_URL_ESCAPE zum Konvertieren von alle Escapezeichen in *LpszUrl* auf die tatsächlichen Werte.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Diese Methode fügt die einzelnen Felder, um die vollständige URL-Zeichenfolge, die mithilfe des folgenden Formats zu erstellen:

**\<Schema > ://\<Benutzer >:\<übergeben > @\<Domäne >:\<Port >\<Pfad >\<zusätzliche >**

Beim Aufrufen dieser Methode, die *PdwMaxLength* -Parameter enthalten die maximale Länge des Zeichenfolgenpuffers verwiesen wird, indem Sie zunächst die *LpszUrl* Parameter. Der Wert des der *PdwMaxLength* Parameter mit der tatsächlichen Länge der URL-Zeichenfolge, aktualisiert werden.

### <a name="example"></a>Beispiel

Dieses Beispiel veranschaulicht die Erstellung eines Objekts CUrl und Abrufen der URL-Zeichenfolge

[!code-cpp[NVC_ATL_Utilities#133](../../atl/codesnippet/cpp/curl-class_1.cpp)]

##  <a name="curl"></a>  CUrl::CUrl

Der Konstruktor.

```
CUrl() throw();
CUrl(const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parameter

*URL*  
Die `CUrl` Objekt zu kopieren, um die URL zu erstellen.

##  <a name="dtor"></a>  CUrl:: ~ CUrl

Der Destruktor.

```
~CUrl() throw();
```

##  <a name="getextrainfo"></a>  CUrl::GetExtraInfo

Rufen Sie diese Methode, um zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL.

```
inline LPCTSTR GetExtraInfo() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt eine Zeichenfolge, die zusätzlichen Informationen enthält.

##  <a name="getextrainfolength"></a>  CUrl::GetExtraInfoLength

Rufen Sie diese Methode, um die Länge der zusätzliche Informationen zu erhalten (z. B. *Text* oder # *Text*) aus der URL abrufen.

```
inline DWORD GetExtraInfoLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge der Zeichenfolge, die zusätzlichen Informationen enthält.

##  <a name="gethostname"></a>  CUrl::GetHostName

Rufen Sie diese Methode, um den Namen des Hosts aus der URL zu erhalten.

```
inline LPCTSTR GetHostName() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Namen des Hosts zurück.

##  <a name="gethostnamelength"></a>  CUrl::GetHostNameLength

Rufen Sie diese Methode, um die Länge des Hostnamens abgerufen werden.

```
inline DWORD GetHostNameLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge des zurück.

##  <a name="getpassword"></a>  CUrl::GetPassword

Rufen Sie diese Methode zum Abrufen des Kennworts aus der URL.

```
inline LPCTSTR GetPassword() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt das Kennwort zurück.

##  <a name="getpasswordlength"></a>  CUrl::GetPasswordLength

Rufen Sie diese Methode, um die Länge des Kennworts abgerufen werden.

```
inline DWORD GetPasswordLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge des Kennworts zurück.

##  <a name="getportnumber"></a>  CUrl::GetPortNumber

Rufen Sie diese Methode, um die Portnummer abzurufen.

```
inline ATL_URL_PORT GetPortNumber() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Nummer des Ports an.

##  <a name="getscheme"></a>  CUrl::GetScheme

Rufen Sie diese Methode, um das URL-Schema abgerufen.

```
inline ATL_URL_SCHEME GetScheme() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die [ATL_URL_SCHEME](atl-url-scheme-enum.md) Wert, der das Schema der URL beschreibt.

##  <a name="getschemename"></a>  CUrl::GetSchemeName

Rufen Sie diese Methode zum Abrufen des Namens der URL-Schema.

```
inline LPCTSTR GetSchemeName() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den URL-Schemanamen (z. B. "http" oder "ftp") zurück.

##  <a name="getschemenamelength"></a>  CUrl::GetSchemeNameLength

Rufen Sie diese Methode, um die Länge des URL-Schema namens abgerufen werden.

```
inline DWORD GetSchemeNameLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge für URL-Schema zurück.

##  <a name="geturllength"></a>  CUrl::GetUrlLength

Rufen Sie diese Methode, um die URL-Länge abgerufen werden.

```
inline DWORD GetUrlLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die URL-Länge zurück.

##  <a name="geturlpath"></a>  CUrl::GetUrlPath

Rufen Sie diese Methode, um den URL-Pfad abzurufen.

```
inline LPCTSTR GetUrlPath() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den URL-Pfad zurück.

##  <a name="geturlpathlength"></a>  CUrl::GetUrlPathLength

Rufen Sie diese Methode, um die Länge der URL-Pfad abgerufen werden.

```
inline DWORD GetUrlPathLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge der URL-Pfad zurück.

##  <a name="getusername"></a>  CUrl::GetUserName

Rufen Sie diese Methode, um den Benutzernamen aus der URL abzurufen.

```
inline LPCTSTR GetUserName() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt den Benutzernamen zurück.

##  <a name="getusernamelength"></a>  CUrl::GetUserNameLength

Rufen Sie diese Methode, um die Länge des Benutzernamens abgerufen werden.

```
inline DWORD GetUserNameLength() const throw();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Länge für den Benutzer zurück.

##  <a name="operator_eq"></a>  CUrl::operator =

Weist dem angegebenen `CUrl` -Objekt mit dem aktuellen `CUrl` Objekt.

```
CUrl& operator= (const CUrl& urlThat) throw();
```

### <a name="parameters"></a>Parameter

*URL*  
Die `CUrl` -Objekt, in das aktuelle Objekt kopiert.

### <a name="return-value"></a>Rückgabewert

Gibt einen Verweis auf das aktuelle Objekt zurück.

##  <a name="setextrainfo"></a>  CUrl::SetExtraInfo

Rufen Sie diese Methode, um die zusätzlichen Informationen festzulegen (z. B. *Text* oder # *Text*) der URL.

```
inline BOOL SetExtraInfo(LPCTSTR lpszInfo) throw();
```

### <a name="parameters"></a>Parameter

*lpszInfo*  
Die Zeichenfolge mit dem zusätzliche Informationen, die in der URL enthalten.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="sethostname"></a>  CUrl::SetHostName

Rufen Sie diese Methode, um den Hostnamen fest.

```
inline BOOL SetHostName(LPCTSTR lpszHost) throw();
```

### <a name="parameters"></a>Parameter

*lpszHost*  
Der Hostname.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="setpassword"></a>  CUrl::SetPassword

Rufen Sie diese Methode, um das Kennwort festzulegen.

```
inline BOOL SetPassword(LPCTSTR lpszPass) throw();
```

### <a name="parameters"></a>Parameter

*lpszPass*  
Das Kennwort.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="setportnumber"></a>  CUrl::SetPortNumber

Rufen Sie diese Methode, um die Portnummer festgelegt.

```
inline BOOL SetPortNumber(ATL_URL_PORT nPrt) throw();
```

### <a name="parameters"></a>Parameter

*Schnittstellenadresse*  
Nummer des Ports.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="setscheme"></a>  CUrl::SetScheme

Rufen Sie diese Methode, um das URL-Schema festlegen.

```
inline BOOL SetScheme(ATL_URL_SCHEME nScheme) throw();
```

### <a name="parameters"></a>Parameter

*nScheme*  
Eines der [ATL_URL_SCHEME](atl-url-scheme-enum.md) Werte für das Schema.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Sie können auch das Schema nach Namen festlegen (siehe [CUrl::SetSchemeName](#setschemename)).

##  <a name="setschemename"></a>  CUrl::SetSchemeName

Rufen Sie diese Methode, um den URL-Schemanamen festgelegt.

```
inline BOOL SetSchemeName(LPCTSTR lpszSchm) throw();
```

### <a name="parameters"></a>Parameter

*lpszSchm*  
Der Name des URL-Schema.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

### <a name="remarks"></a>Hinweise

Sie können auch das Schema festlegen, mit einem [ATL_URL_SCHEME](atl-url-scheme-enum.md) Konstanten (finden Sie unter [CUrl::SetScheme](#setscheme)).

##  <a name="seturlpath"></a>  CUrl::SetUrlPath

Rufen Sie diese Methode zum Festlegen des URL-Pfads.

```
inline BOOL SetUrlPath(LPCTSTR lpszPath) throw();
```

### <a name="parameters"></a>Parameter

*lpszPath*  
Die URL-Pfad.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

##  <a name="setusername"></a>  CUrl::SetUserName

Rufen Sie diese Methode, um den Benutzernamen festgelegt.

```
inline BOOL SetUserName(LPCTSTR lpszUser) throw();
```

### <a name="parameters"></a>Parameter

*lpszUser*  
Der Benutzername.

### <a name="return-value"></a>Rückgabewert

Gibt "true" bei Erfolg bei "false".

## <a name="see-also"></a>Siehe auch

[Klassen](../../atl/reference/atl-classes.md)
