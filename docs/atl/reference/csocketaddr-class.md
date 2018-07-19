---
title: CSocketAddr-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9e63a464b68267c8202cdf47717fd1cd81db639c
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884036"
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
  
 Die Elemente dieser Klasse, die verwendet werden, um das Suchen der Adressen im Netzwerk verwenden Sie die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
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
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>Parameter  
 *szHost*  
 Der Hostname oder IP-Adresse.  
  
 *szPortOrServiceName*  
 Die Portnummer oder der Name des Diensts auf dem Host.  
  
 *nPortNo*  
 Nummer des Ports.  
  
 *flags*  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 *addr_family*  
 Adressenfamilie (z. B. PF_INET).  
  
 *sock_type*  
 Socket-Typ (z. B. SOCK_STREAM).  
  
 *ai_proto*  
 Protokoll (z. B. IPPROTO_IP oder IPPROTO_IPV6).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Die Host-Name-Parameter kann im IPv4- oder IPv6-Format vorliegen. Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="findinet4addr"></a>  CSocketAddr::FindINET4Addr  
 Rufen Sie diese Methode, um den Namen des IPv4-Hosts in die Adresse des Hosts zu konvertieren.  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parameter  
 *szHost*  
 Der Hostname oder IP-Adresse.  
  
 *nPortNo*  
 Nummer des Ports.  
  
 *flags*  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 *sock_type*  
 Socket-Typ (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="findinet6addr"></a>  CSocketAddr::FindINET6Addr  
 Rufen Sie diese Methode, um den Namen des IPv6-Hosts in die Adresse des Hosts zu konvertieren.  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parameter  
 *szHost*  
 Der Hostname oder IP-Adresse.  
  
 *nPortNo*  
 Nummer des Ports.  
  
 *flags*  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 *sock_type*  
 Socket-Typ (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse wurde erfolgreich berechnet wird. Gibt einen Windows Socket-Fehlercode ungleich NULL bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="getaddrinfo"></a>  CSocketAddr::GetAddrInfo  
 Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der `addrinfo` Liste.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Ein Verweis auf ein bestimmtes Element in der [Addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) Liste.  
  
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
