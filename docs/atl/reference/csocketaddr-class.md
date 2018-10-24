---
title: CSocketAddr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 705cbd051f7c5761ae9a2aabfe919519681ef089
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2018
ms.locfileid: "49990216"
---
# <a name="csocketaddr-class"></a>CSocketAddr-Klasse

Diese Klasse stellt Methoden zum Konvertieren von Hostnamen in Host-Adressen, IPv4 und IPV6-Formate unterstützen.

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
|[CSocketAddr::FindAddr](#findaddr)|Rufen Sie diese Methode, um die angegebene Hostname in die Adresse des Hosts zu konvertieren.|
|[CSocketAddr::FindINET4Addr](#findinet4addr)|Rufen Sie diese Methode, um den Namen des IPv4-Hosts in die Adresse des Hosts zu konvertieren.|
|[CSocketAddr::FindINET6Addr](#findinet6addr)|Rufen Sie diese Methode, um den Namen des IPv6-Hosts in die Adresse des Hosts zu konvertieren.|
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der `addrinfo` Liste.|
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Rufen Sie diese Methode zum Zurückgeben der eines Zeigers auf die `addrinfo` Liste.|

## <a name="remarks"></a>Hinweise

Diese Klasse stellt eine IP-Version, dass unabhängig Ansatz für die Suche nach Adressen im Netzwerk für die Verwendung mit Windows sockets-API-Funktionen und Socket-Wrappern in Bibliotheken.

Die Elemente dieser Klasse, die verwendet werden, um das Suchen der Adressen im Netzwerk verwenden Sie die Win32-API-Funktion [Getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo). Die ANSI- oder Unicode-Version der Funktion wird aufgerufen, je nachdem, ob der Code für ANSI- oder UNICODE kompiliert wird.

Diese Klasse unterstützt sowohl IPv4-Netzwerkadressen, andIPv6.

## <a name="requirements"></a>Anforderungen

**Header:** atlsocket.h

##  <a name="csocketaddr"></a>  CSocketAddr::CSocketAddr

Der Konstruktor.

```
CSocketAddr();
```

### <a name="remarks"></a>Hinweise

Erstellt ein neues `CSocketAddr` -Objekt und initialisiert die verknüpfte Liste, die Antwortinformationen über den Host enthält.

##  <a name="findaddr"></a>  CSocketAddr::FindAddr

Rufen Sie diese Methode, um die angegebene Hostname in die Adresse des Hosts zu konvertieren.

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
Der Hostname oder IP-Adresse.

*szPortOrServiceName*<br/>
Die Portnummer oder der Name des Diensts auf dem Host.

*nPortNo*<br/>
Nummer des Ports.

*flags*<br/>
0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*addr_family*<br/>
Adressenfamilie (z. B. PF_INET).

*sock_type*<br/>
Socket-Typ (z. B. SOCK_STREAM).

*ai_proto*<br/>
Protokoll (z. B. IPPROTO_IP oder IPPROTO_IPV6).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Hinweise

Die Host-Name-Parameter kann im IPv4- oder IPv6-Format vorliegen. Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) zum Durchführen der Konvertierung.

##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr

Rufen Sie diese Methode, um den Namen des IPv4-Hosts in die Adresse des Hosts zu konvertieren.

```
int FindINET4Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parameter

*szHost*<br/>
Der Hostname oder IP-Adresse.

*nPortNo*<br/>
Nummer des Ports.

*flags*<br/>
0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*sock_type*<br/>
Socket-Typ (z. B. SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) zum Durchführen der Konvertierung.

##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr

Rufen Sie diese Methode, um den Namen des IPv6-Hosts in die Adresse des Hosts zu konvertieren.

```
int FindINET6Addr(
    const TCHAR *szHost,
    int nPortNo,
    int flags = 0,
    int sock_type = SOCK_STREAM);
```

### <a name="parameters"></a>Parameter

*szHost*<br/>
Der Hostname oder IP-Adresse.

*nPortNo*<br/>
Nummer des Ports.

*flags*<br/>
0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.

*sock_type*<br/>
Socket-Typ (z. B. SOCK_STREAM).

### <a name="return-value"></a>Rückgabewert

Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.

### <a name="remarks"></a>Hinweise

Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-getaddrinfo) zum Durchführen der Konvertierung.

##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo

Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der `addrinfo` Liste.

```
addrinfo* const GetAddrInfo(int nIndex = 0) const;
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Ein Verweis auf ein bestimmtes Element in der [Addrinfo](https://msdn.microsoft.com/library/windows/desktop/ms737530) Liste.

### <a name="return-value"></a>Rückgabewert

Gibt einen Zeiger auf die `addrinfo` Struktur verweist *nIndex* in der verknüpften Liste, die Antwortinformationen über den Host enthält.

##  <a name="getaddrinfolist"></a>  CSocketAddr::GetAddrInfoList

Rufen Sie diese Methode zum Zurückgeben der eines Zeigers auf die `addrinfo` Liste.

```
addrinfo* const GetAddrInfoList() const;
```

### <a name="return-value"></a>Rückgabewert

Zeiger auf eine verknüpfte Liste eines oder mehrerer `addrinfo` Strukturen, die Antwortinformationen über den Host. Weitere Informationen finden Sie unter [Addrinfo Struktur](https://msdn.microsoft.com/library/windows/desktop/ms737530).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
