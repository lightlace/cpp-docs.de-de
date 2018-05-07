---
title: CInternetConnection Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07b269afce3ec0c3ef60e6cc37782fdea18260cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cinternetconnection-class"></a>CInternetConnection-Klasse
Verwaltet die Verbindung mit einem Internetserver.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Erstellt ein `CInternetConnection`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Ruft die Kontext-ID für dieses Verbindungsobjekt ab.|  
|[CInternetConnection::GetServerName](#getservername)|Ruft den Namen des Servers mit der Verbindung verknüpft sind.|  
|[CInternetConnection::GetSession](#getsession)|Ruft einen Zeiger auf die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt, das mit der Verbindung zugeordnet.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Ein Handle für eine Internet-Sitzung.|  
  
## <a name="remarks"></a>Hinweise  
 Es ist die Basisklasse für MFC-Klassen [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), und [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Alle diese Klassen stellen zusätzliche Funktionen für die Kommunikation mit den jeweiligen FTP, HTTP oder Gopher-Server bereit.  
  
 Um direkt mit einem Internetserver kommunizieren zu können, benötigen Sie ein [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt und ein `CInternetConnection` Objekt.  
  
 Um weitere Informationen darüber, wie von der WinInet-Klassen, finden Sie im Artikel [Internet Programmieren mit WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxinet.h  
  
##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection  
 Diese Memberfunktion wird aufgerufen, wenn ein `CInternetConnection` Objekt erstellt wird.  
  
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
 Der Kontextbezeichner für den `CInternetConnection` Objekt. Finden Sie unter **"Hinweise"** Weitere Informationen zu `dwContext`.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie nie `CInternetConnection` selbst; rufen Sie stattdessen die [CInternetSession](../../mfc/reference/cinternetsession-class.md) Memberfunktion für die Art der Verbindung, die Sie einrichten möchten:  
  
- [CInternetSession:: GetFTPConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession:: GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession:: GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 Der Standardwert für `dwContext` wird gesendet, von MFC ermöglicht, die `CInternetConnection`-abgeleitetes Objekt aus der [CInternetSession](../../mfc/reference/cinternetsession-class.md) erstellte Objekt die **InternetConnection**-abgeleitetes Objekt. Die Standardeinstellung ist auf 1 festgelegt. Allerdings können Sie explizit eine bestimmten Kontext-ID im Zuweisen der [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) Konstruktor für die Verbindung. Das Objekt und jede Arbeit, die es ausführt, werden dieser Kontext-ID zugeordnet werden. Der Kontextbezeichner wird zurückgegeben, um [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) zum Status des Objekts bereitzustellen, mit denen es identifiziert wird. Finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontextbezeichner.  
  
##  <a name="getcontext"></a>  CInternetConnection::GetContext  
 Rufen Sie diese Memberfunktion, um die Kontext-ID für diese Sitzung zu erhalten.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anwendung zugewiesen Kontext-ID  
  
### <a name="remarks"></a>Hinweise  
 Die Kontext-ID ist im ursprünglich angegebene [CInternetSession](../../mfc/reference/cinternetsession-class.md) und wird an übertragen `CInternetConnection`- und [CInternetFile](../../mfc/reference/cinternetfile-class.md)-abgeleiteten Klassen aus, es sei denn, die im Aufruf einer Funktion anders angegeben, der geöffnet wird die Verbindung. Die Kontext-ID jeder Vorgang, der das angegebene Objekt zugeordnet ist, und identifiziert den Vorgang vom zurückgegebenen Statusinformationen [CInternetSession:: OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Weitere Informationen dazu, wie **GetContext** funktioniert mit anderen WinInet-Klassen so erteilen Sie die Benutzerinformationen zum clientinstallationsstatus finden Sie im Artikel [Internetgrundlagen: WinInet](../../mfc/wininet-basics.md) für Weitere Informationen über den Kontext Der Bezeichner.  
  
##  <a name="getservername"></a>  CInternetConnection::GetServerName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Servers, der dieser Internet-Verbindung zugeordnet.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Servers ist mit dieser Verbindungsobjekt arbeiten.  
  
##  <a name="getsession"></a>  CInternetConnection::GetSession  
 Rufen Sie diese Memberfunktion zum Abrufen eines Zeigers auf die `CInternetSession` -Objekt, das dieser Verbindung zugeordnet ist.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine [CInternetSession](../../mfc/reference/cinternetsession-class.md) Objekt, das mit diesem Internet Connection-Objekt zugeordnet.  
  
##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET  
 Verwenden Sie diesen Operator, um das Handle für die API-Ebene für die aktuelle Sitzung mit Internet abzurufen.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



