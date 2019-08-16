---
title: CSocketAddr-Klasse
ms.date: 10/22/2018
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
ms.openlocfilehash: 2a131323e64b1bf67f76ec92e7a3e4fcba899661
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69496346"
---
# <a name="csocketaddr-class"></a>CSocketAddr-Klasse

Diese Klasse stellt Methoden zum Umstellen von Hostnamen in Host Adressen bereit und unterstützt sowohl IPv4-als auch IPv6-Formate.

## <a name="syntax"></a>Syntax

```
class CSocketAddr
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CSocketAddr::CSocketAddr](#csocketaddr)|Der Konstruktor.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CSocketAddr::FindAddr](#findaddr)|Mit dieser Methode wird der angegebene Hostname in die Host Adresse konvertiert.|
|[CSocketAddr:: FindINET4Addr](#findinet4addr)|Mit dieser Methode können Sie den IPv4-Hostnamen in die Host Adresse konvertieren.|
|[CSocketAddr:: FindINET6Addr](#findinet6addr)|Mit dieser Methode können Sie den IPv6-Hostnamen in die Host Adresse konvertieren.|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Ruft diese Methode auf, um einen Zeiger auf ein bestimmtes Element in `addrinfo` der Liste zurückzugeben.|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Mit dieser Methode wird ein Zeiger auf die `addrinfo` Liste zurückgegeben.|

## <a name="remarks"></a>Hinweise

Diese Klasse bietet einen von der IP-Version unabhängigen Ansatz für die Suche nach Netzwerkadressen für die Verwendung mit Windows Sockets-API-Funktionen und socketwrapper in Bibliotheken.

Die Member dieser Klasse, die zum Suchen von Netzwerkadressen verwendet werden, verwenden die Win32-API-Funktion [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo). Die ANSI-oder Unicode-Version der Funktion wird aufgerufen, abhängig davon, ob Ihr Code für ANSI oder Unicode kompiliert ist.

Diese Klasse unterstützt beide IPv4-andIPv6-Netzwerkadressen.

## <a name="requirements"></a>Anforderungen

**Header:** atlsocket. h

##  <a name="csocketaddr"></a>CSocketAddr:: CSocketAddr

Der Konstruktor.

```
CSocketAddr();
```

### <a name="remarks"></a>Hinweise

Erstellt ein neues `CSocketAddr` -Objekt und initialisiert die verknüpfte Liste, die Antwortinformationen über den Host enthält.

##  <a name="findaddr"></a>CSocketAddr:: findaddr

Mit dieser Methode wird der angegebene Hostname in die Host Adresse konvertiert.

```
int FindAddr(
    const TCHAR *szHost,
    const TCHAR *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const TCHAR *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```

### <a name="parameters"></a>Parameter

*szHost*<br/>
Der Hostname oder die gepunktete IP-Adresse.

*szPortOrServiceName*<br/>
Die Portnummer oder der Name des Diensts auf dem Host.

*nPortNo*<br/>
Die Portnummer.

*flags*<br/>
0 oder eine Kombination aus AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*addr_family*<br/>
Adressfamilie (z. b. PF_INET).

*sock_type*<br/>
Socketyp (z. b. SOCK_STREAM).

*ai_proto*<br/>
Protokoll (z. b. IPPROTO_IP oder IPPROTO_IPV6).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Adresse erfolgreich berechnet wird. Gibt einen Windows-socketfehlercode ungleich NULL bei einem Fehler zurück. Bei erfolgreicher Ausführung wird die berechnete Adresse in einer verknüpften Liste gespeichert, auf die `CSocketAddr::GetAddrInfoList` mithilfe `CSocketAddr::GetAddrInfo`von und verwiesen werden kann.

### <a name="remarks"></a>Hinweise

Der Hostname-Parameter kann im IPv4-oder IPv6-Format vorliegen. Diese Methode ruft die Win32-API-Funktion [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) auf, um die Konvertierung auszuführen.

##  <a name="findinet4addr"></a>CSocketAddr:: FindINET4Addr

Mit dieser Methode können Sie den IPv4-Hostnamen in die Host Adresse konvertieren.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parameter

*szHost*<br/>
Der Hostname oder die gepunktete IP-Adresse.

*nPortNo*<br/>
Die Portnummer.

*flags*<br/>
0 oder eine Kombination aus AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*sock_type*<br/>
Socketyp (z. b. SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Adresse erfolgreich berechnet wird. Gibt einen Windows-socketfehlercode ungleich NULL bei einem Fehler zurück. Bei erfolgreicher Ausführung wird die berechnete Adresse in einer verknüpften Liste gespeichert, auf die `CSocketAddr::GetAddrInfoList` mithilfe `CSocketAddr::GetAddrInfo`von und verwiesen werden kann.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Win32-API-Funktion [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) auf, um die Konvertierung auszuführen.

##  <a name="findinet6addr"></a>CSocketAddr:: FindINET6Addr

Mit dieser Methode können Sie den IPv6-Hostnamen in die Host Adresse konvertieren.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parameter

*szHost*<br/>
Der Hostname oder die gepunktete IP-Adresse.

*nPortNo*<br/>
Die Portnummer.

*flags*<br/>
0 oder eine Kombination aus AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*sock_type*<br/>
Socketyp (z. b. SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null) zurück, wenn die Adresse erfolgreich berechnet wird. Gibt einen Windows-socketfehlercode ungleich NULL bei einem Fehler zurück. Bei erfolgreicher Ausführung wird die berechnete Adresse in einer verknüpften Liste gespeichert, auf die `CSocketAddr::GetAddrInfoList` mithilfe `CSocketAddr::GetAddrInfo`von und verwiesen werden kann.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Win32-API-Funktion [getaddrinfo](/windows/win32/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) auf, um die Konvertierung auszuführen.

##  <a name="getaddrinfo"></a>CSocketAddr:: getaddrinfo

Ruft diese Methode auf, um einen Zeiger auf ein bestimmtes Element in `addrinfo` der Liste zurückzugeben.

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Ein Verweis auf ein bestimmtes Element in der [addrinfo](/windows/win32/api/ws2def/ns-ws2def-addrinfow) -Liste.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `addrinfo` Struktur zurück, auf die von *nIndex* in der verknüpften Liste verwiesen wird, die Antwortinformationen über den Host enthält.

##  <a name="getaddrinfolist"></a>CSocketAddr:: getaddrinfolist

Mit dieser Methode wird ein Zeiger auf die `addrinfo` Liste zurückgegeben.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Rückgabewert

Ein Zeiger auf eine verknüpfte Liste von einer `addrinfo` oder mehreren Strukturen, die Antwortinformationen über den Host enthält. Weitere Informationen finden Sie unter [addrinfo Structure](/windows/win32/api/ws2def/ns-ws2def-addrinfow).

## <a name="see-also"></a>Siehe auch

[Klassen Übersicht](../../atl/atl-class-overview.md)
