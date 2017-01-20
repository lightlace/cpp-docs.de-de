---
title: "CDatabase Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CDatabase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDatabase-Klasse"
  - "Datenbankklassen [C++], ODBC"
  - "Datenbankverbindungen [C++], CDatabase-Klasse"
  - "MFC [C++], ODBC"
  - "ODBC [C++], CDatabase-Klasse"
  - "ODBC database class"
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
caps.handback.revision: "14"
ms.author: "mblome"
manager: "ghogen"
---
# CDatabase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Verbindung zu einer Datenquelle dar, durch die Sie die Datenquelle ausgeführt werden können.  
  
## Syntax  
  
```  
  
class CDatabase : public CObject  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDatabase::CDatabase](../Topic/CDatabase::CDatabase.md)|Erstellt ein `CDatabase`\-Objekt.  Sie müssen das Objekt initialisieren, indem Sie `OpenEx` oder **Öffnen** aufrufen.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDatabase::BeginTrans](../Topic/CDatabase::BeginTrans.md)|Startet eine Transaktion "" \- Eine umkehrbare Aufrufe `AddNew`, zu **Bearbeiten**, zu **Löschen** und zu **Update**\-Memberfunktionen der Klasse `CRecordset` auf der verbundenen Datenquelle.  Die Datenquelle muss Transaktionen unterstützen, damit **BeginTrans** jeden Auswirkungen hat.|  
|[CDatabase::BindParameters](../Topic/CDatabase::BindParameters.md)|Vor dem Aufrufen von `CDatabase::ExecuteSQL` ermöglicht das Bindungsparametern.|  
|[CDatabase::Cancel](../Topic/CDatabase::Cancel.md)|Bricht einen asynchronen Vorgang oder einen Prozess aus einem zweiten Thread ab.|  
|[CDatabase::CanTransact](../Topic/CDatabase::CanTransact.md)|Gibt Wert ungleich 0 zurück, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDatabase::CanUpdate](../Topic/CDatabase::CanUpdate.md)|Gibt Wert ungleich 0 zurück, wenn das Objekt `CDatabase` aktualisierbar ist nicht \(schreibgeschützt\).|  
|[CDatabase::Close](../Topic/CDatabase::Close.md)|Schließt die Datenquellenverbindung.|  
|[CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md)|Schließt eine Transaktion ab, die von **BeginTrans** gestartet wird.  Befehle in der Transaktion, die die Datenquelle ändern, werden durchgeführt.|  
|[CDatabase::ExecuteSQL](../Topic/CDatabase::ExecuteSQL.md)|Führt eine SQL\-Anweisung aus.  Keine Datensätze werden zurückgegeben.|  
|[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md)|Identifiziert die Vorgänge, durch die Lesezeichen auf Recordsetobjekten erhalten bleiben.|  
|[CDatabase::GetConnect](../Topic/CDatabase::GetConnect.md)|Gibt die ODBC\-Verbindungszeichenfolge zurück, die verwendet wird, um das `CDatabase`\-Objekt einer Datenquelle herzustellen.|  
|[CDatabase::GetCursorCommitBehavior](../Topic/CDatabase::GetCursorCommitBehavior.md)|Identifiziert die Auswirkungen des eines Commits führens einer Transaktion auf einem geöffneten Recordset\-Objekt.|  
|[CDatabase::GetCursorRollbackBehavior](../Topic/CDatabase::GetCursorRollbackBehavior.md)|Identifiziert den Auswirkungen Zurücksetzen einer Transaktion auf einem geöffneten Recordset\-Objekt.|  
|[CDatabase::GetDatabaseName](../Topic/CDatabase::GetDatabaseName.md)|Gibt den Namen der Datenbank derzeit zurück.|  
|[CDatabase::IsOpen](../Topic/CDatabase::IsOpen.md)|Gibt Wert ungleich 0 zurück, wenn das Objekt gegenwärtig `CDatabase` mit einer Datenquelle verbunden ist.|  
|[CDatabase::OnSetOptions](../Topic/CDatabase::OnSetOptions.md)|Aufgerufen durch das Framework, um Standardverbindungsoptionen festzulegen.  Die Standardimplementierung legt den Abfragentimeoutwert fest.  Sie können diese Optionen vorzeitig wiederherstellen, indem Sie `SetQueryTimeout` aufrufen.|  
|[CDatabase::Open](../Topic/CDatabase::Open.md)|Richtet eine Verbindung zu einer Datenquelle ein \(über einen ODBC\-Treiber\).|  
|[CDatabase::OpenEx](../Topic/CDatabase::OpenEx.md)|Richtet eine Verbindung zu einer Datenquelle ein \(über einen ODBC\-Treiber\).|  
|[CDatabase::Rollback](../Topic/CDatabase::Rollback.md)|Rückseitenänderungen vorgenommen während der aktuellen Transaktion.  Die Datenquelle wird auf den vorherigen Zustand zurück, wie am **BeginTrans** Aufruf definiert, unverändert.|  
|[CDatabase::SetLoginTimeout](../Topic/CDatabase::SetLoginTimeout.md)|Legt die Anzahl der Sekunden nach von Datenquellenverbindungsversuchswillenstimeout fest.|  
|[CDatabase::SetQueryTimeout](../Topic/CDatabase::SetQueryTimeout.md)|Legt die Anzahl der Sekunden nach von Datenbankabfragevorgangswillenstimeout fest.  Wirkt sich alle folgende Recordset **Öffnen**, `AddNew`, **Bearbeiten** und **Löschen** Aufrufe.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CDatabase::m\_hdbc](../Topic/CDatabase::m_hdbc.md)|Verbindungshandle der Open Database Connectivity \(ODBC\) an eine Datenquelle.  Typ **HDBC**.|  
  
## Hinweise  
 Eine Datenquelle ist eine bestimmte Instanz von Daten, die von oder Datenbankmanagementsystem \(DBMS\) gehostet werden.  Zu den Microsoft SQL Server, Microsoft Access\-, Borland\-dBASE und xBASE.  Sie können eine oder mehrere `CDatabase`\-Objekte besitzen, die in der Anwendung aktiv sind.  
  
> [!NOTE]
>  Wenn Sie mit den Datenzugriffsobjekten \(DAO\) Klasse anstatt die Klassen der Open Database Connectivity \(ODBC\), Verwendungsklasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) stattdessen arbeiten.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Um `CDatabase` zu verwenden, erstellen Sie ein `CDatabase`\-Objekt und Aufrufen ihrer `OpenEx`\-Memberfunktion auf.  Dadurch wird eine Verbindung.  Wenn Sie dann `CRecordset`\-Objekte für das Funktionieren auf der verbundenen Datenquelle erstellen, führen Sie den Recordsetkonstruktor ein Zeiger auf dem `CDatabase`\-Objekt.  Wenn Sie beenden, die Verbindung zu verwenden, rufen Sie die Memberfunktion auf **Schließen** und zerstören Sie das `CDatabase`\-Objekt.  **Schließen** schließt alle Recordsets, die Sie vorher nicht geschlossen haben.  
  
 Weitere Informationen zu `CDatabase`, finden Sie in Artikel [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md) und [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## Anforderungen  
 **Header:**  afxdb.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)