---
title: CSocketAddr-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
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
ms.openlocfilehash: ee3f69874460d09e495a237985a98ace19134a01
ms.lasthandoff: 02/24/2017

---
# <a name="csocketaddr-class"></a>CSocketAddr-Klasse
Diese Klasse stellt Methoden zum Konvertieren von Host-Namen in Adressen, IPv4 und IPV6-Formate unterstützen.  
  
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
|[CSocketAddr::FindAddr](#findaddr)|Rufen Sie diese Methode, um dem angegebenen Hostnamen in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|Rufen Sie diese Methode, um den IPv4-Hostnamen in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|Rufen Sie diese Methode, um den IPv6-Hostnamen in die Adresse des Hosts zu konvertieren.|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der **Addrinfo** Liste.|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf die **Addrinfo** Liste.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse stellt eine IP-Version sprachunabhängigen Ansatz für die Suche nach Adressen im Netzwerk für die Verwendung mit Windows sockets-API-Funktionen und Socket-Wrapper in Bibliotheken.  
  
 Die Member dieser Klasse, die verwendet werden, um Adressen im Netzwerk zu suchen, verwenden die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
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
 Rufen Sie diese Methode, um dem angegebenen Hostnamen in die Adresse des Hosts zu konvertieren.  
  
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
 Die Portnummer oder der Name des Diensts auf dem Host.  
  
 `nPortNo`  
 Die Portnummer.  
  
 `flags`  
 0 oder eine Kombination von AI_PASSIVE, AI_CANONNAME oder AI_NUMERICHOST.  
  
 *addr_family*  
 Adressenfamilie (z. B. PF_INET).  
  
 `sock_type`  
 Socket-Datentyp (z. B. SOCK_STREAM).  
  
 *ai_proto*  
 Protokoll (z. B. IPPROTO_IP oder IPPROTO_IPV6).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt&0; (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die referenziert werden kann, mit `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Der Host-Name-Parameter möglicherweise entweder IPv4 oder IPv6-Format. Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Ausführen der Konvertierung.  
  
##  <a name="findinet4addr"></a>CSocketAddr::FindINET4Addr  
 Rufen Sie diese Methode, um den IPv4-Hostnamen in die Adresse des Hosts zu konvertieren.  
  
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
 Socket-Datentyp (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt&0; (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die referenziert werden kann, mit `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Ausführen der Konvertierung.  
  
##  <a name="findinet6addr"></a>CSocketAddr::FindINET6Addr  
 Rufen Sie diese Methode, um den IPv6-Hostnamen in die Adresse des Hosts zu konvertieren.  
  
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
 Socket-Datentyp (z. B. SOCK_STREAM).  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt&0; (null), wenn die Adresse erfolgreich berechnet wird. Gibt einen Wert ungleich NULL Windows Socket-Fehlercode bei einem Fehler zurück. Wenn erfolgreich, die berechnete Adresse in einer verknüpften Liste gespeichert ist, die referenziert werden kann, mit `CSocketAddr::GetAddrInfoList` und `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Win32-API-Funktion [Getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) zum Ausführen der Konvertierung.  
  
##  <a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo  
 Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf ein bestimmtes Element in der **Addrinfo** Liste.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Ein Verweis auf ein bestimmtes Element in der [Addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Zeiger auf die **Addrinfo** auf die Struktur `nIndex` in der verknüpften Liste, die Antwortinformationen über den Host enthält.  
  
##  <a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList  
 Rufen Sie diese Methode, um die Rückgabe eines Zeigers auf die **Addrinfo** Liste.  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>Rückgabewert  
 Zeiger auf eine verknüpfte Liste von einem oder mehreren `addrinfo` Strukturen, die Antwortinformationen über den Host enthält. Weitere Informationen zu den `addrinfo` -Struktur, finden Sie im Artikel "Addrinfo" in der [MSDN-Bibliothek](http://go.microsoft.com/fwlink/linkid=556)  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

