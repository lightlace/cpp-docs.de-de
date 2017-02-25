---
title: "CDaoWorkspace Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoWorkspace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspace class"
  - "DAO workspaces [C++]"
  - "DAO workspaces [C++], CDaoWorkspace class"
  - "database engine [C++], accessing via workspace"
  - "DDLs [C++]"
  - "default workspaces [C++]"
  - "default workspaces [C++], DAO"
  - "Standardwerte [C++], Arbeitsbereiche"
  - "ODBC-Klassen [C++], vs. DAO classes"
  - "persistence [C++], DAO workspace"
  - "security [MFC]"
  - "security [MFC], DAO workspaces"
  - "sessions [C++], DAO workspace"
  - "transaction spaces [C++]"
  - "transaction spaces [C++], DAO workspace"
  - "Workspace class"
  - "workspaces [C++], DAO"
  - "workspaces [C++], default"
  - "workspaces [C++], interface to database engine"
  - "workspaces [C++], Dauerhaftigkeit"
  - "Workspaces collection"
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoWorkspace Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verwaltet eine benannte, kennwortgeschützte, Datenbanksitzung von der Anmeldung, um, durch einen einzelnen Benutzer abzumelden.  
  
## Syntax  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoWorkspace::CDaoWorkspace](../Topic/CDaoWorkspace::CDaoWorkspace.md)|Erstellt ein Arbeitsbereichsobjekt.  Danach Aufruf **Create** oder **Öffnen**.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoWorkspace::Append](../Topic/CDaoWorkspace::Append.md)|Fügt einen neu erstellten Arbeitsbereich mit der Arbeitsbereichsauflistung des Datenbankmoduls an.|  
|[CDaoWorkspace::BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)|Beginnt eine neue Transaktion, die für alle Datenbanken gilt, die im Arbeitsbereich geöffnet sind.|  
|[CDaoWorkspace::Close](../Topic/CDaoWorkspace::Close.md)|Schließt den Arbeitsbereich und alle Objekte, die sie enthält.  Während Transaktionen zurückgesetzt.|  
|[CDaoWorkspace::CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)|Schließt die aktuelle Transaktion ab und speichert die Änderungen.|  
|[CDaoWorkspace::CompactDatabase](../Topic/CDaoWorkspace::CompactDatabase.md)|Komprimiert \(oder Duplikate\) eine Datenbank.|  
|[CDaoWorkspace::Create](../Topic/CDaoWorkspace::Create.md)|Erstellt ein neues DAO\-Arbeitsbereichsobjekt.|  
|[CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)|Gibt die Anzahl der DAO\-Datenbank\-Objekten in der Datenbankauflistung des Arbeitsbereichs zurück.|  
|[CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)|Gibt Informationen über eine bestimmte DAO\-Datenbank zurück, die in der Datenbankauflistung des Arbeitsbereichs definiert ist.|  
|[CDaoWorkspace::GetIniPath](../Topic/CDaoWorkspace::GetIniPath.md)|Gibt den Speicherort der Initialisierungseinstellungen des Microsoft Jet\-Datenbankmoduls in der Windows\-Registrierung zurück.|  
|[CDaoWorkspace::GetIsolateODBCTrans](../Topic/CDaoWorkspace::GetIsolateODBCTrans.md)|Gibt einen Wert zurück, der angibt, ob mehrere Transaktionen, die dieselbe ODBC\-Datenquelle betreffen, über mehrere erzwungene Verbindungen zur Datenquelle befinden.|  
|[CDaoWorkspace::GetLoginTimeout](../Topic/CDaoWorkspace::GetLoginTimeout.md)|Gibt die Anzahl der Sekunden zurück, bevor ein Fehler auftritt, wenn der Benutzer versucht, auf eine ODBC\-Datenbank anzumelden.|  
|[CDaoWorkspace::GetName](../Topic/CDaoWorkspace::GetName.md)|Gibt den benutzerdefinierten Namen für das Arbeitsbereichsobjekt zurück.|  
|[CDaoWorkspace::GetUserName](../Topic/CDaoWorkspace::GetUserName.md)|Gibt den angegebenen Benutzernamen zurück, als der Arbeitsbereich erstellt wurde.  Dies ist der Name des Arbeitsbereichsbesitzers.|  
|[CDaoWorkspace::GetVersion](../Topic/CDaoWorkspace::GetVersion.md)|Gibt eine Zeichenfolge zurück, die die Version des Datenbankmoduls enthält, das mit dem Arbeitsbereich zugeordnet ist.|  
|[CDaoWorkspace::GetWorkspaceCount](../Topic/CDaoWorkspace::GetWorkspaceCount.md)|Gibt die Anzahl der DAO\-Arbeitsbereichsobjekten in der Arbeitsbereichsauflistung des Datenbankmoduls zurück.|  
|[CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)|Gibt Informationen zu einem angegebenen DAO\-Arbeitsbereich zurück, der in der Arbeitsbereichsauflistung des Datenbankmoduls definiert ist.|  
|[CDaoWorkspace::Idle](../Topic/CDaoWorkspace::Idle.md)|Ermöglicht dem Datenbankmodul, um Tasks auszuführen.|  
|[CDaoWorkspace::IsOpen](../Topic/CDaoWorkspace::IsOpen.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn der Arbeitsbereich geöffnet ist.|  
|[CDaoWorkspace::Open](../Topic/CDaoWorkspace::Open.md)|Öffnet explizit ein Arbeitsbereichsobjekt, das mit Standardarbeitsbereich DAO zugeordnet ist.|  
|[CDaoWorkspace::RepairDatabase](../Topic/CDaoWorkspace::RepairDatabase.md)|Versucht, eine beschädigte Datenbank zu reparieren.|  
|[CDaoWorkspace::Rollback](../Topic/CDaoWorkspace::Rollback.md)|Beendet die aktuelle Transaktion und speichert keine Änderungen.|  
|[CDaoWorkspace::SetDefaultPassword](../Topic/CDaoWorkspace::SetDefaultPassword.md)|Legt das Kennwort fest, unter dem das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt ohne ein bestimmtes Kennwort erstellt wird.|  
|[CDaoWorkspace::SetDefaultUser](../Topic/CDaoWorkspace::SetDefaultUser.md)|Legt den Benutzernamen fest, dem das Datenbankmodul verwendet, wenn ein Arbeitsbereichsobjekt ohne einen bestimmten Benutzernamen erstellt wird.|  
|[CDaoWorkspace::SetIniPath](../Topic/CDaoWorkspace::SetIniPath.md)|Legt den Speicherort der Initialisierungseinstellungen des Microsoft Jet\-Datenbankmoduls in der Windows\-Registrierung fest.|  
|[CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md)|Gibt an, ob mehrere Transaktionen, die dieselbe ODBC\-Datenquelle betreffen, isoliert werden, indem mehrere Verbindungen zur Datenquelle erzwingt.|  
|[CDaoWorkspace::SetLoginTimeout](../Topic/CDaoWorkspace::SetLoginTimeout.md)|Legt die Anzahl von Sekunden fest, bevor ein Fehler auftritt, wenn der Benutzer versucht, einer ODBC\-Datenquelle anzumelden.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoWorkspace::m\_pDAOWorkspace](../Topic/CDaoWorkspace::m_pDAOWorkspace.md)|verweist auf dem zugrunde liegenden DAO\-Arbeitsbereichsobjekt.|  
  
## Hinweise  
 In den meisten Fällen benötigen Sie nicht mehrere Arbeitsbereiche, und Sie müssen nicht, um explizite Arbeitsbereichsobjekte zu erstellen; Wenn Sie Datenbank und Recordset\-Objekte öffnen, verwenden sie Standardarbeitsbereich DAO.  Bei Bedarf können Sie mehrere Sitzungen gleichzeitig ausführen, indem Sie zusätzliche Arbeitsbereichsobjekte erstellen.  Jedes Arbeitsbereichsobjekt kann geöffnete Datenbankobjekte der mehrere in einer eigenen Datenbankauflistung enthalten.  In MFC ist ein Arbeitsbereich hauptsächlich ein Transaktions\-Manager und gibt einen Satz von allen geöffneten Datenbanken im gleichen "Transaktionsleerzeichen" an.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben ein Präfix "CDao".  Im Allgemeinen sind die MFC\-Klassen auf Grundlage DAO besser geeignet als die MFC\-Klassen auf Grundlage ODBC.  Die DAO\-basierten Klassenzugangsdaten durch das Microsoft Jet\-Datenbankmodul, einschließlich ODBC\-Treiber.  Sie unterstützen auch Operationen der Datendefinitionssprache \(Data Definition Language\), wie das Erstellen von Datenbanken und Hinzufügen von Tabellen und Feldern zu Klassen, ohne zu müssen, DAO direkt aufzurufen.  
  
## Funktionen  
 \- Klasse `CDaoWorkspace` stellt Folgendes:  
  
-   Expliziter Zugriff nach Bedarf zu einem standardmäßigen Arbeitsbereich erstellt, durch das Initialisieren des Datenbankmoduls.  Normalerweise Sie Standardarbeitsbereich der Verwendung DAO implizit durch das Erstellen der Datenbank und der Recordset\-Objekte.  
  
-   Ein Transaktionsleerzeichen, in dem alle Transaktionen auf Datenbanken gelten, die im Arbeitsbereich geöffnet sind.  Sie können zusätzliche Arbeitsbereiche erstellen, um separate Transaktionsbereiche zu verwalten.  
  
-   Eine Schnittstelle zu vielen Eigenschaften des zugrunde liegenden Microsoft Jet\-Datenbankmoduls \(siehe die statischen Memberfunktionen\).  Ein Arbeitsbereich oder das Aufrufen einer statischen Memberfunktion Öffnen oder Erstellen, bevor geöffnet, oder Erstellen, initialisiert das Datenbankmodul.  
  
-   Zugriff auf die Arbeitsbereichsauflistung des Datenbankmoduls, mit der alle aktiven Arbeitsbereiche speichert, die ihm angefügt wurden.  Sie können mit Arbeitsbereichen auch erstellen und bearbeiten, ohne sie aus der Auflistung.  
  
## Sicherheit  
 MFC implementiert nicht die Benutzer und Gruppen in Auflistungen DAO, die für Sicherheitskontrolle verwendet werden.  Wenn Sie diese Aspekte von DAO benötigen, müssen Sie sie selbst über direkte Aufrufe DAO\-Schnittstellen programmieren.  Weitere Informationen finden Sie unter [Technischer Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Verwendung  
 Sie können Klasse `CDaoWorkspace` verwenden:  
  
-   Öffnen Sie explizit den Standardarbeitsbereich.  
  
     Normalerweise ist die Verwendung des Standardarbeitsbereich implizit \- wenn Sie neue [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) oder [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)\-Objekte öffnen.  Möglicherweise müssen Sie jedoch explizit darauf zugreifen \- beispielsweise, Datenbankmoduleigenschaften oder die Arbeitsbereichsauflistung zugreifen.  Siehe "impliziten Verwendung von dem standardmäßigen Arbeitsbereich" unten.  
  
-   Erstellen Sie neue Arbeitsbereiche.  Rufen Sie [Fügen Sie an](../Topic/CDaoWorkspace::Append.md) auf, wenn Sie sie der Arbeitsbereichsauflistung hinzufügen möchten.  
  
-   Öffnen Sie einen vorhandenen Arbeitsbereichs in der Arbeitsbereichsauflistung.  
  
 Das Erstellen eines neuen Arbeitsbereichs, der noch nicht in der Arbeitsbereichsauflistung vorhanden ist, wird unter der [Erstellen Sie](../Topic/CDaoWorkspace::Create.md)\-Memberfunktion beschrieben.  Arbeitsbereichsobjekte bestehen nicht auf eine Art von zwischen datababase Modulsitzungen weiter.  Wenn die Anwendungslinks MFC statisch, die Anwendung beenden das Datenbankmodul nicht initialisiert.  Wenn die Anwendungslinks dynamisch mit MFC, das Datenbankmodul nicht initialisiert wird, wenn die MFC\-DLL entladen wird.  
  
 Die standardmäßigen Arbeitsbereich explizit öffnen oder das Öffnen eines vorhandenen Arbeitsbereichs in den zugeordneten Auflistung, wird auf der [Geöffnet](../Topic/CDaoWorkspace::Open.md)\-Memberfunktion beschrieben.  
  
 Beenden Sie eine Arbeitsbereichssitzung, indem Sie den Arbeitsbereich mit der [Abschluss](../Topic/CDaoWorkspace::Close.md)\-Memberfunktion schließen.  **Schließen** schließt alle Datenbanken, die Sie vorher nicht geschlossen haben und setzt über nicht mit Commit bestätigten Transaktionen zurück.  
  
## Transaktionen  
 DAO verwaltet Transaktionen auf der Arbeitsbereichsebene; Daher gelten Transaktionen für ein Arbeitsbereich mit der geöffneten Datenbanken mehrere für alle Datenbanken zu.  Wenn beispielsweise zwei Datenbanken nicht mit Commit bestätigte Updates haben und Sie [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md) aufrufen, werden alle Aktualisierungen übernommen.  Wenn Sie Transaktionen zu einer einzelnen Datenbank beschränken möchten, benötigen Sie ein separates Arbeitsbereichsobjekt für sie.  
  
## Impliziter Verwendung von dem standardmäßigen Arbeitsbereich  
 Standardarbeitsbereich verwendet MFC aus DAO implizit unter folgenden Umständen:  
  
-   Wenn Sie erstellen, ein neues Objekt `CDaoDatabase` jedoch so nicht durch ein vorhandenes Objekt `CDaoWorkspace` ausführen, erstellt ein temporäres MFC Arbeitsbereichsobjekt für Sie, das dem Standardarbeitsbereich DAO entspricht.  Wenn Sie so für mehrere Datenbanken ausführen, werden alle Datenbankobjekte dem standardmäßigen Arbeitsbereich zugeordnet.  Sie können auf den Arbeitsbereich einer Datenbank von einem `CDaoDatabase` Datenmember zugreifen.  
  
-   Auch wenn ein `CDaoRecordset`\-Objekt erstellen, ohne einen Zeiger auf ein Objekt `CDaoDatabase` anzugeben, MFC erstellt ein temporäres Datenbankobjekt und, durch Erweiterung, ein temporäres Arbeitsbereichsobjekt.  Sie können die Datenbank eines Recordsets und indirekt auf den Arbeitsbereich, durch einen `CDaoRecordset` Datenmember zugreifen.  
  
## Andere Vorgänge  
 Andere Datenbankvorgänge werden auch, wie Reparatur einer beschädigten Datenbank oder Komprimieren einer Datenbank bereitgestellt.  
  
 Informationen über DAO direkt aufrufen und über DAO\-Sicherheit, finden Sie unter [Technischer Hinweis 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoWorkspace`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)