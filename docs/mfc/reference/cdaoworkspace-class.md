---
title: CDaoWorkspace Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoWorkspace
- AFXDAO/CDaoWorkspace
- AFXDAO/CDaoWorkspace::CDaoWorkspace
- AFXDAO/CDaoWorkspace::Append
- AFXDAO/CDaoWorkspace::BeginTrans
- AFXDAO/CDaoWorkspace::Close
- AFXDAO/CDaoWorkspace::CommitTrans
- AFXDAO/CDaoWorkspace::CompactDatabase
- AFXDAO/CDaoWorkspace::Create
- AFXDAO/CDaoWorkspace::GetDatabaseCount
- AFXDAO/CDaoWorkspace::GetDatabaseInfo
- AFXDAO/CDaoWorkspace::GetIniPath
- AFXDAO/CDaoWorkspace::GetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::GetLoginTimeout
- AFXDAO/CDaoWorkspace::GetName
- AFXDAO/CDaoWorkspace::GetUserName
- AFXDAO/CDaoWorkspace::GetVersion
- AFXDAO/CDaoWorkspace::GetWorkspaceCount
- AFXDAO/CDaoWorkspace::GetWorkspaceInfo
- AFXDAO/CDaoWorkspace::Idle
- AFXDAO/CDaoWorkspace::IsOpen
- AFXDAO/CDaoWorkspace::Open
- AFXDAO/CDaoWorkspace::RepairDatabase
- AFXDAO/CDaoWorkspace::Rollback
- AFXDAO/CDaoWorkspace::SetDefaultPassword
- AFXDAO/CDaoWorkspace::SetDefaultUser
- AFXDAO/CDaoWorkspace::SetIniPath
- AFXDAO/CDaoWorkspace::SetIsolateODBCTrans
- AFXDAO/CDaoWorkspace::SetLoginTimeout
- AFXDAO/CDaoWorkspace::m_pDAOWorkspace
dev_langs: C++
helpviewer_keywords:
- CDaoWorkspace [MFC], CDaoWorkspace
- CDaoWorkspace [MFC], Append
- CDaoWorkspace [MFC], BeginTrans
- CDaoWorkspace [MFC], Close
- CDaoWorkspace [MFC], CommitTrans
- CDaoWorkspace [MFC], CompactDatabase
- CDaoWorkspace [MFC], Create
- CDaoWorkspace [MFC], GetDatabaseCount
- CDaoWorkspace [MFC], GetDatabaseInfo
- CDaoWorkspace [MFC], GetIniPath
- CDaoWorkspace [MFC], GetIsolateODBCTrans
- CDaoWorkspace [MFC], GetLoginTimeout
- CDaoWorkspace [MFC], GetName
- CDaoWorkspace [MFC], GetUserName
- CDaoWorkspace [MFC], GetVersion
- CDaoWorkspace [MFC], GetWorkspaceCount
- CDaoWorkspace [MFC], GetWorkspaceInfo
- CDaoWorkspace [MFC], Idle
- CDaoWorkspace [MFC], IsOpen
- CDaoWorkspace [MFC], Open
- CDaoWorkspace [MFC], RepairDatabase
- CDaoWorkspace [MFC], Rollback
- CDaoWorkspace [MFC], SetDefaultPassword
- CDaoWorkspace [MFC], SetDefaultUser
- CDaoWorkspace [MFC], SetIniPath
- CDaoWorkspace [MFC], SetIsolateODBCTrans
- CDaoWorkspace [MFC], SetLoginTimeout
- CDaoWorkspace [MFC], m_pDAOWorkspace
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: "24"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 96cc8325ce8084d62f05283b424ead222bc55dd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace-Klasse
Verwaltet eine benannte, kennwortgeschützte Datenbanksitzung eines einzelnen Benutzers von der Anmeldung bis zu Abmeldung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Erstellt ein Arbeitsbereichsobjekt im. Rufen Sie anschließend **erstellen** oder **öffnen**.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|Fügt einen neu erstellten Arbeitsbereich an die Datenbank-Engine-arbeitsbereicheauflistung an.|  
|[CDaoWorkspace::BeginTrans](#begintrans)|Beginnt eine neue Transaktion, die für alle Datenbanken, die im Arbeitsbereich öffnen gilt.|  
|[CDaoWorkspace::Close](#close)|Schließt den Arbeitsbereich und aller darin enthaltenen Objekte. Ausstehende Transaktionen ein Rollback ausgeführt.|  
|[CDaoWorkspace::](#committrans)|Schließt die aktuelle Transaktion ab und speichert die Änderungen.|  
|[CDaoWorkspace:: CompactDatabase](#compactdatabase)|Eine Datenbank komprimiert (oder dupliziert).|  
|[CDaoWorkspace:: Create](#create)|Erstellt ein neues Objekt des DAO-Arbeitsbereich.|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Gibt die Anzahl von DAO-Datenbankobjekten in den Arbeitsbereich datenbankauflistung zurück.|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Gibt Informationen zu einer angegebenen DAO-Datenbank, die in den Arbeitsbereich datenbankauflistung definiert.|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Gibt den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung-Einstellungen in der Windows-Registrierung zurück.|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Gibt einen Wert, der angibt, ob mehrere Transaktionen, die die ODBC-Datenquelle über isolierte sind mehrere Verbindungen mit der Datenquelle erzwungen.|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Gibt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, melden Sie sich mit einer ODBC-Datenbank zurück.|  
|[CDaoWorkspace::GetName](#getname)|Der benutzerdefinierte Name für die Arbeitsbereichsobjekt zurückgegeben.|  
|[CDaoWorkspace::GetUserName](#getusername)|Gibt zurück, dass der Benutzername angegeben, wenn der Arbeitsbereich erstellt wurde. Dies ist der Name der Besitzer des Arbeitsbereichs.|  
|[CDaoWorkspace::GetVersion](#getversion)|Gibt eine Zeichenfolge mit der Version des Datenbankmoduls, die mit dem Arbeitsbereich verknüpft sind.|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|Gibt die Anzahl der Objekte für DAO-Arbeitsbereich in das Datenbankmodul arbeitsbereicheauflistung zurück.|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Gibt Informationen zu einem angegebenen DAO-Arbeitsbereich in das Datenbankmodul arbeitsbereicheauflistung definiert.|  
|[CDaoWorkspace::Idle](#idle)|Ermöglicht das Datenbankmodul Hintergrundaufgaben ausführen.|  
|[CDaoWorkspace::IsOpen](#isopen)|Gibt, die ungleich NULL, wenn der Arbeitsbereich ist öffnen.|  
|[CDaoWorkspace::Open](#open)|Öffnet explizit eine Arbeitsbereichsobjekt, das DAO-Standardarbeitsbereich zugeordnet.|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Versucht, eine beschädigte Datenbank zu reparieren.|  
|[CDaoWorkspace::Rollback](#rollback)|Beendet die aktuelle Transaktion aus, und die Änderungen nicht gespeichert.|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Legt das Kennwort, das das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt im ohne ein bestimmtes Kennwort erstellt wird.|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Legt den Benutzernamen, den das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt im, ohne einen bestimmten Benutzernamen erstellt wird fest.|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Legt den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung-Einstellungen in der Windows-Registrierung fest.|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Gibt an, ob mehrere Transaktionen, die die ODBC-Datenquelle isoliert werden, indem mehrere Verbindungen mit der Datenquelle zu erzwingen.|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, eine ODBC-Datenquelle anmelden.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|Verweist auf das zugrunde liegende DAO-Arbeitsbereich "-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Klicken Sie in den meisten Fällen benötigen Sie nicht mehrere Arbeitsbereiche, und Sie müssen keine explizite Arbeitsbereichsobjekte zu erstellen; Wenn Sie die Datenbank und Recordset-Objekte öffnen, verwenden sie die DAO-Standardarbeitsbereich. Allerdings können bei Bedarf Sie mehrere Sitzungen zu einem Zeitpunkt ausführen, indem zusätzliche Workspace-Objekte erstellen. Jedes Arbeitsbereichsobjekt im kann mehrere geöffneten Datenbankobjekten in eine eigene Sammlung Datenbanken enthalten. In MFC ist ein Arbeitsbereich in erster Linie eine Transaktions-Manager, eine Reihe von open Datenbanken alle im selben "Transaktionsprotokoll-Speicherplatz" angeben  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben jeweils "CDao"-Präfix. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die MFC-Klassen basierend auf ODBC. Die DAO-basierten Klassen greifen auf Daten über das Microsoft Jet-Datenbankmodul, einschließlich der ODBC-Treiber. Außerdem unterstützen (Data Definition Language, Datendefinitionssprache)-Vorgänge, z. B. das Erstellen von Datenbanken und Hinzufügen von Tabellen und Felder, die über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="capabilities"></a>Funktionen  
 Klasse `CDaoWorkspace` ermöglicht Folgendes:  
  
-   Expliziter Zugriff ggf. zu einem Standardarbeitsbereich erstellt, indem Sie das Datenbankmodul zu initialisieren. In der Regel verwenden Sie die DAO-Standardarbeitsbereich implizit von Datenbank und Recordset-Objekte erstellen.  
  
-   Öffnen Sie im Arbeitsbereich ein Transaktionsprotokoll-Speicherplatz in der Transaktionen für alle Datenbanken angewendet. Sie können zusätzliche Arbeitsbereiche zum Verwalten von Leerzeichen separate Transaktion erstellen.  
  
-   Eine Schnittstelle zu viele Eigenschaften der zugrunde liegenden Microsoft Jet-Datenbankmodul (siehe die statische Memberfunktionen). Öffnen oder erstellen einen Arbeitsbereich Aufrufen einer statischen Memberfunktion vor dem Öffnen zu erstellen, initialisiert das Datenbankmodul.  
  
-   Zugriff auf das Datenbankmodul arbeitsbereicheauflistung, das alle aktiven Arbeitsbereiche speichert, die es angefügt wurden. Sie können auch erstellen und Verwenden von Arbeitsbereichen ohne sie auf die Auflistung angefügt werden.  
  
## <a name="security"></a>Sicherheit  
 MFC implementiert nicht die Sammlungen von Benutzern und Gruppen über DAO, die für die sicherheitssteuerung verwendet werden. Wenn Sie diese Aspekte der DAO benötigen, müssen Sie sie selbst über direkte Aufrufe von DAO-Schnittstellen programmieren. Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="usage"></a>Verwendung  
 Sie können die Klasse `CDaoWorkspace` an:  
  
-   Den Standardarbeitsbereich explizit zu öffnen.  
  
     In der Regel ist die Verwendung der Standardarbeitsbereich implizit — Wenn Sie neue öffnen [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte. Sie können jedoch explizit Zugriff – z. B. in den Eigenschaften des Access-Datenbankmoduls oder die Auflistung der Arbeitsbereiche. Finden Sie unter "Impliziten Verwendung der Standardarbeitsbereich" unten ein.  
  
-   Erstellen Sie neue Arbeitsbereiche. Rufen Sie [Append](#append) Wenn Sie diese auf die Auflistung der Arbeitsbereiche hinzufügen möchten.  
  
-   Öffnen Sie einen vorhandenen Arbeitsbereich, in der Auflistung der Arbeitsbereiche.  
  
 Einen neuen Arbeitsbereich erstellen, die noch nicht vorhanden in den Arbeitsbereichen der Auflistung beschrieben, unter wird der [erstellen](#create) Memberfunktion. Arbeitsbereichsobjekte beibehalten in keiner Weise zwischen Datababase Modul Sitzungen nicht. Wenn Ihre Anwendung MFC statisch verknüpft ist, wird beim Beenden der Anwendung das Datenbankmodul deinitialisiert. Wenn Ihre Anwendung dynamisch mit MFC verknüpft ist, ist das Datenbankmodul nicht initialisiert, wenn die MFC-DLL entladen wird.  
  
 Explizit öffnen den Arbeitsbereich "Standard" oder einen vorhandenen Arbeitsbereich in der Auflistung Arbeitsbereiche öffnen wird beschrieben, unter der [öffnen](#open) Memberfunktion.  
  
 Arbeitsbereich Sitzung beenden, schließen Sie den Arbeitsbereich mit der [schließen](#close) Memberfunktion. **Schließen** schließt alle Datenbanken, die nicht abgeschlossen wurde zuvor Rollback für Transaktionen ohne Commit ausgeführt.  
  
## <a name="transactions"></a>Transaktionen  
 DAO verwaltet Transaktionen auf der Ebene des Arbeitsbereichs. Daher gelten Transaktionen für einen Arbeitsbereich mit mehreren open Datenbanken für alle Datenbanken. Beispielsweise, wenn zwei Datenbanken haben uncommitted Updates und Sie rufen [CommitTrans](#committrans), alle Updates ein Commit ausgeführt werden. Wenn Sie Transaktionen für eine einzelne Datenbank beschränken möchten, benötigen Sie einen separaten Arbeitsbereichsobjekt für sie.  
  
## <a name="implicit-use-of-the-default-workspace"></a>Implizite Verwendung der Standardarbeitsbereich  
 Verwendet MFC-DAO-Standardarbeitsbereich implizit in den folgenden Situationen:  
  
-   Wenn Sie ein neues erstellen `CDaoDatabase` Objekt jedoch nicht durch einen vorhandenen aus `CDaoWorkspace` -Objekt MFC erstellt ein Objekt temporärer Arbeitsbereich für Sie die DAO-Standardarbeitsbereich entspricht. In diesem Fall für mehrere Datenbanken sind alle Datenbankobjekte der Standardarbeitsbereich zugeordnet. Sie erreichen eine Datenbank-Arbeitsbereich, über eine `CDaoDatabase` -Datenmember.  
  
-   Auf ähnliche Weise bei Erstellung einer `CDaoRecordset` Objekt ohne einen Zeiger auf eine `CDaoDatabase` -Objekt MFC wird ein temporäres Objekt erstellt und durch Erweiterung auch ein temporärer Arbeitsbereich-Objekt. Sie können einem Recordset-Datenbank und indirekt den Arbeitsbereich zugreifen, durch eine `CDaoRecordset` -Datenmember.  
  
## <a name="other-operations"></a>Andere Vorgänge  
 Andere Datenbankoperationen werden ebenfalls bereitgestellt, z. B. eine beschädigte Datenbank zu reparieren oder durch das Komprimieren einer Datenbank.  
  
 Weitere Informationen über das Aufrufen von DAO direkt und DAO-Sicherheit, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="append"></a>CDaoWorkspace::Append  
 Rufen Sie diese Memberfunktion auf, nach dem Aufruf [erstellen](#create).  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 **Append** Fügt ein Objekt neu erstellten Arbeitsbereich arbeitsbereicheauflistung für das Datenbankmodul. Arbeitsbereiche beibehalten zwischen Datenbank-Engine-Sitzungen nicht; Sie werden nur im Arbeitsspeicher nicht auf dem Datenträger gespeichert. Sie müssen keinen Arbeitsbereich angefügt werden soll; Wenn Sie nicht der Fall ist, können Sie weiterhin verwenden.  
  
 Ein angefügten Arbeitsbereich bleibt in der Auflistung Arbeitsbereiche in einer aktiven geöffneten Zustand erst nach dem Aufruf der [schließen](#close) Memberfunktion.  
  
 Verwandte Informationen finden Sie im Thema "Append-Methode" DAO-Hilfe.  
  
##  <a name="begintrans"></a>CDaoWorkspace::BeginTrans  
 Rufen Sie diese Memberfunktion zum Initiieren einer Transaktion.  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf **BeginTrans**, Updates, die Sie, um die Struktur der Daten oder Datenbankobjekte vornehmen werden wirksam, wenn Sie die Transaktion ein Commit ausgeführt. Da der Arbeitsbereich ein Leerzeichen Einzeltransaktion definiert wird, gilt die Transaktion alle geöffneten Datenbanken im Arbeitsbereich ab. Es gibt zwei Möglichkeiten, die Transaktion abzuschließen:  
  
-   Rufen Sie die [CommitTrans](#committrans) Memberfunktion versucht, einen commit der Transaktion und Änderungen an der Datenquelle gespeichert.  
  
-   Oder rufen Sie die [Rollback](#rollback) Memberfunktion versucht, die Transaktion abbricht.  
  
 Schließen die Arbeitsbereichsobjekt oder ein Datenbankobjekt, während eine Transaktion ausstehend ist ein Rollback aller anstehende Transaktionen.  
  
 Wenn Sie Transaktionen auf eine ODBC-Datenquelle von Berechtigungen für eine andere ODBC-Datenquelle isolieren möchten, finden Sie unter der [SetIsolateODBCTrans](#setisolateodbctrans) Memberfunktion.  
  
##  <a name="cdaoworkspace"></a>CDaoWorkspace::CDaoWorkspace  
 Erstellt ein `CDaoWorkspace`-Objekt.  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen der C++-Objekt, haben Sie zwei Optionen:  
  
-   Rufen Sie des Objekts [öffnen](#open) Memberfunktion Standardarbeitsbereich öffnen oder ein vorhandenes Objekt in der Auflistung der Arbeitsbereiche zu öffnen.  
  
-   Oder rufen Sie des Objekts [erstellen](#create) Memberfunktion versucht, ein neues Objekt des DAO-Arbeitsbereich zu erstellen. Dies startet explizit eine neue Arbeitsbereich-Sitzung, die Sie zum verweisen kann, über die `CDaoWorkspace` Objekt. Nach dem Aufruf **erstellen**, Sie können Aufrufen [Anfügen](#append) , wenn Sie den Arbeitsbereich des Datenbankmoduls arbeitsbereicheauflistung hinzufügen möchten.  
  
 Finden Sie unter der Übersicht zur Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Informationen, wenn Sie explizit erstellen, müssen eine `CDaoWorkspace` Objekt. In der Regel verwenden Sie Arbeitsbereiche, die implizit erstellt, beim Öffnen einer [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt ohne Angabe eines Arbeitsbereichs oder beim Öffnen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt ohne Angabe eines Datenbankobjekts. MFC-DAO-Objekte, die auf diese Weise erstellt verwenden DAO Standardarbeitsbereich, die einmal erstellt und wiederverwendet wird.  
  
 Um einen Arbeitsbereich und der darin enthaltenen Objekte freizugeben, rufen Sie den des Arbeitsbereichsobjekts [schließen](#close) Memberfunktion.  
  
##  <a name="close"></a>CDaoWorkspace::Close  
 Rufen Sie diese Memberfunktion, um das Arbeitsbereichsobjekt im schließen.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Ein Arbeitsbereichsobjekt öffnen schließen gibt das zugrunde liegende DAO-Objekt und der Arbeitsbereich ist ein Mitglied der arbeitsbereicheauflistung entfernt es aus der Auflistung. Aufrufen von **schließen** gilt als guter Programmierstil.  
  
> [!CAUTION]
>  Ein Arbeitsbereichsobjekt im Schließen schließt alle geöffneten Datenbanken im Arbeitsbereich. Dies führt alle geöffneten Recordsets in den Datenbanken, die ebenfalls geschlossen wird, und alle ausstehenden Änderungen oder Updates ein Rollback. Weitere Informationen finden Sie unter der [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), und [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) Memberfunktionen.  
  
 Arbeitsbereich "-Objekte sind nicht dauerhaft; Sie sind nur vorhanden, während Verweise auf diese vorhanden sind. Dies bedeutet, dass wenn die Datenbank-Engine-Sitzung beendet wird, dem Arbeitsbereich und der datenbankauflistung nicht beibehalten werden. Sie müssen sie erneut auf die nächste Sitzung erstellen, von Ihrem Arbeitsbereich und die Datenbanken erneut zu öffnen.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" DAO-Hilfe.  
  
##  <a name="committrans"></a>CDaoWorkspace::  
 Rufen Sie diese Memberfunktion zum commit einer Transaktion – eine Gruppe von Änderungen und Updates auf eine oder mehrere Datenbanken in den Arbeitsbereich zu speichern.  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einer Reihe von Änderungen an der Datenbank Daten oder die Struktur, beginnend mit einem Aufruf von [BeginTrans](#begintrans). Nach Abschluss die Transaktion entweder commit es oder Rollback (die Änderungen Abbrechen) mit [Rollback](#rollback). Ohne Transaktionen geht standardmäßig werden Updates von Datensätzen sofort ein Commit ausgeführt wurde. Aufrufen von **BeginTrans** Verpflichtung Updates verzögert wird, erst nach dem Aufruf bewirkt, dass **CommitTrans**.  
  
> [!CAUTION]
>  In einem Arbeitsbereich Transaktionen sind immer global für den Arbeitsbereich und sind nicht auf nur eine Datenbank oder ein Recordset beschränkt. Wenn Sie auf mehr als eine Datenbank oder ein Recordset innerhalb einer Arbeitsbereichstransaktion Vorgänge **CommitTrans** Commits alle ausstehenden Updates und **Rollback** alle Vorgänge auf jenen Datenbanken wiederhergestellt und Recordsets.  
  
 Wenn Sie eine Datenbank oder eine ausstehende Transaktionen, die im Arbeitsbereich schließen, werden die Transaktionen alle ein Rollback ausgeführt.  
  
> [!NOTE]
>  Hierbei handelt es sich nicht um ein Zweiphasen-Commit-Mechanismus. Wenn ein Update nicht übernehmen, führt andere weiterhin commit.  
  
##  <a name="compactdatabase"></a>CDaoWorkspace:: CompactDatabase  
 Rufen Sie diese Memberfunktion zum Komprimieren einer angegebenen Microsoft Jet (. MDB)-Datenbank.  
  
```  
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int nOptions = 0);

 
static void PASCAL CompactDatabase(
    LPCTSTR lpszSrcName,  
    LPCTSTR lpszDestName,  
    LPCTSTR lpszLocale,  
    int nOptions,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSrcName`  
 Der Name eines vorhandenen "geschlossen" Datenbank. Es kann ein vollständiger Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Falls der Dateiname eine Erweiterung enthält, müssen Sie es angeben. Wenn Ihr Netzwerk die uniform Namenskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad, z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte Schrägstriche in der Pfadzeichenfolgen erforderlich sind, da "\\" ist die C++-Escape-Zeichen.)  
  
 `lpszDestName`  
 Der vollständige Pfad der komprimierten Datenbank, die Sie erstellen. Sie können auch angeben, einen Netzwerkpfad als mit `lpszSrcName`. Sie können keine der `lpszDestName` Argument an dieselbe Datenbankdatei als `lpszSrcName`.  
  
 `lpszPassword`  
 Ein Kennwort verwendet, wenn eine kennwortgeschützte Datenbank komprimiert werden sollen. Beachten Sie, dass bei Verwendung die Version von `CompactDatabase` , ein Kennwort akzeptiert, müssen Sie alle Parameter angeben. Auch, da dies eine Connect-Parameter ist, es erfordert spezielle Formatierung, wie folgt:; PWD = `lpszPassword`. Zum Beispiel:; PWD = "Zufrieden". (Das führende Semikolon erforderlich ist.)  
  
 `lpszLocale`  
 Ein Zeichenfolgenausdruck, der zur Angabe von Sortierreihenfolge zum Erstellen von `lpszDestName`. Wenn Sie dieses Argument nicht angeben, durch das Akzeptieren des Standardwerts von **DbLangGeneral** (siehe unten), das Gebietsschema der neuen Datenbank ist mit der alten Datenbank identisch. Dabei sind folgende Werte möglich:  
  
- **DbLangGeneral** Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und Modern Spanisch  
  
- **DbLangArabic** Arabisch  
  
- **DbLangCyrillic** Russisch  
  
- **DbLangCzech** Tschechisch  
  
- **DbLangDutch** Niederländisch  
  
- **DbLangGreek** Griechisch  
  
- **DbLangHebrew** Hebräisch  
  
- **DbLangHungarian** Ungarisch  
  
- **DbLangIcelandic** Isländisch  
  
- **DbLangNordic** Nordeuropäische Sprachen (Microsoft Jet-Datenbank-Engine nur Version 1.0)  
  
- **DbLangNorwdan** Norwegisch und Dänisch  
  
- **DbLangPolish** Polnisch  
  
- **DbLangSpanish** Spanisch (traditionell)  
  
- **DbLangSwedfin** Tschechisch und Finnisch  
  
- **DbLangTurkish** Türkisch  
  
 `nOptions`  
 Gibt eine oder mehrere Optionen für die Zieldatenbank `lpszDestName`. Wenn Sie dieses Argument nicht angeben, durch das Akzeptieren des Standardwert der `lpszDestName` hat dieselbe Verschlüsselung und die gleiche Version wie `lpszSrcName`. Sie können Kombinieren der **DbEncrypt** oder **DbDecrypt** Steueroption und eine der Optionen Version mit dem bitweisen OR-Operator. Werte, die einem Datenbankformat verwendet, keine Database Engine Version angeben sind möglich:  
  
- **DbEncrypt** beim Komprimieren der Datenbank zu verschlüsseln.  
  
- **DbDecrypt** beim Komprimieren die Datenbank zu entschlüsseln.  
  
- **dbVersion10** erstellen Sie eine Datenbank, Version 1.0 der Microsoft Jet-Modul beim Komprimieren verwendet.  
  
- **dbVersion11** erstellen Sie eine Datenbank, Version 1.1 der Microsoft Jet-Modul beim Komprimieren verwendet.  
  
- **dbVersion20** erstellen Sie eine Datenbank, Version 2.0 der Microsoft Jet-Modul beim Komprimieren verwendet.  
  
- **dbVersion30** erstellen Sie eine Datenbank, Version 3.0 der Microsoft Jet-Modul beim Komprimieren verwendet.  
  
 Sie können **DbEncrypt** oder **DbDecrypt** in den Optionsargument, um anzugeben, ob zum Verschlüsseln oder die Datenbank zu entschlüsseln, die komprimiert wird. Wenn Sie eine Verschlüsselungskonstante nicht angeben oder wenn Sie beide einschließen **DbDecrypt** und **DbEncrypt**, `lpszDestName` müssen dieselbe Verschlüsselung als `lpszSrcName`. Sie können eine der Konstanten Version im Optionsargument verwenden, um die Version des Datenformats für die komprimierte Datenbank anzugeben. Diese Konstante wirkt sich auf nur die Version des Datenformats `lpszDestName`. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen `lpszDestName` müssen die gleiche Version wie `lpszSrcName`. Können Sie compact `lpszDestName` nur für eine Version, die gleich oder höher als die des `lpszSrcName`.  
  
> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, kann, selbst wenn die Implementierung der Sicherheit für Benutzername und Kennwort, um die binäre Datenträgerdatei direkt zu lesen, aus der Datenbank besteht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie Daten in einer Datenbank ändern, wird die Datenbankdatei kann fragmentiert und verwenden mehr Speicherplatz als erforderlich. Sie sollten in regelmäßigen Abständen, Ihre Datenbank defragmentieren Sie die Datenbankdatei komprimieren. Die komprimierte Datenbank ist in der Regel kleiner. Sie könne auch die Sortierreihenfolge, die Verschlüsselung oder die Version des Datenformats ändern, während Sie kopieren und die Datenbank zu komprimieren.  
  
> [!CAUTION]
>  Die `CompactDatabase` Memberfunktion nicht ordnungsgemäß konvertiert werden, eine vollständige Microsoft Access-Datenbank von einer Version in einen anderen. Es wird nur das Datenformat konvertiert. Microsoft Access-definierten Objekten, z. B. Formulare und Berichte werden nicht konvertiert. Allerdings werden die Daten ordnungsgemäß konvertiert.  
  
> [!TIP]
>  Sie können auch `CompactDatabase` zum Kopieren einer Datenbankdatei.  
  
 Weitere Informationen zum Komprimieren von Datenbanken finden Sie im Thema "CompactDatabase Method" DAO-Hilfe.  
  
##  <a name="create"></a>CDaoWorkspace:: Create  
 Rufen Sie diese Memberfunktion, um ein neues Objekt des DAO-Arbeitsbereich zu erstellen und verknüpfen Sie sie mit der MFC `CDaoWorkspace` Objekt.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge mit bis zu 14 Zeichen, die das neuen Arbeitsbereich-Objekt eindeutig bezeichnet. Sie müssen einen Namen angeben. Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
 *lpszUserName*  
 Der Benutzername des Besitzers des Arbeitsbereichs. Anforderungen, finden Sie unter der `lpszDefaultUser` Parameter an die [SetDefaultUser](#setdefaultuser) Memberfunktion. Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" DAO-Hilfe.  
  
 `lpszPassword`  
 Das Kennwort des neuen Arbeitsbereichs-Objekts. Ein Kennwort kann bis zu 14 Zeichen lang sein und darf Zeichen außer ASCII 0 (null). Kennwörter sind Groß-/Kleinschreibung beachtet. Verwandte Informationen finden Sie im Thema "Password-Eigenschaft" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Der gesamte Erstellungsvorgang ist:  
  
1.  Erstellen einer [CDaoWorkspace](#cdaoworkspace) Objekt.  
  
2.  Rufen Sie des Objekts **erstellen** Memberfunktion um den zugrunde liegenden DAO-Arbeitsbereich zu erstellen. Sie müssen einen Namen angeben.  
  
3.  Rufen Sie optional [Append](#append) , wenn Sie den Arbeitsbereich des Datenbankmoduls arbeitsbereicheauflistung hinzufügen möchten. Sie können mit dem Arbeitsbereich arbeiten, ohne Sie angefügt.  
  
 Nach der **erstellen** Aufruf der, die Arbeitsbereichsobjekt befindet sich im geöffneten Zustand für die Verwendung bereit. Rufen Sie nicht **öffnen** nach **erstellen**. Rufen Sie nicht **erstellen** , wenn der Arbeitsbereich in der Auflistung der Arbeitsbereiche ist bereits vorhanden. **Erstellen Sie** Datenbankmodul initialisiert, wenn es für Ihre Anwendung nicht bereits initialisiert wurde.  
  
##  <a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von DAO-Datenbankobjekten in den Arbeitsbereich datenbankauflistung – die Anzahl der geöffneten Datenbanken im Arbeitsbereich.  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der geöffneten Datenbanken im Arbeitsbereich.  
  
### <a name="remarks"></a>Hinweise  
 `GetDatabaseCount`ist nützlich, wenn alle definierten Datenbanken in den Arbeitsbereich datenbankauflistung durchlaufen werden sollen. Informationen zu einer bestimmten Datenbank in der Auflistung zu erhalten, finden Sie unter [GetDatabaseInfo](#getdatabaseinfo). Typische Verwendung ist, rufen Sie `GetDatabaseCount` für die Anzahl der geöffneten Datenbanken, klicken Sie dann verwenden Sie diese Zahl als Schleifenindex für wiederholte Aufrufe von `GetDatabaseInfo`.  
  
##  <a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo  
 Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen über eine Datenbank geöffnet, in dem Arbeitsbereich zu erhalten.  
  
```  
void GetDatabaseInfo(
    int nIndex,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetDatabaseInfo(
    LPCTSTR lpszName,  
    CDaoDatabaseInfo& dbinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Datenbankobjekts in den Arbeitsbereich datenbankauflistung für die Suche nach Index.  
  
 `dbinfo`  
 Ein Verweis auf eine [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Datenbank abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, aktualisiert werden kann, Transaktionen  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Abfragetimeout Version Reihenfolge sortieren  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: Verbinden  
  
 `lpszName`  
 Der Name des Datenbankobjekts, für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die das neuen Arbeitsbereich-Objekt eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie eine Datenbank über einen Index zu suchen. Die andere Version können Sie anhand des Namens einer Datenbank zu suchen.  
  
 Eine Beschreibung der Informationen zurückgegeben `dbinfo`, finden Sie unter der [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
##  <a name="getinipath"></a>CDaoWorkspace::GetIniPath  
 Rufen Sie diese Memberfunktion um den Speicherort der Microsoft Jet-Datenbank-Engine Initialisierung Einstellungen in der Windows-Registrierung zu erhalten.  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die den Speicherort in der Registrierung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Speicherort zum Abrufen von Informationen zu den Einstellungen für das Datenbankmodul verwenden. Die zurückgegebenen Informationen ist tatsächlich auf den Namen der Unterschlüssel der Registrierung.  
  
 Weitere Informationen finden Sie unter den Themen "IniPath-Eigenschaft" und "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe.  
  
##  <a name="getisolateodbctrans"></a>CDaoWorkspace::GetIsolateODBCTrans  
 Rufen Sie diese Memberfunktion um den aktuellen Wert der Eigenschaft DAO IsolateODBCTrans für den Arbeitsbereich zu erhalten.  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der ODBC-Transaktionen isoliert sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In einigen Situationen müssen Sie möglicherweise mehrere gleichzeitige Transaktionen mit ausstehender für eine ODBC-Datenbank verfügen. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Bedenken Sie, dass jeder Arbeitsbereich eine eigene ODBC-Verbindung mit der Datenbank kann zwar haben, dies die Systemleistung verlangsamt wird. Da der Transaktionsisolation nicht normal erforderlich ist, sind ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.  
  
 Einige ODBC-Server, z. B. Microsoft SQL Server, gestatten keine gleichzeitige Transaktionen über eine einzelne Verbindung. Wenn Sie mehr als eine Transaktion zu einem Zeitpunkt Ausstehend für eine Datenbank dieser Art verfügen müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf **"true"** für jeden Arbeitsbereich, sobald es zu öffnen. Dies erzwingt eine separate ODBC-Verbindung für jeden Arbeitsbereich.  
  
 Verwandte Informationen finden Sie im Thema "IsolateODBCTrans-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getlogintimeout"></a>CDaoWorkspace::GetLoginTimeout  
 Rufen Sie diese Memberfunktion um den aktuellen Wert der DAO-LoginTimeout-Eigenschaft für den Arbeitsbereich zu erhalten.  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sekunden, bevor ein Fehler tritt auf, wenn Sie versuchen, mit einer ODBC-Datenbank anzumelden.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert stellt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, melden Sie sich mit einer ODBC-Datenbank. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Wenn LoginTimeout auf 0 festgelegt ist, kein Timeout tritt auf, und die Kommunikation mit der Datenquelle möglicherweise nicht mehr reagiert.  
  
 Wenn Sie versuchen, die mit einer ODBC-Datenbank, z. B. Microsoft SQL Server, melden Sie sich möglicherweise schlägt die Verbindung aufgrund von Netzwerkfehlern oder weil der Server nicht ausgeführt wird. Anstatt zu warten, des Standardwerts 20 Sekunden eine Verbindung herstellen, können Sie angeben, wie lange das Datenbankmodul wartet, bevor er einen Fehler erzeugt. Anmelden an den Server erfolgt implizit als Teil einer Reihe von verschiedenen Ereignisse, z. B. das Ausführen einer Abfrage auf eine externe Datenbank.  
  
 Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getname"></a>CDaoWorkspace::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen des benutzerdefinierten Namens für den DAO-Arbeitsbereich-Objekt zugrunde liegende der `CDaoWorkspace` Objekt.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , die der benutzerdefinierte Name des DAO-Arbeitsbereichsobjekts enthält.  
  
### <a name="remarks"></a>Hinweise  
 Der Name ist nützlich für den Zugriff auf den Arbeitsbereich DAO-Objekt in das Datenbankmodul arbeitsbereicheauflistung anhand des Namens.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getusername"></a>CDaoWorkspace::GetUserName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Besitzers des Arbeitsbereichs.  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , den Besitzer des Arbeitsbereichsobjekts darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Abrufen oder Festlegen der Berechtigungen für den Besitzer des Arbeitsbereichs, DAO direkt, um die Einstellung der Eigenschaft Berechtigungen zu überprüfen. Dadurch wird bestimmt, welche Berechtigungen dieses Benutzers. Um Berechtigungen zu arbeiten, benötigen Sie ein SYSTEM aus. MDA-Datei.  
  
 Informationen zum Aufrufen von DAO direkt, finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getversion"></a>CDaoWorkspace::GetVersion  
 Rufen Sie diese Memberfunktion zum Ermitteln der Version von Microsoft Jet-Datenbankmodul verwendet.  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der die Version des Datenbankmoduls, die mit dem Objekt verbundenen angibt.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert stellt die Versionsnummer im Format "größer.kleiner"; beispielsweise "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und die Versionsnummer (0).  
  
 Verwandte Informationen finden Sie im Thema "Version-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getworkspacecount"></a>CDaoWorkspace::GetWorkspaceCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von DAO-Arbeitsbereich Objekten in das Datenbankmodul arbeitsbereicheauflistung.  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der geöffneten Arbeitsbereiche in der Auflistung der Arbeitsbereiche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Anzahl umfasst keine geöffneten Arbeitsbereiche nicht auf die Auflistung angefügt. `GetWorkspaceCount`ist nützlich, wenn alle definierten Arbeitsbereiche in der Auflistung der Arbeitsbereiche durchlaufen werden sollen. Informationen zu einem bestimmten Arbeitsbereich in der Auflistung zu erhalten, finden Sie unter [GetWorkspaceInfo](#getworkspaceinfo). Typische Verwendung ist, rufen Sie `GetWorkspaceCount` für die Anzahl der geöffneten Arbeitsbereiche, dann verwenden Sie diese Zahl als Schleifenindex für wiederholte Aufrufe von `GetWorkspaceInfo`.  
  
##  <a name="getworkspaceinfo"></a>CDaoWorkspace::GetWorkspaceInfo  
 Rufen Sie diese Memberfunktion, um verschiedene Arten von Informationen über einen Arbeitsbereich öffnen, in der Sitzung zu erhalten.  
  
```  
void GetWorkspaceInfo(
    int nIndex,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetWorkspaceInfo(
    LPCTSTR lpszName,  
    CDaoWorkspaceInfo& wkspcinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Datenbankobjekts in der Auflistung Arbeitsbereiche für die Suche nach Index.  
  
 `wkspcinfo`  
 Ein Verweis auf eine [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über den Arbeitsbereich abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Benutzername  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: ODBCTrans isolieren  
  
 `lpszName`  
 Der Name des Arbeitsbereichsobjekts im für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die das neuen Arbeitsbereich-Objekt eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `wkspcinfo`, finden Sie unter der [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen zu vorherigen Ebenen sowie an.  
  
##  <a name="idle"></a>CDaoWorkspace::Idle  
 Rufen Sie **Leerlauf** bereitzustellen, das Datenbankmodul die Möglichkeit zum Ausführen von Hintergrundaufgaben, die aufgrund von intensiver Datenverarbeitung möglicherweise nicht auf dem neuesten Stand.  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>Parameter  
 `nAction`  
 Aktion bei der Verarbeitung im Leerlauf ausgeführt werden soll. Derzeit die einzigen gültige Aktion ist **DbFreeLocks**.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist häufig in, Multitasking mehrbenutzerumgebungen in der ist nicht genügend Hintergrundverarbeitungszeit, um alle Datensätze in einem Recordset aktuell zu halten.  
  
> [!NOTE]
>  Aufrufen von **Leerlauf** ist mit Datenbanken mit Version 3.0 der Microsoft Jet-Datenbankmodul nicht erforderlich. Verwendung **Leerlauf** nur für Datenbanken, die mit früheren Versionen erstellt wurden.  
  
 In der Regel lesen, die Sperren aufgehoben werden und Daten im lokalen Dynaset-Type-Recordset-Objekte aktualisiert wird nur verwendet werden, wenn keine anderen Aktionen (einschließlich mausbewegungen) auftreten. Wenn Sie in regelmäßigen Abständen Aufrufen **Leerlauf**, Sie geben das Datenbankmodul mit Hintergrundprozesse Aufgaben freigibt, dessen Stand zu nicht benötigte Sperren lesen. Angeben der **DbFreeLocks** Konstante als Argument verzögert verarbeitet werden, bevor alle Lesesperren freigegeben werden.  
  
 Diese Memberfunktion ist nicht im Einzelbenutzermodus Umgebungen erforderlich, wenn mehrere Instanzen einer Anwendung ausgeführt werden. Die **Leerlauf** Memberfunktion kann Leistung in einer mehrbenutzerumgebung erhöhen, da es erzwingt, dass das Datenbankmodul beim Leeren der Daten auf den Datenträger, die Freigabe von Sperren für den Arbeitsspeicher. Sie können auch Lesesperren freigeben, indem Sie Vorgänge Teil einer Transaktion vornehmen.  
  
 Verwandte Informationen finden Sie im Thema "Im Leerlauf Method" DAO-Hilfe.  
  
##  <a name="isopen"></a>CDaoWorkspace::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoWorkspace` -Objekts geöffnet ist – d. h., ob das MFC-Objekt durch einen Aufruf von initialisiert wurde [öffnen](#open) oder einen Aufruf von [erstellen](#create).  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Arbeitsbereichsobjekt im geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können keine der Memberfunktionen eines Arbeitsbereichs Funktionen aufrufen, die im geöffneten Zustand ist.  
  
##  <a name="m_pdaoworkspace"></a>CDaoWorkspace::m_pDAOWorkspace  
 Ein Zeiger auf das zugrunde liegende DAO-Arbeitsbereich "-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Datenelement aus, wenn Sie den Zugriff auf das zugrunde liegende DAO-Objekt weiterleiten müssen. Sie können die DAO-Objekt Schnittstellen über diesem Zeiger aufrufen.  
  
 Informationen zum direkten Zugriff auf DAO-Objekten finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="open"></a>CDaoWorkspace::Open  
 Öffnet explizit eine Arbeitsbereichsobjekt, das DAO-Standardarbeitsbereich zugeordnet.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Objekts die DAO-Arbeitsbereich zu öffnen, eine Zeichenfolge mit bis zu 14 Zeichen, die den Arbeitsbereich eindeutig bezeichnet. Akzeptieren Sie den Standardwert **NULL** Standardarbeitsbereich explizit zu öffnen. Benennungsanforderungen, finden Sie unter der `lpszName` -Parameter für [erstellen](#create). Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CDaoWorkspace` Objekt, das mit dieser Memberfunktion können Sie eine der folgenden Aktionen ausführen:  
  
-   Den Standardarbeitsbereich explizit zu öffnen. Übergeben Sie **NULL** für `lpszName`.  
  
-   Öffnen Sie ein vorhandenes `CDaoWorkspace` -Objekt, ein Mitglied der Arbeitsbereiche-Auflistung nach Namen. Übergeben Sie einen gültigen Namen für ein vorhandenes Arbeitsbereichsobjekt ein.  
  
 **Öffnen Sie** Workspace-Objekts in einem geöffneten Status versetzt, und auch das Datenbankmodul initialisiert, wenn es für Ihre Anwendung nicht bereits initialisiert wurde.  
  
 Obwohl viele `CDaoWorkspace` Member Funktionen können nur aufgerufen werden, nachdem der Arbeitsbereich geöffnet wurde, die folgenden Memberfunktionen, die über das Datenbankmodul ausgeführt werden, stehen nach der Erstellung der C++-Objekt, aber vor einem Aufruf von **öffnen** :  
  
||||  
|-|-|-|  
|[Erstellen](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[Im Leerlauf](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="repairdatabase"></a>CDaoWorkspace::RepairDatabase  
 Rufen Sie diese Memberfunktion auf, wenn Sie versuchen, eine beschädigte Datenbank zu reparieren, die das Microsoft Jet-Datenbankmodul greift auf müssen.  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Pfad und Dateiname für eine vorhandene Microsoft Jet-Datenbankmodul-Datenbankdatei. Wenn Sie den Pfad angeben, wird nur das aktuelle Verzeichnis durchsucht. Wenn Ihr System die uniform Namenskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad wie z. B.: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelten umgekehrten Schrägstriche sind in der Path-Zeichenfolge erforderlich, da "\\" ist die C++-Escape-Zeichen.)  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen durch den angegebenen Datenbank schließen `lpszName` , bevor Sie es zu reparieren. In einer mehrbenutzerumgebung sind andere Benutzer keine `lpszName` öffnen, während Sie es repariert werden. Wenn `lpszName` nicht geschlossen oder ist nicht verfügbar für die ausschließliche Verwendung ein Fehler auftritt.  
  
 Diese Memberfunktion versucht, eine Datenbank zu reparieren, die durch einen unvollständigen Schreibvorgang möglicherweise als beschädigt markiert wurde. Dies kann auftreten, wenn eine Anwendung mithilfe der Microsoft Jet-Datenbankmodul wegen eines Problems Power Netzwerkausfall oder einem Hardware unerwartet geschlossen wird. Wenn Sie den Vorgang und der Aufruf abgeschlossen der [schließen](../../mfc/reference/cdaodatabase-class.md#close) Memberfunktion oder beenden Sie die Anwendung auf eine übliche Weise, die Datenbank wird nicht als möglicherweise beschädigt gekennzeichnet werden.  
  
> [!NOTE]
>  Reparieren Sie eine Datenbank, und es ist auch eine gute Idee, komprimieren sie mithilfe der [CompactDatabase](#compactdatabase) Member-Funktion, um die Datei zu defragmentieren und Speicherplatz zu gewinnen.  
  
 Weitere Informationen zum Reparieren von Datenbanken finden Sie im Thema "RepairDatabase Method" DAO-Hilfe.  
  
##  <a name="rollback"></a>CDaoWorkspace::Rollback  
 Rufen Sie diese Memberfunktion, um die aktuelle Transaktion zu beenden und alle Datenbanken in den Arbeitsbereich, deren Bedingung wiederherstellen, bevor die Transaktion gestartet wurde.  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  In einem Arbeitsbereichsobjekt Transaktionen sind immer global für den Arbeitsbereich und sind nicht auf nur eine Datenbank oder ein Recordset beschränkt. Wenn Sie auf mehr als eine Datenbank oder ein Recordset innerhalb einer Arbeitsbereichstransaktion Vorgänge **Rollback** alle Vorgänge für alle diese Datenbanken und Recordsets wiederhergestellt.  
  
 Wenn Sie ein Arbeitsbereichsobjekt im schließen, ohne zu speichern oder ein Rollback aller anstehenden Transaktionen, werden die Transaktionen automatisch zurückgesetzt. Beim Aufrufen [CommitTrans](#committrans) oder **Rollback** erst nach Aufrufen von [BeginTrans](#begintrans), ein Fehler auftritt.  
  
> [!NOTE]
>  Wenn Sie eine Transaktion zu beginnen, zeichnet das Datenbankmodul seine Vorgänge in einer Datei, die in das Verzeichnis, angegeben durch die Umgebungsvariable "TEMP" auf der Arbeitsstation gespeichert. Wenn die Transaktionsprotokolldatei den verfügbaren Speicher auf dem TEMPORÄREN Laufwerk ausgeschöpft hat, verursacht das Datenbankmodul MFC ermöglicht, lösen eine `CDaoException` (DAO-Fehler 2004). An diesem Punkt ist beim Aufrufen **CommitTrans**, eine unbestimmte Anzahl von Vorgängen wird ein Commit ausgeführt, aber die verbleibenden unvollständigen Vorgänge verloren, und der Vorgang wurde neu gestartet werden. Aufrufen von **Rollback** frei das Transaktionsprotokoll und ein Rollback für alle Vorgänge aus, in der Transaktion.  
  
##  <a name="setdefaultpassword"></a>CDaoWorkspace::SetDefaultPassword  
 Rufen Sie diese Memberfunktion, um das Standardkennwort festzulegen, das das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt im ohne ein bestimmtes Kennwort erstellt wird.  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPassword`  
 Das Standardkennwort. Ein Kennwort kann bis zu 14 Zeichen lang sein und darf Zeichen außer ASCII 0 (null). Kennwörter sind Groß-/Kleinschreibung beachtet.  
  
### <a name="remarks"></a>Hinweise  
 Das Standardkennwort, das Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf zu erstellen. Wenn Sie nachfolgende Arbeitsbereiche erstellen, müssen Sie nicht Geben Sie ein Kennwort in die [erstellen](#create) aufrufen.  
  
 So verwenden Sie diese Memberfunktion auf:  
  
1.  Erstellen einer `CDaoWorkspace` -Objekt rufen Sie jedoch nicht **erstellen**.  
  
2.  Rufen Sie `SetDefaultPassword` und, falls gewünscht, [SetDefaultUser](#setdefaultuser).  
  
3.  Rufen Sie **erstellen** für dieses Arbeitsbereichsobjekt oder nachfolgender Felder ohne Angabe eines Kennworts.  
  
 Standardmäßig die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die DefaultPassword-Eigenschaft wird festgelegt, auf eine leere Zeichenfolge ("").  
  
 Weitere Informationen zur Sicherheit finden Sie im Thema "Berechtigungen Property" in der DAO-Hilfe. Weitere Informationen finden Sie unter den Themen "DefaultPassword-Eigenschaft" und "DefaultUser Property" in der DAO-Hilfe.  
  
##  <a name="setdefaultuser"></a>CDaoWorkspace::SetDefaultUser  
 Rufen Sie diese Memberfunktion um den Standardbenutzernamen festzulegen, den das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt ohne einen bestimmten Benutzernamen erstellt wird.  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDefaultUser`  
 Der Standardname für die Benutzer. Ein Benutzername kann 1 bis 20 Zeichen lang sein und Buchstaben, Zeichen mit Akzenten, Zahlen, Leerzeichen und Symbole mit Ausnahme von: "(Anführungszeichen) / (Schrägstrich), \ (umgekehrter Schrägstrich), \[ \] (Klammern): (Doppelpunkt) &#124; (senkrechter Strich), \< (kleiner-als-Zeichen), > (größer-als-Zeichen), + (Pluszeichen) = (Gleichheitszeichen), Semikolon (;), (Komma), (Fragezeichen) * (Sternchen), führende Leerzeichen und Steuerzeichen (ASCII 00 und ASCII-31). Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Der Standardname für den Benutzer, die Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf erstellen. Wenn Sie nachfolgende Arbeitsbereiche erstellen, müssen Sie keinen Benutzernamen im Angeben der [erstellen](#create) aufrufen.  
  
 So verwenden Sie diese Memberfunktion auf:  
  
1.  Erstellen einer `CDaoWorkspace` -Objekt rufen Sie jedoch nicht **erstellen**.  
  
2.  Rufen Sie `SetDefaultUser` und, falls gewünscht, [SetDefaultPassword](#setdefaultpassword).  
  
3.  Rufen Sie **erstellen** für dieses Arbeitsbereichsobjekt oder nachfolgender Felder, ohne einen Benutzernamen anzugeben.  
  
 Standardmäßig die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die DefaultPassword-Eigenschaft wird festgelegt, auf eine leere Zeichenfolge ("").  
  
 Weitere Informationen finden Sie unter den Themen "DefaultUser-Eigenschaft" und "DefaultPassword-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setinipath"></a>CDaoWorkspace::SetIniPath  
 Rufen Sie diese Memberfunktion zum Angeben des Speicherorts der Windows-registrierungseinstellungen für das Microsoft Jet-Datenbankmodul.  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszRegistrySubkey*  
 Eine Zeichenfolge mit dem Namen des ein Windows-Registrierungsunterschlüssel für den Speicherort der Microsoft Jet-Datenbank-Engine-Einstellungen oder Parameter für installierbare ISAM-Datenbanken erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetIniPath` nur, wenn Sie spezielle Einstellungen angeben müssen. Weitere Informationen finden Sie im Thema "IniPath-Eigenschaft" DAO-Hilfe.  
  
> [!NOTE]
>  Rufen Sie `SetIniPath` während der Anwendungsinstallation, nicht wenn die Anwendung ausgeführt wird. `SetIniPath`muss aufgerufen werden, bevor Sie alle Arbeitsbereiche, Datenbanken oder Recordsets öffnen. Andernfalls löst MFC eine Ausnahme aus.  
  
 Sie können diesen Mechanismus verwenden, so konfigurieren Sie das Datenbankmodul mit vom Benutzer bereitgestellte registrierungseinstellungen. Der Gültigkeitsbereich dieses Attributs ist auf die Anwendung beschränkt und kann nicht geändert werden, ohne Ihre Anwendung neu zu starten.  
  
##  <a name="setisolateodbctrans"></a>CDaoWorkspace::SetIsolateODBCTrans  
 Rufen Sie diese Memberfunktion um den Wert der Eigenschaft für den Arbeitsbereich DAO IsolateODBCTrans festzulegen.  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>Parameter  
 *bIsolateODBCTrans*  
 Übergeben Sie **"true"** beginnen, Isolieren von ODBC-Transaktionen werden sollen. Übergeben Sie **"false"** Wenn Isolieren von ODBC-Transaktionen beendet werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 In einigen Situationen müssen Sie möglicherweise mehrere gleichzeitige Transaktionen mit ausstehender für eine ODBC-Datenbank verfügen. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Obwohl jeder Arbeitsbereich eine eigene ODBC-Verbindung mit der Datenbank aufweisen kann, wird dadurch die Systemleistung. Da der Transaktionsisolation nicht normal erforderlich ist, sind ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.  
  
 Einige ODBC-Server, z. B. Microsoft SQL Server, gestatten keine gleichzeitige Transaktionen über eine einzelne Verbindung. Wenn Sie mehr als eine Transaktion zu einem Zeitpunkt Ausstehend für eine Datenbank dieser Art verfügen müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf **"true"** für jeden Arbeitsbereich, sobald es zu öffnen. Dies erzwingt eine separate ODBC-Verbindung für jeden Arbeitsbereich.  
  
##  <a name="setlogintimeout"></a>CDaoWorkspace::SetLoginTimeout  
 Rufen Sie diese Memberfunktion um den Wert der DAO-LoginTimeout-Eigenschaft für den Arbeitsbereich festzulegen.  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `nSeconds`  
 Die Anzahl der Sekunden, bevor ein Fehler tritt auf, wenn Sie versuchen, mit einer ODBC-Datenbank anzumelden.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert stellt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, melden Sie sich mit einer ODBC-Datenbank. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Wenn LoginTimeout auf 0 festgelegt ist, kein Timeout tritt auf, und die Kommunikation mit der Datenquelle möglicherweise nicht mehr reagiert.  
  
 Wenn Sie versuchen, die mit einer ODBC-Datenbank, z. B. Microsoft SQL Server, melden Sie sich möglicherweise schlägt die Verbindung aufgrund von Netzwerkfehlern oder weil der Server nicht ausgeführt wird. Anstatt zu warten, des Standardwerts 20 Sekunden eine Verbindung herstellen, können Sie angeben, wie lange das Datenbankmodul wartet, bevor er einen Fehler erzeugt. Mit dem Server anmelden erfolgt implizit als Teil einer Reihe von verschiedenen Ereignisse, z. B. das Ausführen einer Abfrage auf eine externe Datenbank. Der Timeoutwert wird durch die aktuelle Einstellung der LoginTimeout-Eigenschaft bestimmt.  
  
 Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)
