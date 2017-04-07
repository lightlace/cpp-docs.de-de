---
title: CInternetConnection Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- asynchronous connections
- CInternetConnection class
- Internet connections
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: 21
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
ms.openlocfilehash: 7f99562e0c6103fc3f46a7fe28f9d2f2efff0a01
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetconnection-class"></a>CInternetConnection-Klasse
Verwaltet die Verbindung mit einem Internetserver.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Erstellt ein `CInternetConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Ruft die Kontext-ID für dieses Verbindungsobjekt ab.|  
|[CInternetConnection::GetServerName](#getservername)|Ruft den Namen des Servers mit der Verbindung verknüpft ist.|  
|[CInternetConnection::GetSession](#getsession)|Ruft einen Zeiger auf die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt, das der Verbindung zugeordnet.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Ein Handle für eine Internet-Sitzung.|  
  
## <a name="remarks"></a>Hinweise  
 Es ist die Basisklasse für MFC-Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Jede dieser Klassen bietet zusätzliche Funktionen für die Kommunikation mit dem jeweiligen FTP-, HTTP- oder Gopher-Server.  
  
 Um direkt mit einem Internetserver zu kommunizieren, muss Ihnen ein [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt und ein `CInternetConnection` Objekt.  
  
 Um weitere Informationen dazu, wie von der WinInet-Klassen, finden Sie im Artikel [Internet Programmierung mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 Diese Member-Funktion wird aufgerufen, wenn ein `CInternetConnection` Objekt erstellt wird.  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Parameter  
 `pSession`  
 Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt.  
  
 `pstrServer`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen des Servers enthält.  
  
 `nPort`  
 Die Zahl, die den Internet-Port für diese Verbindung identifiziert.  
  
 `dwContext`  
 Der Kontextbezeichner für den `CInternetConnection` Objekt. Finden Sie unter **Hinweise** Weitere Informationen zu `dwContext`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nicht `CInternetConnection` selbst, rufen Sie stattdessen die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Member-Funktion für den Typ der Verbindung, die Sie einrichten möchten:  
  
- [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 Der Standardwert für `dwContext` von MFC gesendet wird die `CInternetConnection`-abgeleitetes Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellten Objekt der **InternetConnection**-abgeleitetes Objekt. Der Standardwert ist auf 1 festgelegt. Sie können jedoch einen bestimmten Kontext-Bezeichner im explizit zuweisen der [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) Konstruktor für die Verbindung. Das Objekt und die Arbeit ist, werden dieser Kontext-ID zugeordnet werden. Die Kontext-ID wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) um den Status des Objekts bereitzustellen, mit dem er identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="getcontext"></a>CInternetConnection::GetContext  
 Rufen Sie diese Memberfunktion, um die Kontext-ID für diese Sitzung zu erhalten.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anwendung zugeordnete Kontext-ID  
  
### <a name="remarks"></a>Hinweise  
 Die Kontext-ID ist ursprünglich im angegebenen [CInternetSession](../../mfc/reference/cinternetsession-class.md) und wird an `CInternetConnection`- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-abgeleitete Klassen, sofern nicht anders in den Aufruf einer Funktion angegeben, die die Verbindung geöffnet wird. Die Kontext-ID jeder Vorgang, der dem angegebenen Objekt zugeordnet ist, und identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Weitere Informationen dazu, wie **GetContext** arbeitet mit anderen WinInet-Klassen Geben Sie die Informationen zum Benutzer, finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="getservername"></a>CInternetConnection::GetServerName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Servers mit diesem Internet-Verbindung verknüpft ist.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Servers, den dieses Verbindungsobjekt arbeitet.  
  
##  <a name="getsession"></a>CInternetConnection::GetSession  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die `CInternetSession` -Objekt, das dieser Verbindung zugeordnet ist.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt, das mit diesem Internet Connection-Objekt zugeordnet.  
  
##  <a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 Verwenden Sie diesen Operator, um das Handle auf API-Ebene für die aktuelle Sitzung mit Internet abzurufen.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




