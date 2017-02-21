---
title: "CDaoDatabase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoDatabase class"
  - "CDaoDatabase class, and workspace"
  - "CDaoDatabase class, vs. CDatabase class"
  - "CDatabase-Klasse, vs. CDaoDatabase class"
  - "Datenbankklassen [C++], DAO"
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDaoDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Verbindung zu einer Datenbank dar, durch die Sie die Daten angewendet werden können.  
  
## Syntax  
  
```  
class CDaoDatabase : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](../Topic/CDaoDatabase::CDaoDatabase.md)|Erstellt ein `CDaoDatabase`\-Objekt.  Rufen Sie **Öffnen** auf, um das Objekt zu einer Datenbank herzustellen.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](../Topic/CDaoDatabase::CanTransact.md)|Gibt Wert ungleich 0 wenn die Datenbankstütztransaktionen zurück.|  
|[CDaoDatabase::CanUpdate](../Topic/CDaoDatabase::CanUpdate.md)|Gibt Wert ungleich 0 zurück, wenn das Objekt `CDaoDatabase` aktualisierbar ist nicht \(schreibgeschützt\).|  
|[CDaoDatabase::Close](../Topic/CDaoDatabase::Close.md)|Schließt die Datenbankverbindung.|  
|[CDaoDatabase::Create](../Topic/CDaoDatabase::Create.md)|Erstellt das zugrunde liegende DAO\-Datenbank\-Objekt und initialisiert das `CDaoDatabase`\-Objekt.|  
|[CDaoDatabase::CreateRelation](../Topic/CDaoDatabase::CreateRelation.md)|Definiert eine neue Beziehung zwischen den Tabellen in der Datenbank.|  
|[CDaoDatabase::DeleteQueryDef](../Topic/CDaoDatabase::DeleteQueryDef.md)|Löscht ein Querydef\-Objekt, das in der Querydefauflistung der Datenbank gespeichert wird.|  
|[CDaoDatabase::DeleteRelation](../Topic/CDaoDatabase::DeleteRelation.md)|Löscht eine vorhandene Beziehung zwischen Tabellen in der Datenbank.|  
|[CDaoDatabase::DeleteTableDef](../Topic/CDaoDatabase::DeleteTableDef.md)|Löscht die Definition einer Tabelle in der Datenbank.  Hierdurch wird die tatsächliche Tabelle mit sämtlichen Daten.|  
|[CDaoDatabase::Execute](../Topic/CDaoDatabase::Execute.md)|Führt eine Aktionsabfrage aus.  Aufrufen von **Execute** für eine Abfrage gibt, dass sich eine Ausnahme auslöst ergibt.|  
|[CDaoDatabase::GetConnect](../Topic/CDaoDatabase::GetConnect.md)|Gibt die Verbindungszeichenfolge zurück, die verwendet wird, um das `CDaoDatabase`\-Objekt zu einer Datenbank herzustellen.  Wird für ODBC.|  
|[CDaoDatabase::GetName](../Topic/CDaoDatabase::GetName.md)|Gibt den Namen der Datenbank derzeit zurück.|  
|[CDaoDatabase::GetQueryDefCount](../Topic/CDaoDatabase::GetQueryDefCount.md)|Gibt die Anzahl der Abfragen zurück, die für die Datenbank definiert sind.|  
|[CDaoDatabase::GetQueryDefInfo](../Topic/CDaoDatabase::GetQueryDefInfo.md)|Gibt Informationen über eine bestimmte Abfrage zurück, die in der Datenbank definiert ist.|  
|[CDaoDatabase::GetQueryTimeout](../Topic/CDaoDatabase::GetQueryTimeout.md)|Gibt die Anzahl der Sekunden nach von Datenbankabfragevorgangswillenstimeout zurück.  Wirkt sich alle geöffneten nachfolgendes, fügt neue, Aktualisieren und Bearbeitungsvorgänge und andere Vorgänge auf ODBC\-Datenquellen \(nur\) wie **Execute** Aufrufen hinzu.|  
|[CDaoDatabase::GetRecordsAffected](../Topic/CDaoDatabase::GetRecordsAffected.md)|Gibt die Anzahl der Datensätze zurück, die durch das letzte Update, Bearbeiten betroffen sind oder fügt Vorgang oder durch einen Aufruf **Execute** hinzu.|  
|[CDaoDatabase::GetRelationCount](../Topic/CDaoDatabase::GetRelationCount.md)|Gibt die Anzahl von Verbindungen zurück, die zwischen Tabellen in der Datenbank definiert werden.|  
|[CDaoDatabase::GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md)|Gibt Informationen über eine bestimmte Beziehung zurück, die zwischen Tabellen in der Datenbank definiert ist.|  
|[CDaoDatabase::GetTableDefCount](../Topic/CDaoDatabase::GetTableDefCount.md)|Gibt die Anzahl der Tabellen zurück, die in der Datenbank definiert werden.|  
|[CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md)|Gibt Informationen über eine bestimmte Tabelle in der Datenbank zurück.|  
|[CDaoDatabase::GetVersion](../Topic/CDaoDatabase::GetVersion.md)|Gibt die Version des Datenbankmoduls zurück, das der Datenbank zugeordnet ist.|  
|[CDaoDatabase::IsOpen](../Topic/CDaoDatabase::IsOpen.md)|Gibt Wert ungleich 0 zurück, wenn das Objekt gegenwärtig `CDaoDatabase` mit einer Datenbank verbunden ist.|  
|[CDaoDatabase::Open](../Topic/CDaoDatabase::Open.md)|Richtet eine Verbindung mit einer Datenbank her.|  
|[CDaoDatabase::SetQueryTimeout](../Topic/CDaoDatabase::SetQueryTimeout.md)|Legt die Anzahl von Sekunden fest, nach der Datenbankabfragevorgänge \(nur auf ODBC\-Datenquellen\) Timeout.  Wirkt sich alle geöffneten nachfolgendes, fügt neue, Aktualisierungs\- und Löschvorgänge hinzu.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDaoDatabase::m\_pDAODatabase](../Topic/CDaoDatabase::m_pDAODatabase.md)|Ein Zeiger auf den zugrunde liegenden DAO\-Datenbank\-Objekt.|  
|[CDaoDatabase::m\_pWorkspace](../Topic/CDaoDatabase::m_pWorkspace.md)|Ein Zeiger auf [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)\-Objekt, das die Datenbank enthält und sein Transaktionsleerzeichen definiert.|  
  
## Hinweise  
 Informationen zu den unterstützten Datenbankformate, finden Sie die [GetName](../Topic/CDaoWorkspace::GetName.md)\-Memberfunktion.  Sie können eine oder mehrere `CDaoDatabase`\-Objekte besitzen, die in einem angegebenen "Arbeitsbereich aktiv sind," dargestellt durch eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)\-Objekt.  Der Arbeitsbereich verwaltet eine Auflistung offener Datenbankobjekte bei, die Datenbankauflistung aufgerufen.  
  
> [!NOTE]
>  Die MFC\-DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage ODBC unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  \- Klasse `CDaoDatabase` stellt eine Schnittstelle, die zu der der ODBC\-Klasse [CDatabase](../../mfc/reference/cdatabase-class.md) ähnelt.  Der Hauptunterschied liegt darin, dass `CDatabase` auf das DBMS von Open Database Connectivity \(ODBC\) und einen ODBC\-Treiber für dieses DBMS zugreift.  `CDaoDatabase` greift auf Daten über ein Datenzugriffsobjekt \(DAO\) auf Grundlage das Microsoft Jet\-Datenbankmodul zu.  Im Allgemeinen sind die MFC\-Klassen auf Grundlage DAO besser geeignet als die MFC\-Klassen auf Grundlage ODBC; die DAO\-basierten Klassen machen die Daten ein und enthalten durch ODBC\-Treiber, über ein eigenes Datenbankmodul.  Die DAO\-basierten Klassen unterstützen auch Operationen der Datendefinitionssprache \(Data Definition Language\), wie das Hinzufügen von Tabellen zu Klassen, ohne zu müssen, DAO direkt aufzurufen.  
  
## Verwendung  
 Sie können Datenbankobjekte implizit erstellen, wenn Sie Recordset\-Objekte erstellen.  Sie können jedoch Datenbankobjekte auch explizit erstellen.  Um eine vorhandene Datenbank mit `CDaoDatabase` explizit zu verwenden, führen Sie eine der folgenden Aktionen aus:  
  
-   Erstellen Sie ein `CDaoDatabase`\-Objekt und einen Zeiger an einem geöffneten [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)\-Objekt.  
  
-   Oder erstellen Sie ein `CDaoDatabase`\-Objekt, ohne den Arbeitsbereich anzugeben \(MFC erstellt ein temporäres Arbeitsbereichsobjekt\).  
  
 Um eine neue Microsoft Jet\-Datenbanken \(.MDB\) zu erstellen, erstellen Sie ein `CDaoDatabase`\-Objekt und Aufrufen ihrer [Erstellen Sie](../Topic/CDaoDatabase::Create.md)\-Memberfunktion auf.  Rufen Sie **Öffnen***nicht* nach **Create** auf.  
  
 Um eine vorhandene Datenbank zu öffnen, erstellen Sie ein `CDaoDatabase`\-Objekt und Aufrufen ihrer [Öffnen Sie](../Topic/CDaoDatabase::Open.md)\-Memberfunktion auf.  
  
 Alle Techniken fügt das DAO\-Datenbank\-Objekt zu Datenbanken Auflistung des Arbeitsbereichs an und öffnet eine Verbindung mit den Daten.  Wenn Sie dann [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) oder [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md)\-Objekte für das Funktionieren auf der verbundenen Datenbank erstellen, führen Sie die Konstruktoren für diese Objekte ein Zeiger auf dem `CDaoDatabase`\-Objekt.  Wenn Sie beenden, die Verbindung zu verwenden, rufen Sie die Memberfunktion auf [Schließen Sie](../Topic/CDaoDatabase::Close.md) und zerstören Sie das `CDaoDatabase`\-Objekt.  **Schließen** schließt alle Recordsets, die Sie vorher nicht geschlossen haben.  
  
## Transaktionen  
 Datenbanktransaktionsverarbeitung wird auf der Arbeitsbereichsebene angegeben \- finden Sie die [BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md), [CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md) und [Rollback](../Topic/CDaoWorkspace::Rollback.md)\-Memberfunktionen der Klasse `CDaoWorkspace`.  
  
## ODBC\-Verbindungen  
 Es wird empfohlen, mit ODBC\-Datenquellen besteht darin, externe Tabellen einer Datenbank Microsoft Jet\-Datenbanken \(.MDB\) anfügen.  
  
## Auflistungen  
 Jede Datenbank behält seine eigene Auflistungen tabledef\-, Querydef, Recordset und Beziehungsobjekte bei.  \- Klasse `CDaoDatabase` stellt Memberfunktionen zur Bearbeitung dieser Objekte.  
  
> [!NOTE]
>  Die Objekte werden in DAO, nicht im MFC\-Datenbankobjekt gespeichert.  MFC stellt Klassen für tabledef\-, Querydef und Recordset\-Objekte jedoch nicht für Beziehungsobjekte bereit.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## Anforderungen  
 **Header:**  afxdao.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CDaoException Class](../../mfc/reference/cdaoexception-class.md)