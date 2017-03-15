---
title: CDaoWorkspace Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoWorkspace
dev_langs:
- C++
helpviewer_keywords:
- DAO workspaces [C++]
- transaction spaces [C++], DAO workspace
- ODBC classes [C++], vs. DAO classes
- default workspaces [C++], DAO
- workspaces [C++], DAO
- sessions [C++], DAO workspace
- Workspace class
- CDaoWorkspace class
- workspaces [C++], interface to database engine
- Workspaces collection
- persistence [C++], DAO workspace
- workspaces [C++], default
- defaults [C++], workspaces
- DAO workspaces [C++], CDaoWorkspace class
- security [MFC], DAO workspaces
- security [MFC]
- database engine [C++], accessing via workspace
- transaction spaces [C++]
- DDLs [C++]
- workspaces [C++], persistence
- default workspaces [C++]
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
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
ms.openlocfilehash: 5d7f9aea6fa4913641bc92662b3cf5dfeaddb9d8
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspace-class"></a>CDaoWorkspace-Klasse
Verwaltet eine benannte, kennwortgeschützte Datenbanksitzung eines einzelnen Benutzers von der Anmeldung bis zu Abmeldung.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](#cdaoworkspace)|Erstellt ein Workspace-Objekt. Rufen Sie anschließend **erstellen** oder **öffnen**.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::Append](#append)|Fügt einen neu erstellten Arbeitsbereich des Datenbankmoduls arbeitsbereicheauflistung an.|  
|[CDaoWorkspace::BeginTrans](#begintrans)|Beginnt eine neue Transaktion, die für alle Datenbanken, die in den Arbeitsbereich öffnen gilt.|  
|[CDaoWorkspace::Close](#close)|Schließt den Arbeitsbereich und alle darin enthaltenen Objekte. Ausstehende Transaktionen ein Rollback ausgeführt.|  
|[CDaoWorkspace::](#committrans)|Schließt die aktuelle Transaktion ab und speichert die Änderungen.|  
|[CDaoWorkspace:: CompactDatabase](#compactdatabase)|Eine Datenbank komprimiert (oder dupliziert).|  
|[CDaoWorkspace:: Create](#create)|Erstellt ein neues Objekt des DAO-Arbeitsbereich.|  
|[CDaoWorkspace::GetDatabaseCount](#getdatabasecount)|Gibt die Anzahl der Datenbankobjekte DAO in den Arbeitsbereich datenbankauflistung zurück.|  
|[CDaoWorkspace::GetDatabaseInfo](#getdatabaseinfo)|Gibt Informationen zu einer angegebenen DAO-Datenbank in den Arbeitsbereich Databases-Auflistung definiert.|  
|[CDaoWorkspace::GetIniPath](#getinipath)|Gibt den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung Einstellungen in der Windows-Registrierung zurück.|  
|[CDaoWorkspace::GetIsolateODBCTrans](#getisolateodbctrans)|Gibt einen Wert, der angibt, ob mehrere Transaktionen, die die ODBC-Datenquelle über isoliert sind mehrere Verbindungen zur Datenquelle erzwungen.|  
|[CDaoWorkspace::GetLoginTimeout](#getlogintimeout)|Gibt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, sich an eine ODBC-Datenbank anzumelden.|  
|[CDaoWorkspace::GetName](#getname)|Der benutzerdefinierte Name für die Workspace-Objekt zurückgegeben.|  
|[CDaoWorkspace::GetUserName](#getusername)|Gibt der Benutzernamen zurück, wenn der Arbeitsbereich erstellt wurde. Dies ist der Name des Besitzers des Arbeitsbereichs.|  
|[CDaoWorkspace::GetVersion](#getversion)|Gibt eine Zeichenfolge mit der Version des Datenbankmoduls, die dem Arbeitsbereich zugeordnet.|  
|[CDaoWorkspace::GetWorkspaceCount](#getworkspacecount)|Gibt die Anzahl der Objekte für DAO-Arbeitsbereich in die Datenbank-Engine arbeitsbereicheauflistung zurück.|  
|[CDaoWorkspace::GetWorkspaceInfo](#getworkspaceinfo)|Gibt Informationen zu einem angegebenen DAO-Arbeitsbereich in die Datenbank-Engine-arbeitsbereicheauflistung definiert.|  
|[CDaoWorkspace::Idle](#idle)|Ermöglicht das Datenbankmodul Hintergrundaufgaben ausführen.|  
|[CDaoWorkspace::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn der Arbeitsbereich öffnen.|  
|[CDaoWorkspace::Open](#open)|Explizit öffnet ein Workspace-Objekt, das DAO-Standardarbeitsbereich zugeordnet.|  
|[CDaoWorkspace::RepairDatabase](#repairdatabase)|Versucht, eine beschädigte Datenbank zu reparieren.|  
|[CDaoWorkspace::Rollback](#rollback)|Beendet die aktuelle Transaktion, und die Änderungen nicht gespeichert.|  
|[CDaoWorkspace::SetDefaultPassword](#setdefaultpassword)|Legt das Kennwort, das das Datenbankmodul verwendet, wenn ein Workspace-Objekt ohne ein bestimmtes Kennwort erstellt wird.|  
|[CDaoWorkspace::SetDefaultUser](#setdefaultuser)|Legt den Benutzernamen, den das Datenbankmodul verwendet, wenn ein Workspace-Objekt, ohne einen bestimmten Benutzernamen erstellt wird fest.|  
|[CDaoWorkspace::SetIniPath](#setinipath)|Legt den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung Einstellungen in der Windows-Registrierung fest.|  
|[CDaoWorkspace::SetIsolateODBCTrans](#setisolateodbctrans)|Gibt an, ob mehrere Transaktionen, die die ODBC-Datenquelle isoliert werden, indem mehrere Verbindungen an die Datenquelle zu erzwingen.|  
|[CDaoWorkspace::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn der Benutzer versucht, sich mit einer ODBC-Datenquelle anzumelden.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoWorkspace::m_pDAOWorkspace](#m_pdaoworkspace)|Verweist auf das zugrunde liegende DAO-Workspace-Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 In den meisten Fällen brauchen Sie mehrere Arbeitsbereiche, und Sie müssen keine explizite Workspace-Objekte zu erstellen; Wenn Sie die Datenbank und Recordset-Objekte öffnen, verwenden sie DAO-Standardarbeitsbereich. Allerdings können bei Bedarf Sie mehrere Sitzungen gleichzeitig ausführen, indem zusätzliche Workspace-Objekte erstellen. Jeder Arbeitsbereichsobjekt kann mehrere geöffneten Datenbankobjekten in seine eigene Sammlung von Datenbanken enthalten. In MFC ist ein Arbeitsbereich in erster Linie ein Transaktions-Manager, eine Reihe von geöffneten Datenbanken angeben, alle in der "Transaktionsbereich."  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben eine "CDao"-Präfix. Im Allgemeinen sind die MFC-Klassen basierend auf DAO leistungsfähiger als die ODBC-basierten MFC-Klassen. DAO-basierte Klassen greifen auf Daten über das Microsoft Jet-Datenbankmodul, einschließlich der ODBC-Treiber. Außerdem unterstützen (Data Definition Language, Datendefinitionssprache) Vorgänge wie das Erstellen von Datenbanken und Hinzufügen von Tabellen und Felder, die über die Klassen ohne DAO direkt aufrufen.  
  
## <a name="capabilities"></a>Funktionen  
 Klasse `CDaoWorkspace` ermöglicht Folgendes:  
  
-   Explizite Zugriff, falls erforderlich, um ein Standardarbeitsbereich von Initialisieren des Datenbankmoduls erstellt. In der Regel verwenden Sie DAO-Standardarbeitsbereich implizit durch das Erstellen der Datenbank und Recordset-Objekte.  
  
-   Öffnen Sie im Arbeitsbereich ein Transaktionsbereich, in dem Transaktionen für alle Datenbanken angewendet. Sie können zusätzliche Arbeitsbereiche zum Verwalten von separate Transaktionsbereiche erstellen.  
  
-   Eine Schnittstelle zu viele Eigenschaften von der zugrunde liegenden Microsoft Jet-Datenbankmodul (siehe die statischen Memberfunktionen). Öffnen oder Erstellen eines Arbeitsbereichs oder Aufrufen einer statischen Memberfunktion vor dem Öffnen zu erstellen, das Datenbankmodul initialisiert.  
  
-   Zugriff auf die Datenbank-Engine-Arbeitsbereiche-Auflistung, die alle aktiven Workspaces gespeichert werden, die es angefügt wurden. Sie können auch erstellen und Verwenden von Arbeitsbereichen ohne auf die Auflistung anfügen.  
  
## <a name="security"></a>Sicherheit  
 MFC implementiert nicht die Sammlungen von Benutzern und Gruppen in DAO, die für die Sicherheitskontrolle verwendet werden. Wenn Sie diese Aspekte von DAO benötigen, müssen Sie sie selbst über direkte Aufrufe von DAO-Schnittstellen programmieren. Weitere Informationen finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="usage"></a>Verwendung  
 Sie können die Klasse `CDaoWorkspace` an:  
  
-   Öffnen Sie den Standardarbeitsbereich explizit.  
  
     In der Regel ist die Verwendung des Standardarbeitsbereichs implizit – beim Öffnen einer neuen [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekte. Müssen Sie jedoch möglicherweise explizit Zugriff – beispielsweise, um die Eigenschaften des Datenbankmoduls Zugriff oder die Auflistung der Arbeitsbereiche. "Implizite Verwendung des Standardarbeitsbereichs" unten.  
  
-   Erstellen Sie neue Arbeitsbereiche. Rufen Sie [Append](#append) Wenn sie arbeitsbereicheauflistung hinzugefügt werden soll.  
  
-   Öffnen Sie einen vorhandenen Arbeitsbereich in der Auflistung der Arbeitsbereiche.  
  
 Einen neuen Arbeitsbereich erstellen, die bereits existiert nicht in den Arbeitsbereichen der Auflistung unter beschrieben wird die [erstellen](#create) Member-Funktion. Workspace-Objekte beibehalten in keiner Weise zwischen Datababase Engine Sitzungen nicht. Wenn Ihre Anwendung MFC statisch verknüpft ist, wird durch das Beenden der Anwendung das Datenbankmodul deinitialisiert. Wenn Ihre Anwendung dynamisch mit MFC verknüpft wird, ist die Datenbank-Engine nicht initialisiert, wenn die MFC-DLL entladen wird.  
  
 Explizit Öffnen des Standardarbeitsbereichs, oder öffnen einen vorhandenen Arbeitsbereich in der Auflistung Arbeitsbereiche wird beschrieben, unter der [öffnen](#open) Member-Funktion.  
  
 Arbeitsbereich Sitzung beenden, schließen Sie den Arbeitsbereich mit der [schließen](#close) Member-Funktion. **Schließen** schließt alle Datenbanken, die nicht abgeschlossen wurde zuvor Rollback für Transaktionen ohne Commit ausgeführt.  
  
## <a name="transactions"></a>Transaktionen  
 DAO verwaltet Transaktionen auf die Arbeitsbereich-Ebene. Daher gelten Transaktionen in einem Arbeitsbereich mit mehreren geöffneten Datenbanken für alle Datenbanken. Z. B. wenn zwei Datenbanken haben uncommitted Updates und Sie rufen [CommitTrans](#committrans), alle Updates wird ein Commit ausgeführt. Wenn Sie Transaktionen mit einer einzelnen Datenbank beschränken möchten, benötigen Sie ein eigenes Workspace-Objekt für sie.  
  
## <a name="implicit-use-of-the-default-workspace"></a>Implizite Verwendung des Standardarbeitsbereichs  
 Verwendet MFC-DAO-Standardarbeitsbereich implizit in den folgenden Fällen:  
  
-   Wenn Sie ein neues erstellen `CDaoDatabase` -Objekt, jedoch nicht über einen vorhandenen aus `CDaoWorkspace` Objekt MFC erstellt ein temporärer Arbeitsbereich-Objekt, das DAO-Standardarbeitsbereich entspricht. Wenn Sie für mehrere Datenbanken alle Datenbankobjekte der Standardarbeitsbereich zugeordnet sind dazu. Sie erreichen eine Datenbank-Arbeitsbereichs mit einem `CDaoDatabase` -Datenmember.  
  
-   Auf ähnliche Weise bei der Erstellung einer `CDaoRecordset` Objekt ohne einen Zeiger auf ein `CDaoDatabase` Objekt MFC wird ein temporäres Objekt erstellt und durch Erweiterung, ein temporärer Arbeitsbereich-Objekt. Sie können die Datenbank des Recordsets und indirekt den Arbeitsbereich zugreifen, über eine `CDaoRecordset` -Datenmember.  
  
## <a name="other-operations"></a>Andere Vorgänge  
 Andere Datenbankoperationen werden ebenfalls bereitgestellt, z. B. eine beschädigte Datenbank reparieren oder eine Datenbank.  
  
 Informationen über DAO direkt aufrufen und DAO-Sicherheit finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="a-nameappenda--cdaoworkspaceappend"></a><a name="append"></a>CDaoWorkspace::Append  
 Rufen Sie diese Memberfunktion aufrufen, nachdem Sie [erstellen](#create).  
  
```  
virtual void Append();
```  
  
### <a name="remarks"></a>Hinweise  
 **Fügen Sie** einer neu erstellten Workspace-Objekt an das Datenbankmodul Workspaces-Auflistung angefügt. Arbeitsbereiche beibehalten zwischen Datenbank-Engine-Sitzungen nicht; Sie werden nur im Arbeitsspeicher, nicht auf dem Datenträger gespeichert. Sie müssen keinen fügen Sie einen Arbeitsbereich; Wenn Sie dies nicht tun, können Sie weiterhin verwenden.  
  
 Ein angefügten Arbeitsbereich bleibt in der Auflistung Arbeitsbereiche in einem aktiven geöffneten Zustand bis zum Aufruf der [schließen](#close) Member-Funktion.  
  
 Weitere Informationen finden Sie im Thema "Append-Methode" in der DAO-Hilfe.  
  
##  <a name="a-namebegintransa--cdaoworkspacebegintrans"></a><a name="begintrans"></a>CDaoWorkspace::BeginTrans  
 Rufen Sie diese Memberfunktion zum Initiieren einer Transaktion.  
  
```  
void BeginTrans();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **BeginTrans**, Updates, die Sie, um die Struktur von Daten oder Datenbankobjekte vornehmen werden wirksam, wenn Sie die Transaktion ein Commit ausgeführt. Da Arbeitsbereich einen einzelnen Transaktionsbereich definiert wird, gilt die Transaktion für alle geöffneten Datenbanken im Arbeitsbereich. Es gibt zwei Möglichkeiten, die Transaktion abzuschließen:  
  
-   Rufen Sie die [CommitTrans](#committrans) Memberfunktion, um einen commit für die Transaktion, und speichern Sie Änderungen an der Datenquelle.  
  
-   Oder rufen Sie die [Rollback](#rollback) -Memberfunktion, die Transaktion abzubrechen.  
  
 Die Workspace-Objekt oder ein Datenbankobjekt schließen, während eine Transaktion ansteht Rollback aller ausstehenden Transaktionen.  
  
 Um Transaktionen für eine ODBC-Datenquelle aus den in einer anderen ODBC-Datenquelle zu isolieren, finden Sie unter der [SetIsolateODBCTrans](#setisolateodbctrans) Member-Funktion.  
  
##  <a name="a-namecdaoworkspacea--cdaoworkspacecdaoworkspace"></a><a name="cdaoworkspace"></a>CDaoWorkspace::CDaoWorkspace  
 Erstellt ein `CDaoWorkspace`-Objekt.  
  
```  
CDaoWorkspace();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des C++-Objekts, haben Sie zwei Optionen:  
  
-   Rufen Sie die [öffnen](#open) Memberfunktion Standardarbeitsbereich öffnen oder ein vorhandenes Objekt in der Auflistung der Arbeitsbereiche zu öffnen.  
  
-   Oder rufen Sie die [erstellen](#create) Member-Funktion, um ein neues Objekt des DAO-Arbeitsbereich zu erstellen. Dies startet explizit eine neue Arbeitsbereich-Sitzung, die Sie sich, über beziehen können die `CDaoWorkspace` Objekt. Nach dem Aufruf von **erstellen**, rufen Sie [Append](#append) , wenn Sie den Arbeitsbereich des Datenbankmoduls Arbeitsbereiche Sammlung hinzufügen möchten.  
  
 Finden Sie unter Übersicht über die Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Informationen, wenn Sie explizit erstellen müssen ein `CDaoWorkspace` Objekt. In der Regel verwenden Sie Arbeitsbereiche, die implizit erstellt, wenn Sie öffnen ein [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt ohne Angabe eines Arbeitsbereichs oder beim Öffnen einer [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) Objekt ohne Angabe eines Datenbankobjekts. MFC-DAO-Objekte, die auf diese Weise erstellten verwenden DAO-Standardarbeitsbereich, die einmal erstellt und wiederverwendet.  
  
 Um einen Arbeitsbereich und der darin enthaltenen Objekte freizugeben, rufen Sie die Workspace-Objekt [schließen](#close) Member-Funktion.  
  
##  <a name="a-nameclosea--cdaoworkspaceclose"></a><a name="close"></a>CDaoWorkspace::Close  
 Rufen Sie diese Memberfunktion zum Workspace-Objekt zu schließen.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Schließen einen Arbeitsbereich öffnen-Objekt gibt das zugrunde liegende DAO-Objekt und der Arbeitsbereich ist ein Element der Auflistung Arbeitsbereiche entfernt es aus der Auflistung. Aufrufen von **schließen** empfiehlt sich.  
  
> [!CAUTION]
>  Ein Workspace-Objekt geschlossen wird, öffnen Sie Datenbanken im Arbeitsbereich. Dies führt alle geöffneten Recordsets in den Datenbanken wird ebenfalls geschlossen, und alle ausstehenden Änderungen oder Updates zurückgesetzt. Weitere Informationen finden Sie unter der [CDaoDatabase::Close](../../mfc/reference/cdaodatabase-class.md#close), [CDaoRecordset::Close](../../mfc/reference/cdaorecordset-class.md#close), [CDaoTableDef::Close](../../mfc/reference/cdaotabledef-class.md#close), und [CDaoQueryDef::Close](../../mfc/reference/cdaoquerydef-class.md#close) Memberfunktionen.  
  
 Workspace-Objekte sind nicht permanent. Sie sind nur vorhanden, während Verweise auf diese vorhanden sind. Dies bedeutet, dass wenn die Sitzung beendet wird, den Arbeitsbereich und die Sammlung von Datenbanken nicht beibehalten werden. Sie müssen sie erneut auf die nächste Sitzung erstellen, von Ihrem Arbeitsbereich und die Datenbanken erneut zu öffnen.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" in der DAO-Hilfe.  
  
##  <a name="a-namecommittransa--cdaoworkspacecommittrans"></a><a name="committrans"></a>CDaoWorkspace::  
 Rufen Sie diese Memberfunktion zum commit einer Transaktion – eine Gruppe von Änderungen und Updates auf eine oder mehrere Datenbanken in den Arbeitsbereich zu speichern.  
  
```  
void CommitTrans();
```  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einer Reihe von Änderungen an der Datenbank Daten oder die Struktur, beginnend mit einem Aufruf von [BeginTrans](#begintrans). Wenn Sie die Transaktion abschließen, entweder commit es oder Rollback (Abbrechen) mit [Rollback](#rollback). Standardmäßig ohne Transaktionen sind Updates für Datensätze sofort ein Commit ausgeführt. Aufrufen von **BeginTrans** bewirkt, dass Engagement Updates verzögert werden, bis zum Aufruf von **CommitTrans**.  
  
> [!CAUTION]
>  In einem Arbeitsbereich Transaktionen sind immer global für den Arbeitsbereich und nicht nur eine Datenbank oder ein Recordset auf. Wenn Sie in mehr als eine Datenbank oder ein Recordset innerhalb einer Arbeitsbereichstransaktion Vorgänge **CommitTrans** Commits alle ausstehenden Updates und **Rollback** alle Vorgänge für diese Datenbanken und Recordsets wiederhergestellt.  
  
 Wenn Sie eine Datenbank oder ein Arbeitsbereich mit ausstehender Transaktionen schließen, werden die Transaktionen alle ein Rollback ausgeführt.  
  
> [!NOTE]
>  Dies ist kein Zweiphasen-Commit-Mechanismus. Wenn ein Update nicht zu übernehmen, werden anderen weiterhin Commit ausgeführt.  
  
##  <a name="a-namecompactdatabasea--cdaoworkspacecompactdatabase"></a><a name="compactdatabase"></a>CDaoWorkspace:: CompactDatabase  
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
 Der Name eines vorhandenen geschlossene Datenbank. Es kann ein vollständiger Pfad und Dateiname, z. B. "C:\\\MYDB. MDB". Wenn der Dateiname eine Erweiterung hat, müssen Sie es angeben. Wenn Ihr Netzwerk die einheitliche Benennungskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad wie z. B. "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte umgekehrte Schrägstriche sind in der Path-Zeichenfolgen erforderlich, weil "\\" ist die C++-Escape-Zeichen.)  
  
 `lpszDestName`  
 Der vollständige Pfad der komprimierten Datenbank, die Sie erstellen. Sie können auch angeben, einen Netzwerkpfad als mit `lpszSrcName`. Sie können keine der `lpszDestName` Argument an dieselbe Datenbankdatei als `lpszSrcName`.  
  
 `lpszPassword`  
 Ein Kennwort verwendet, wenn zum Komprimieren einer kennwortgeschützten Datenbank. Beachten Sie, dass bei Verwendung die Version von `CompactDatabase` , die ein Kennwort akzeptiert, müssen Sie alle Parameter angeben. Außerdem, da dies eine Connect-Parameter ist, erfordert spezielle Formatierung, wie folgt:; PWD= `lpszPassword`. Zum Beispiel:; PWD = "Happy". (Das führende Semikolon erforderlich ist.)  
  
 `lpszLocale`  
 Ein Zeichenfolgenausdruck, der zum Angeben der Sortierreihenfolge zum Erstellen verwendet `lpszDestName`. Wenn Sie dieses Argument nicht angeben, durch das Akzeptieren des Standardwerts von **DbLangGeneral** (siehe unten), das Gebietsschema der neuen Datenbank ist identisch mit der alten Datenbank. Dabei sind folgende Werte möglich:  
  
- **DbLangGeneral** Englisch, Deutsch, Französisch, Portugiesisch, Italienisch und modernes Spanisch  
  
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
  
- **DbLangSwedfin** Schwedisch und Finnisch  
  
- **DbLangTurkish** Türkisch  
  
 `nOptions`  
 Gibt eine oder mehrere Optionen für die Zieldatenbank `lpszDestName`. Wenn Sie dieses Argument nicht angeben, durch das Akzeptieren des Standardwert der `lpszDestName` haben dieselbe Verschlüsselung und die gleiche Version wie `lpszSrcName`. Sie können Kombinieren der **DbEncrypt** oder **DbDecrypt** Option mit einer der Optionen Version mit dem bitweisen OR-Operator. Werte, die einem Datenbankformat keine Datenbank-Engine Version angeben sind möglich:  
  
- **DbEncrypt** die Datenbank beim Komprimieren verschlüsselt.  
  
- **DbDecrypt** entschlüsselt die Datenbank beim Komprimieren.  
  
- **dbVersion10** erstellen Sie eine Datenbank, die beim Komprimieren das Microsoft Jet-Datenbank-Engine-Version 1.0 verwendet.  
  
- **dbVersion11** erstellen Sie eine Datenbank, die beim Komprimieren der Microsoft Jet-Datenbank-Engine-Version 1.1 verwendet.  
  
- **dbVersion20** erstellen Sie eine Datenbank, Version 2.0 der Microsoft Jet-Datenbankengine beim Komprimieren verwendet.  
  
- **dbVersion30** erstellen Sie eine Datenbank, Version 3.0 der Microsoft Jet-Datenbankengine beim Komprimieren verwendet.  
  
 Sie können **DbEncrypt** oder **DbDecrypt** im Optionsargument angeben, ob verschlüsselt oder die Datenbank entschlüsseln, da diese komprimiert wird. Wenn Sie eine nicht angeben oder wenn Sie beide enthalten **DbDecrypt** und **DbEncrypt**, `lpszDestName` müssen dieselbe Verschlüsselung wie `lpszSrcName`. Sie können eine der Konstanten Version im Optionsargument verwenden, um die Version des Datenformats für die komprimierte Datenbank anzugeben. Diese Konstante betrifft nur die Version des Datenformats von `lpszDestName`. Sie können nur eine Versionskonstante angeben. Wenn Sie eine Versionskonstante weglassen `lpszDestName` müssen die gleiche Version wie `lpszSrcName`. Sie können komprimieren `lpszDestName` nur auf eine Version, die identisch sind oder höher als der `lpszSrcName`.  
  
> [!CAUTION]
>  Wenn eine Datenbank nicht verschlüsselt ist, ist es möglich, auch wenn die Implementierung der Sicherheit für Benutzername und Kennwort, um die binäre Datenträgerdatei direkt zu lesen, aus die die Datenbank besteht.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie Daten in einer Datenbank ändern, wird die Datenbankdatei möglicherweise fragmentiert und mehr Speicherplatz als erforderlich. In regelmäßigen Abständen, sollten Sie die Datenbank für die Speicherdatenbank komprimieren. Die komprimierte Datenbank ist in der Regel kleiner. Sie können auch die Sortierreihenfolge, die Verschlüsselung oder die Version des Datenformats ändern, während Sie kopieren und komprimieren Sie die Datenbank.  
  
> [!CAUTION]
>  Der `CompactDatabase` Member-Funktion wird nicht ordnungsgemäß konvertiert eine vollständige Microsoft Access-Datenbank von einer Version in einen anderen. Es wird nur das Format konvertiert. Microsoft Access definierten Objekte wie Formulare und Berichte werden nicht konvertiert. Allerdings werden die Daten ordnungsgemäß konvertiert.  
  
> [!TIP]
>  Sie können auch `CompactDatabase` um eine Datei zu kopieren.  
  
 Weitere Informationen zum Komprimieren von Datenbanken finden Sie im Thema "CompactDatabase Method" in der DAO-Hilfe.  
  
##  <a name="a-namecreatea--cdaoworkspacecreate"></a><a name="create"></a>CDaoWorkspace:: Create  
 Rufen Sie diese Memberfunktion zum Erstellen eines neuen Objekts des DAO-Arbeitsbereich und die MFC-Bibliothek zugeordnet `CDaoWorkspace` Objekt.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszUserName,  
    LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Eine Zeichenfolge mit bis zu 14 Zeichen, die den neuen Arbeitsbereich-Objekt eindeutig bezeichnet. Sie müssen einen Namen angeben. Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
 *lpszUserName*  
 Der Benutzername des Besitzers des Arbeitsbereichs. Anforderungen finden Sie die `lpszDefaultUser` Parameter, um die [SetDefaultUser](#setdefaultuser) Member-Funktion. Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" in der DAO-Hilfe.  
  
 `lpszPassword`  
 Das Kennwort für das neue Workspace-Objekt. Ein Kennwort kann bis zu 14 Zeichen lang sein und kann alle Zeichen mit Ausnahme von ASCII 0 (null) enthalten. Groß-und Kleinschreibung. Verwandte Informationen finden Sie im Thema "Kennworteigenschaft" DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Die gesamte Erstellung erfolgt:  
  
1.  Erstellen einer [CDaoWorkspace](#cdaoworkspace) Objekt.  
  
2.  Rufen Sie die **erstellen** Member-Funktion den zugrunde liegenden DAO-Arbeitsbereich erstellt. Geben Sie einen Arbeitsbereichsnamen an.  
  
3.  Rufen Sie optional [Append](#append) , wenn Sie den Arbeitsbereich des Datenbankmoduls Arbeitsbereiche Sammlung hinzufügen möchten. Sie können mit dem Arbeitsbereich arbeiten, ohne es anfügen.  
  
 Nach der **erstellen** -Aufruf im Workspace-Objekt im geöffneten Zustand, einsatzbereit ist. Rufen Sie **öffnen** nach **erstellen**. Rufen Sie **erstellen** Arbeitsbereich bereits in der Auflistung der Arbeitsbereiche vorhanden ist. **Erstellen Sie** das Datenbankmodul initialisiert, wenn es für Ihre Anwendung nicht bereits initialisiert wurde.  
  
##  <a name="a-namegetdatabasecounta--cdaoworkspacegetdatabasecount"></a><a name="getdatabasecount"></a>CDaoWorkspace::GetDatabaseCount  
 Rufen Sie diese Memberfunktion, um die Anzahl von DAO-Datenbankobjekte in den Arbeitsbereich Databases-Auflistung abgerufen, die Anzahl der geöffneten Datenbanken im Arbeitsbereich.  
  
```  
short GetDatabaseCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der geöffneten Datenbanken im Arbeitsbereich.  
  
### <a name="remarks"></a>Hinweise  
 `GetDatabaseCount`ist nützlich, wenn Sie alle definierten Datenbanken in den Arbeitsbereich datenbankauflistung durchlaufen müssen. Um Informationen zu einer bestimmten Datenbank in der Auflistung abzurufen, finden Sie unter [GetDatabaseInfo](#getdatabaseinfo). Wird zum Aufrufen `GetDatabaseCount` für die Anzahl der geöffneten Datenbanken, dann verwenden Sie diese Zahl als Schleifenindex wiederholte Aufrufe an `GetDatabaseInfo`.  
  
##  <a name="a-namegetdatabaseinfoa--cdaoworkspacegetdatabaseinfo"></a><a name="getdatabaseinfo"></a>CDaoWorkspace::GetDatabaseInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen über eine Datenbank geöffnet, in dem Arbeitsbereich zu erhalten.  
  
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
 Der nullbasierte Index des Database-Objekts in den Arbeitsbereich datenbankauflistung, für die Suche nach Index.  
  
 `dbinfo`  
 Ein Verweis auf eine [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über die Datenbank abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, aktualisiert werden kann, Transaktionen  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Abfragetimeout Version Reihenfolge sortieren  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: Verbinden  
  
 `lpszName`  
 Der Name des Datenbankobjekts, für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die den neuen Arbeitsbereich-Objekt eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie eine Datenbank über einen Index zu suchen. Die andere Version können Sie eine Datenbank nach Namen suchen.  
  
 Eine Beschreibung der Informationen zurückgegeben `dbinfo`, finden Sie unter der [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
##  <a name="a-namegetinipatha--cdaoworkspacegetinipath"></a><a name="getinipath"></a>CDaoWorkspace::GetIniPath  
 Rufen Sie diese Memberfunktion, um den Speicherort der Microsoft Jet-Datenbank-Engine-Initialisierung Einstellungen in der Windows-Registrierung zu erhalten.  
  
```  
static CString PASCAL GetIniPath();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit dem Registrierungsschlüssel.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Speicherort zum Abrufen von Informationen zu den Einstellungen für das Datenbankmodul verwenden. Die zurückgegebenen Informationen ist tatsächlich auf den Namen der Unterschlüssel der Registrierung.  
  
 Weitere Informationen finden Sie unter den Themen "IniPath-Eigenschaft" und "Anpassen von Windows-Registrierung Einstellungen für den Datenzugriff" DAO-Hilfe.  
  
##  <a name="a-namegetisolateodbctransa--cdaoworkspacegetisolateodbctrans"></a><a name="getisolateodbctrans"></a>CDaoWorkspace::GetIsolateODBCTrans  
 Rufen Sie diese Memberfunktion um den aktuellen Wert der Eigenschaft DAO IsolateODBCTrans für den Arbeitsbereich zu erhalten.  
  
```  
BOOL GetIsolateODBCTrans();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ODBC-Transaktionen isoliert sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 In einigen Situationen müssen Sie mehrere nicht abgeschlossene Transaktionen für eine ODBC-Datenbank haben. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Bedenken Sie, dass Obwohl jeder Arbeitsbereich eigene ODBC-Verbindung zur Datenbank haben kann, dies die Leistung des Systems verlangsamt. Da Transaktionsisolation nicht erforderlich ist, werden die ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.  
  
 Einige ODBC-Server, z. B. Microsoft SQL Server lassen keine gleichzeitigen Transaktionen über eine einzelne Verbindung zu. Wenn Sie mehr als eine Transaktion auf einer solchen Datenbank haben müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf **TRUE** für jeden Arbeitsbereich, sobald Sie es öffnen. Dies erzwingt eine separate ODBC-Verbindung für jeden Arbeitsbereich.  
  
 Verwandte Informationen finden Sie im Thema "IsolateODBCTrans Property" in der DAO-Hilfe.  
  
##  <a name="a-namegetlogintimeouta--cdaoworkspacegetlogintimeout"></a><a name="getlogintimeout"></a>CDaoWorkspace::GetLoginTimeout  
 Rufen Sie diese Memberfunktion um den aktuellen Wert der Eigenschaft DAO-LoginTimeout-Parameter für den Arbeitsbereich zu erhalten.  
  
```  
static short PASCAL GetLoginTimeout();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert gibt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Wenn LoginTimeout-Parameter auf 0 festgelegt ist, tritt kein Timeout auf, und die Kommunikation mit der Datenquelle reagiert möglicherweise nicht.  
  
 Wenn Sie versuchen, mit einer ODBC-Datenbank wie Microsoft SQL Server, melden Sie sich möglicherweise schlägt die Verbindung aufgrund eines Netzwerkfehlers oder weil der Server nicht ausgeführt wird. Anstatt für die standardmäßige 20 Sekunden, eine Verbindung herzustellen, können Sie angeben, wie lange die Datenbank-Engine wartet, bevor er einen Fehler erzeugt. Anmelden an den Server wird implizit als Teil einer Zahl verschiedener Ereignisse, z. B. Ausführen einer Abfrage in eine externe Datenbank.  
  
 Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetnamea--cdaoworkspacegetname"></a><a name="getname"></a>CDaoWorkspace::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen der benutzerdefinierte Name des DAO-Arbeitsbereich Objekt zugrunde liegenden der `CDaoWorkspace` Objekt.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) mit dem benutzerdefinierten Namen des DAO-Workspace-Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Der Name ist nützlich für den Zugriff auf die DAO-Workspace-Objekt in die Datenbank-Engine arbeitsbereicheauflistung nach Namen.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetusernamea--cdaoworkspacegetusername"></a><a name="getusername"></a>CDaoWorkspace::GetUserName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Besitzers des Arbeitsbereichs.  
  
```  
CString GetUserName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , den Besitzer des Workspace-Objekts darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie zum Abrufen oder Festlegen der Berechtigungen für den Besitzer des Arbeitsbereichs, DAO direkt, um die Einstellung der Eigenschaft Berechtigungen zu überprüfen. Hiermit wird bestimmt, welche Berechtigungen dieser Benutzer besitzt. Um Berechtigungen zu arbeiten, benötigen Sie ein SYSTEM. MDA-Datei.  
  
 Informationen zum Aufrufen von DAO direkt finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md). Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetversiona--cdaoworkspacegetversion"></a><a name="getversion"></a>CDaoWorkspace::GetVersion  
 Rufen Sie diese Memberfunktion zum Ermitteln der Version von Microsoft Jet-Datenbankmodul verwendet.  
  
```  
static CString PASCAL GetVersion();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , der angibt, der Version der Datenbank-Engine, die dem Objekt zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Wert stellt die Versionsnummer im Format "Hauptversion.Nebenversion"; beispielsweise "3.0". Die Versionsnummer des Produkts (z. B. "3.0") besteht aus der Versionsnummer (3), einem Punkt und der Versionsnummer (0).  
  
 Verwandte Informationen finden Sie unter dem Thema "Version-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="a-namegetworkspacecounta--cdaoworkspacegetworkspacecount"></a><a name="getworkspacecount"></a>CDaoWorkspace::GetWorkspaceCount  
 Rufen Sie diese Memberfunktion, um die Anzahl der DAO Workspace-Objekte in der Datenbank-Engine arbeitsbereicheauflistung abzurufen.  
  
```  
short GetWorkspaceCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der geöffneten Arbeitsbereiche in der Auflistung der Arbeitsbereiche.  
  
### <a name="remarks"></a>Hinweise  
 Diese Anzahl umfasst keine geöffneten Arbeitsbereiche, die nicht an die Auflistung angefügt. `GetWorkspaceCount`ist nützlich, wenn Sie alle definierten Arbeitsbereiche in der Auflistung der Arbeitsbereiche durchlaufen müssen. Informationen zu einem bestimmten Arbeitsbereich in der Auflistung finden Sie unter [GetWorkspaceInfo](#getworkspaceinfo). Wird zum Aufrufen `GetWorkspaceCount` für die Anzahl der geöffneten Arbeitsbereiche, dann verwenden Sie diese Zahl als Schleifenindex wiederholte Aufrufe an `GetWorkspaceInfo`.  
  
##  <a name="a-namegetworkspaceinfoa--cdaoworkspacegetworkspaceinfo"></a><a name="getworkspaceinfo"></a>CDaoWorkspace::GetWorkspaceInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen über einen Arbeitsbereich öffnen in der Sitzung zu erhalten.  
  
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
 Der nullbasierte Index des Database-Objekts in der Auflistung Arbeitsbereiche für die Suche nach Index.  
  
 `wkspcinfo`  
 Ein Verweis auf eine [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) -Objekt, das die angeforderten Informationen zurückgibt.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über den Arbeitsbereich abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Benutzername  
  
- `AFX_DAO_ALL_INFO`Primäre und sekundäre Informationen plus: ODBCTrans isolieren  
  
 `lpszName`  
 Der Name des Workspace-Objekts, für die Suche nach Namen. Der Name ist eine Zeichenfolge mit bis zu 14 Zeichen, die den neuen Arbeitsbereich-Objekt eindeutig bezeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Eine Beschreibung der Informationen zurückgegeben `wkspcinfo`, finden Sie unter der [CDaoWorkspaceInfo](../../mfc/reference/cdaoworkspaceinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für den übergeordneten Ebenen sowie.  
  
##  <a name="a-nameidlea--cdaoworkspaceidle"></a><a name="idle"></a>CDaoWorkspace::Idle  
 Rufen Sie **Leerlauf** ermöglichen das Datenbankmodul die Möglichkeit zum Ausführen von Hintergrundaufgaben, die aufgrund der umfangreichen Datenverarbeitung möglicherweise nicht auf dem neuesten Stand.  
  
```  
static void PASCAL Idle(int nAction = dbFreeLocks);
```  
  
### <a name="parameters"></a>Parameter  
 `nAction`  
 Aktion bei der Verarbeitung im Leerlauf ausgeführt werden soll. Derzeit ist die einzige gültige Aktion, **DbFreeLocks**.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist häufig in Mehrbenutzer-und Leistungsniveau, nicht genügend Hintergrundverarbeitungszeit ist, um alle Datensätze in einem Recordset aktuell zu halten.  
  
> [!NOTE]
>  Aufrufen von **Leerlauf** muss nicht mit Datenbanken mit Version 3.0 des Microsoft Jet-Datenbankmoduls. Verwendung **Leerlauf** nur für Datenbanken, die mit früheren Versionen erstellt wurden.  
  
 In der Regel wird Sperren entfernt Daten lesen und in lokalen vom Typ Dynaset-Recordset-Objekte nur aktualisiert, wenn keine anderen Aktionen (einschließlich mausbewegungen) auftreten. Wenn Sie in regelmäßigen Abständen Aufrufen **Leerlauf**, Sie geben das Datenbankmodul mit der Zeit auf Hintergrundprozesse durchführen, indem Sie auf den aktuellen Stand nicht benötigte Lesesperren. Angeben der **DbFreeLocks** Konstante als Argument verzögert die Verarbeitung, bis alle Lesesperren freigegeben werden.  
  
 Diese Memberfunktion ist nicht im Einzelbenutzermodus Umgebungen erforderlich, wenn mehrere Instanzen einer Anwendung ausgeführt werden. Die **Leerlauf** Memberfunktion kann die Leistung in einer Umgebung mit mehreren Benutzern erhöhen, da das Datenbankmodul zwingt, Daten auf der Festplatte, die Freigabe von Sperren für den Arbeitsspeicher zu leeren. Sie können Lesesperren auch freigeben, indem Sie Operationen in einer Transaktion vornehmen.  
  
 Verwandte Informationen finden Sie im Thema "Im Leerlauf Method" in der DAO-Hilfe.  
  
##  <a name="a-nameisopena--cdaoworkspaceisopen"></a><a name="isopen"></a>CDaoWorkspace::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDaoWorkspace` -Objekts geöffnet ist – d. h., ob das MFC-Objekt durch einen Aufruf von initialisiert wurde [öffnen](#open) oder einen Aufruf von [erstellen](#create).  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn der Workspace-Objekt geöffnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können keine der Memberfunktionen eines Arbeitsbereichs Funktionen aufrufen, die im geöffneten Zustand ist.  
  
##  <a name="a-namempdaoworkspacea--cdaoworkspacempdaoworkspace"></a><a name="m_pdaoworkspace"></a>CDaoWorkspace::m_pDAOWorkspace  
 Ein Zeiger auf das zugrunde liegende DAO-Workspace-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Datenelement aus, wenn Sie so direkten Zugriff auf das zugrunde liegende DAO-Objekt benötigen. Sie können die DAO-Schnittstellen des Objekts mit diesem Zeiger aufrufen.  
  
 Informationen zum direkten Zugriff auf DAO-Objekte finden Sie unter [technischen Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="a-nameopena--cdaoworkspaceopen"></a><a name="open"></a>CDaoWorkspace::Open  
 Explizit öffnet ein Workspace-Objekt, das DAO-Standardarbeitsbereich zugeordnet.  
  
```  
virtual void Open(LPCTSTR lpszName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Name des Objekts die DAO-Arbeitsbereich zu öffnen, eine Zeichenfolge mit bis zu 14 Zeichen, die den Arbeitsbereich eindeutig bezeichnet. Übernehmen Sie den Standardwert **NULL** Standardarbeitsbereich explizit öffnen. Namenskonventionen, finden Sie unter der `lpszName` -Parameter für [erstellen](#create). Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CDaoWorkspace` Objekt, rufen Sie diese Memberfunktion, um einen der folgenden Schritte aus:  
  
-   Öffnen Sie den Standardarbeitsbereich explizit. Pass **NULL** for `lpszName`.  
  
-   Öffnen Sie eine vorhandene `CDaoWorkspace` -Objekt, das ein Mitglied der Auflistung Arbeitsbereiche nach Namen. Übergeben Sie einen gültigen Namen für ein vorhandenes Workspace-Objekt.  
  
 **Öffnen Sie** im Workspace-Objekt in den geöffneten Zustand versetzt, und auch das Datenbankmodul initialisiert, wenn es für Ihre Anwendung nicht bereits initialisiert wurde.  
  
 Obwohl viele `CDaoWorkspace` Element Funktionen können nur aufgerufen werden, nachdem der Arbeitsbereich geöffnet wurde, die folgenden Memberfunktionen, die auf dem Datenbankmodul arbeiten, stehen nach der Erstellung des C++-Objekts, aber vor einem Aufruf von **öffnen**:  
  
||||  
|-|-|-|  
|[Erstellen](#create)|[GetVersion](#getversion)|[SetDefaultUser](#setdefaultuser)|  
|[GetIniPath](#getinipath)|[Im Leerlauf](#idle)|[SetIniPath](#setinipath)|  
|[GetLoginTimeout](#getlogintimeout)|[SetDefaultPassword](#setdefaultpassword)|[SetLoginTimeout](#setlogintimeout)|  
  
##  <a name="a-namerepairdatabasea--cdaoworkspacerepairdatabase"></a><a name="repairdatabase"></a>CDaoWorkspace::RepairDatabase  
 Rufen Sie diese Memberfunktion auf, sollten Sie versuchen, eine beschädigte Datenbank zu reparieren, die das Microsoft Jet-Datenbankmodul zugreift.  
  
```  
static void PASCAL RepairDatabase(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszName`  
 Der Pfad und Dateiname für eine vorhandene Datenbankdatei von Microsoft Jet-Datenbankmodul. Wenn Sie den Pfad weglassen, wird nur das aktuelle Verzeichnis durchsucht. Wenn Ihr System die einheitliche Benennungskonvention (UNC) unterstützt, Sie können auch angeben einen Netzwerkpfad wie z. B.: "\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB". (Doppelte umgekehrte Schrägstriche sind in der Path-Zeichenfolge erforderlich, weil "\\" ist die C++-Escape-Zeichen.)  
  
### <a name="remarks"></a>Hinweise  
 Schließen Sie die Datenbank, die durch angegebene `lpszName` , bevor Sie sie reparieren. In einer Umgebung mit mehreren Benutzern andere Benutzer keinen `lpszName` öffnen, während Sie sie reparieren. Wenn `lpszName` nicht geschlossen oder ist nicht verfügbar für die exklusive Verwendung ein Fehler auftritt.  
  
 Diese Memberfunktion versucht, eine Datenbank zu reparieren, die von einer unvollständigen Schreiboperation als möglicherweise beschädigt markiert wurde. Dies kann auftreten, wenn eine Anwendung mithilfe der Microsoft Jet-Datenbankmodul wegen eines Problems Power oder Hardware unerwartet geschlossen wird. Wenn Sie den Vorgang und der Aufruf abgeschlossen der [schließen](../../mfc/reference/cdaodatabase-class.md#close) Memberfunktion oder die Anwendung normal beenden, die Datenbank wird nicht als möglicherweise beschädigt gekennzeichnet werden.  
  
> [!NOTE]
>  Nach dem Reparieren einer Datenbank ist auch eine gute Idee, komprimieren Sie sie mithilfe der [CompactDatabase](#compactdatabase) Member-Funktion, um die Datei zu defragmentieren und Speicherplatz zu gewinnen.  
  
 Weitere Informationen zum Reparieren von Datenbanken finden Sie im Thema "RepairDatabase Method" in der DAO-Hilfe.  
  
##  <a name="a-namerollbacka--cdaoworkspacerollback"></a><a name="rollback"></a>CDaoWorkspace::Rollback  
 Rufen Sie diese Memberfunktion, um die aktuelle Transaktion zu beenden und alle Datenbanken in den Arbeitsbereich in dem Zustand wiederherzustellen, bevor die Transaktion gestartet wurde.  
  
```  
void Rollback();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  In einem Arbeitsbereichsobjekt Transaktionen sind immer global für den Arbeitsbereich und sind nicht auf nur eine Datenbank oder ein Recordset beschränkt. Wenn Sie in mehr als eine Datenbank oder ein Recordset innerhalb einer Arbeitsbereichstransaktion Vorgänge **Rollback** alle Vorgänge für alle diese Datenbanken und Recordsets wiederhergestellt.  
  
 Ein Workspace-Objekt schließen, ohne zu speichern oder ein Rollback für alle anstehenden Transaktionen, werden automatisch ein Rollback für die Transaktionen ausgeführt. Wenn Sie aufrufen [CommitTrans](#committrans) oder **Rollback** erst nach Aufrufen von [BeginTrans](#begintrans), ein Fehler auftritt.  
  
> [!NOTE]
>  Wenn Sie eine Transaktion beginnen, zeichnet das Datenbankmodul die Vorgänge in einer Datei in das Verzeichnis, angegeben durch die Umgebungsvariable TEMP auf der Arbeitsstation gespeichert. Wenn die Transaktionsprotokolldatei den verfügbaren Speicher auf dem TEMPORÄREN Laufwerk ausgeschöpft hat, das Datenbankmodul führt dazu, dass MFC Auslösen einer `CDaoException` (DAO-Fehler, 2004). An diesem Punkt, wenn Sie aufrufen **CommitTrans**, eine unbestimmte Anzahl von Operationen wird ein Commit ausgeführt, aber die verbleibenden nicht abgeschlossene Vorgänge verloren, und der Vorgang muss neu gestartet werden. Aufrufen von **Rollback** gibt das Transaktionsprotokoll und Rollback für alle Vorgänge in der Transaktion.  
  
##  <a name="a-namesetdefaultpassworda--cdaoworkspacesetdefaultpassword"></a><a name="setdefaultpassword"></a>CDaoWorkspace::SetDefaultPassword  
 Rufen Sie diese Memberfunktion, um das Standard-Kennwort festlegen, das das Datenbankmodul verwendet, wenn ein Workspace-Objekt ohne ein bestimmtes Kennwort erstellt wird.  
  
```  
static void PASCAL SetDefaultPassword(LPCTSTR lpszPassword);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszPassword`  
 Das Standardkennwort. Ein Kennwort kann bis zu 14 Zeichen lang sein und kann alle Zeichen mit Ausnahme von ASCII 0 (null) enthalten. Groß-und Kleinschreibung.  
  
### <a name="remarks"></a>Hinweise  
 Das Standard-Kennwort, das Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf zu erstellen. Wenn Sie nachfolgende Arbeitsbereiche erstellen, müssen Sie nicht angeben ein Kennworts in der [erstellen](#create) aufrufen.  
  
 Diese Memberfunktion verwenden:  
  
1.  Erstellen einer `CDaoWorkspace` Objekt rufen Sie jedoch nicht **erstellen**.  
  
2.  Rufen Sie `SetDefaultPassword` und, falls gewünscht, [SetDefaultUser](#setdefaultuser).  
  
3.  Rufen Sie **erstellen** für dieses Arbeitsbereichsobjekt oder nachfolgender Felder, ohne ein Kennwort angeben.  
  
 In der Standardeinstellung die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die DefaultPassword-Eigenschaft auf eine leere Zeichenfolge festgelegt ist ("").  
  
 Weitere Informationen zur Sicherheit finden Sie im Thema "Permissions-Eigenschaft" in der DAO-Hilfe. Weitere Informationen finden Sie unter den Themen "DefaultPassword-Eigenschaft" und "DefaultUser Property" in der DAO-Hilfe.  
  
##  <a name="a-namesetdefaultusera--cdaoworkspacesetdefaultuser"></a><a name="setdefaultuser"></a>CDaoWorkspace::SetDefaultUser  
 Rufen Sie diese Memberfunktion zum Standard-Benutzernamen festlegen, den das Datenbankmodul verwendet, wenn ein Workspace-Objekt ohne einen bestimmten Benutzernamen erstellt wird.  
  
```  
static void PASCAL SetDefaultUser(LPCTSTR lpszDefaultUser);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDefaultUser`  
 Der Standard-Benutzername. Ein Benutzernamen kann 1 bis 20 Zeichen lang sein und Buchstaben, Sonderzeichen, Zahlen, Leerzeichen und Symbole enthalten: "(Anführungszeichen), Schrägstrich (/), \ (umgekehrter Schrägstrich), \[ \] (Klammern),: (Doppelpunkt), | (Pipe), \< (kleiner-als-Zeichen), > (größer-als-Zeichen), + (Pluszeichen), = (Gleichheitszeichen), Semikolon (;), (Komma), (Fragezeichen), * (Sternchen), führende Leerzeichen und Steuerzeichen (ASCII 00 bis ASCII 31). Verwandte Informationen finden Sie im Thema "UserName-Eigenschaft" in der DAO-Hilfe.  
  
### <a name="remarks"></a>Hinweise  
 Die Standard-Benutzernamen, den Sie festlegen, gilt für neue Arbeitsbereiche, die Sie nach dem Aufruf erstellen. Wenn Sie nachfolgende Arbeitsbereiche erstellen, müssen Sie nicht Geben Sie einen Benutzernamen in der [erstellen](#create) aufrufen.  
  
 Diese Memberfunktion verwenden:  
  
1.  Erstellen einer `CDaoWorkspace` Objekt rufen Sie jedoch nicht **erstellen**.  
  
2.  Rufen Sie `SetDefaultUser` und, falls gewünscht, [SetDefaultPassword](#setdefaultpassword).  
  
3.  Rufen Sie **erstellen** für dieses Arbeitsbereichsobjekt oder nachfolgender Felder, ohne einen Benutzernamen anzugeben.  
  
 In der Standardeinstellung die DefaultUser-Eigenschaft auf "Admin" festgelegt ist und die DefaultPassword-Eigenschaft auf eine leere Zeichenfolge festgelegt ist ("").  
  
 Weitere Informationen finden Sie unter den Themen "DefaultUser Property" und "DefaultPassword Property" in der DAO-Hilfe.  
  
##  <a name="a-namesetinipatha--cdaoworkspacesetinipath"></a><a name="setinipath"></a>CDaoWorkspace::SetIniPath  
 Rufen Sie diese Memberfunktion zum Angeben des Speicherorts der Windows-registrierungseinstellungen für das Microsoft Jet-Datenbankmodul.  
  
```  
static void PASCAL SetIniPath(LPCTSTR lpszRegistrySubKey);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszRegistrySubkey*  
 Eine Zeichenfolge mit dem Namen einer Windows-Registrierungsunterschlüssel für den Speicherort der Microsoft Jet-Datenbank-Engine-Einstellungen oder Parameter für installierbare ISAM-Datenbanken erforderlich sind.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `SetIniPath` nur, wenn Sie spezielle Einstellungen angeben müssen. Weitere Informationen finden Sie unter dem Thema "IniPath-Eigenschaft" in der DAO-Hilfe.  
  
> [!NOTE]
>  Rufen Sie `SetIniPath` während der Anwendungsinstallation nicht wenn die Anwendung ausgeführt wird. `SetIniPath`muss aufgerufen werden, bevor Sie alle Arbeitsbereiche, Datenbanken oder Recordsets öffnen. Andernfalls löst MFC eine Ausnahme aus.  
  
 Dieser Mechanismus können Sie um die Datenbank-Engine mit vom Benutzer bereitgestellte Registrierungseinträge zu konfigurieren. Der Gültigkeitsbereich dieses Attributs ist auf Ihre Anwendung beschränkt und kann nicht ohne Neustarten der Anwendung geändert werden.  
  
##  <a name="a-namesetisolateodbctransa--cdaoworkspacesetisolateodbctrans"></a><a name="setisolateodbctrans"></a>CDaoWorkspace::SetIsolateODBCTrans  
 Rufen Sie diese Memberfunktion um den Wert der Eigenschaft für den Arbeitsbereich DAO IsolateODBCTrans festzulegen.  
  
```  
void SetIsolateODBCTrans(BOOL bIsolateODBCTrans);
```  
  
### <a name="parameters"></a>Parameter  
 *bIsolateODBCTrans*  
 Übergeben Sie **TRUE** Wenn isolieren ODBC-Transaktionen beginnen soll. Übergeben Sie **FALSE** Wenn isolieren ODBC-Transaktionen beendet werden soll.  
  
### <a name="remarks"></a>Hinweise  
 In einigen Situationen müssen Sie mehrere nicht abgeschlossene Transaktionen für eine ODBC-Datenbank haben. Zu diesem Zweck müssen Sie einen separaten Arbeitsbereich für jede Transaktion zu öffnen. Obwohl jeder Arbeitsbereich eigene ODBC-Verbindung zur Datenbank haben kann, wird dadurch die Leistung des Systems. Da Transaktionsisolation nicht erforderlich ist, werden die ODBC-Verbindungen von mehreren Workspace-Objekte, die vom gleichen Benutzer geöffnet standardmäßig freigegeben.  
  
 Einige ODBC-Server, z. B. Microsoft SQL Server lassen keine gleichzeitigen Transaktionen über eine einzelne Verbindung zu. Wenn Sie mehr als eine Transaktion auf einer solchen Datenbank haben müssen, legen Sie die IsolateODBCTrans-Eigenschaft auf **TRUE** für jeden Arbeitsbereich, sobald Sie es öffnen. Dies erzwingt eine separate ODBC-Verbindung für jeden Arbeitsbereich.  
  
##  <a name="a-namesetlogintimeouta--cdaoworkspacesetlogintimeout"></a><a name="setlogintimeout"></a>CDaoWorkspace::SetLoginTimeout  
 Rufen Sie diese Memberfunktion zum Festlegen des Wertes der DAO-LoginTimeout-Eigenschaft für den Arbeitsbereich.  
  
```  
static void PASCAL SetLoginTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `nSeconds`  
 Die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Wert gibt die Anzahl der Sekunden, bevor ein Fehler auftritt, wenn Sie versuchen, eine ODBC-Datenbank anmelden. Die Standardeinstellung für das Anmeldungstimeout beträgt 20 Sekunden. Wenn LoginTimeout-Parameter auf 0 festgelegt ist, tritt kein Timeout auf, und die Kommunikation mit der Datenquelle reagiert möglicherweise nicht.  
  
 Wenn Sie versuchen, mit einer ODBC-Datenbank wie Microsoft SQL Server, melden Sie sich möglicherweise schlägt die Verbindung aufgrund eines Netzwerkfehlers oder weil der Server nicht ausgeführt wird. Anstatt für die standardmäßige 20 Sekunden, eine Verbindung herzustellen, können Sie angeben, wie lange die Datenbank-Engine wartet, bevor er einen Fehler erzeugt. Anmelden bei der Server wird implizit als Teil einer Zahl verschiedener Ereignisse, z. B. Ausführen einer Abfrage in eine externe Datenbank. Der Timeoutwert wird durch die aktuelle Einstellung der LoginTimeout-Eigenschaft bestimmt.  
  
 Verwandte Informationen finden Sie im Thema "LoginTimeout-Eigenschaft" in der DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset-Klasse](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException-Klasse](../../mfc/reference/cdaoexception-class.md)

