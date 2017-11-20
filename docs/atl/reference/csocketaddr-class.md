---
title: CSocketAddr Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
helpviewer_keywords: CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5ed1224fd00d5decb8dc99910563b47e4ba60350
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="csocketaddr-class"></a>CSocketAddr-Klasse
Diese Klasse stellt Methoden zum Konvertieren von Hostnamen in Hostadressen, IPv4 und IPV6-Formate unterstützen.  
  
## <a name="syntax"></a>Syntax  
  
```
class CSocketAddr
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](#csocketaddr)|Der Konstruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](#findaddr)|Rufen Sie diese Methode, um den bereitgestellten Hostnamen in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|Rufen Sie diese Methode, um den Namen des IPv4-Hosts in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|Rufen Sie diese Methode, um die IPv6-Hostname in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der **Addrinfo** Liste.|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf die **Addrinfo** Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt eine IP-Version agnostisch Ansatz für das Nachschlagen von Netzwerkadressen für die Verwendung mit Windows sockets-API-Funktionen und Socket-Wrappern in Bibliotheken.  
  
 Die Member dieser Klasse, die verwendet werden, zum Nachschlagen von Netzwerkadressen verwenden Sie die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 Diese Klasse unterstützt sowohl IPv4-Netzwerkadressen, andIPv6.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlsocket.h  
  
##  <a name="csocketaddr"></a>CSocketAddr::CSocketAddr  
 Der Konstruktor.  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>Hinweise  
 Erstellt ein neues `CSocketAddr` -Objekt und initialisiert die verknüpfte Liste, die Antwortinformationen über den Host enthält.  
  
##  <a name="findaddr"></a>CSocketAddr::FindAddr  
 Rufen Sie diese Methode, um den bereitgestellten Hostnamen in die Adresse des Hosts zu konvertieren.  
  
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
 `szHost`  
 Der Hostname oder die IP-Adresse.  
  
 *szPortOrServiceName*  
 Die Portnummer oder den Namen des Diensts auf dem Host.  
  
 `nPortNo`  
 Die Portnummer.  
  
 `flags`  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 *addr_family*  
 Adressfamilie (z. B. PF_INET).  
  
 `sock_type`  
 Sockettyp (z. B. SOCK_STREAM).  
  
 *ai_proto*  
 Protokoll (z. B. IPPROTO_IP oder IPPROTO_IPV6).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in eine verknüpfte Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Der Namensparameter der Host kann im IPv4- oder IPv6-Format sein. Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="findinet4addr"></a>CSocketAddr::FindINET4Addr  
 Rufen Sie diese Methode, um den Namen des IPv4-Hosts in die Adresse des Hosts zu konvertieren.  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parameter  
 `szHost`  
 Der Hostname oder die IP-Adresse.  
  
 `nPortNo`  
 Die Portnummer.  
  
 `flags`  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 `sock_type`  
 Sockettyp (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in eine verknüpfte Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="findinet6addr"></a>CSocketAddr::FindINET6Addr  
 Rufen Sie diese Methode, um die IPv6-Hostname in die Adresse des Hosts zu konvertieren.  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Parameter  
 `szHost`  
 Der Hostname oder die IP-Adresse.  
  
 `nPortNo`  
 Die Portnummer.  
  
 `flags`  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 `sock_type`  
 Sockettyp (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt 0 (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in eine verknüpfte Liste gespeichert ist, die mit verwiesen werden kann `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Durchführen der Konvertierung.  
  
##  <a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo  
 Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der **Addrinfo** Liste.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Ein Verweis auf ein bestimmtes Element in der [Addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die **Addrinfo** Struktur verweist `nIndex` in der verknüpften Liste, die Antwortinformationen über den Host enthält.  
  
##  <a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList  
 Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf die **Addrinfo** Liste.  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine verknüpfte Liste von einem oder mehreren `addrinfo` Strukturen, die Antwortinformationen über den Host. Weitere Informationen zu den `addrinfo` -Struktur, finden Sie im Artikel "Addrinfo" in der [MSDN Library](http://go.microsoft.com/fwlink/linkid=556)  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)