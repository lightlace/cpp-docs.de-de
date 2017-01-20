---
title: "Datenbankunterst&#252;tzung, MFC-Anwendungs-Assistent"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.database"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-Anwendungs-Assistent, Datenbankunterstützung"
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: 9
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Datenbankunterst&#252;tzung, MFC-Anwendungs-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Seite enthält Optionen, mit deren Hilfe Sie den Umfang der Datenbankunterstützung \(sowie ggf. eine Datenquelle\) für das Projekt festlegen können.  
  
 **Datenbankunterstützung**  
 Legt den Umfang der Datenbankunterstützung für das Projekt fest.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Kein**|Bietet keine Datenbankunterstützung.  Dies ist die Standardoption.|  
|**Nur Headerdateien**|Bietet grundlegende Datenbankunterstützung für die Anwendung.<br /><br /> <ul><li>Wenn Sie unter **Clienttyp** ODBC\-Unterstützung auswählen, fügt der MFC\-Anwendungs\-Assistent dem Projekt die Headerdatei AFXDB.H sowie Linkbibliotheken hinzu.  Es werden jedoch keine datenbankspezifischen Klassen erstellt.  Später können Sie Recordsets für die Überprüfung und Aktualisierung von Datensätzen erstellen.</li><li>Wenn Sie unter **Clienttyp** OLE DB\-Unterstützung auswählen, werden die folgenden Headerdateien hinzugefügt:<br /><br /> <ul><li>ATLBASE.H</li><li>AFXOLEDB.H</li><li>ATLPLUS.H</li></ul></li></ul>|  
|**Datenbankansicht ohne Dateiunterstützung**|Umfasst Datenbank\-Headerdateien, Linkbibliotheken, eine Datensatzansicht und ein Recordset. \(Nur für Anwendungen verfügbar, für die auf der Seite [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert wurde.\) Diese Option beinhaltet Dokumentunterstützung, jedoch keine Serialisierungsunterstützung.  Wenn Sie eine Datenbankansicht einbinden, müssen Sie die Quelle der Daten angeben.|  
|**Datenbankansicht mit Dateiunterstützung**|Umfasst Datenbank\-Headerdateien, Linkbibliotheken, eine Datensatzansicht und ein Recordset. \(Nur für Anwendungen verfügbar, für die auf der Seite **Anwendungstyp** die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert wurde.\) Diese Option unterstützt die Dokumentserialisierung, die Sie beispielsweise zur Aktualisierung einer Benutzerprofildatei einsetzen können.  Datenbankanwendungen arbeiten in der Regel auf der Basis einzelner Datensätze und nicht auf der Basis einzelner Dateien. Aus diesem Grund müssen sie nicht serialisiert werden.  Unter Umständen benötigen Sie die Serialisierung jedoch für andere Aufgaben.  Wenn Sie eine Datenbankansicht einbinden, müssen Sie die Quelle der Daten angeben.|  
  
> [!NOTE]
>  Wenn Sie unter **Datenbankunterstützung** entweder **Datenbankansicht ohne Dateiunterstützung** oder **Datenbankansicht mit Dateiunterstützung** auswählen, werden die Ansichtsklassen je nach der Auswahl unter **Clienttyp** unterschiedlich abgeleitet. Siehe dazu folgende Erläuterungen:  
  
-   Wenn Sie unter **Clienttyp** die Option **ODBC** auswählen, wird die Ansichtsklasse der Anwendung von [CRecordView](../../mfc/reference/crecordview-class.md) abgeleitet.  Diese Klasse ist mit einer von [CRecordset](../../mfc/reference/crecordset-class.md) abgeleiteten Klasse verbunden, die ebenfalls vom MFC\-Anwendungs\-Assistenten erstellt wird.  Mit dieser Option erhalten Sie eine formularbasierte Anwendung, in der die Datensatzansicht verwendet wird, um Datensätze anhand ihrer Recordsets anzuzeigen und zu aktualisieren.  
  
-   Wenn Sie unter **Clienttyp** die Option **OLE DB** auswählen, wird die Ansichtsklasse von [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md) abgeleitet und ist zusätzlich mit einer von [CTable](../../data/oledb/ctable-class.md) oder [CCommand](../../data/oledb/ccommand-class.md) abgeleiteten Klasse verbunden.  
  
 **Clienttyp**  
 Gibt an, ob das Projekt OLE DB\- oder ODBC\-Klassen verwendet.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**OLE DB**|Wenn diese Option ausgewählt ist, und Sie auf die Schaltfläche **Datenquelle** klicken, wird der Assistent für **Datenverknüpfungseigenschaften** aufgerufen. Dieser Assistent unterstützt Sie dabei, eine Verbindung mit einer OLE DB\-Datenquelle herzustellen.|  
|**ODBC**|Wenn diese Option ausgewählt ist, und Sie auf die Schaltfläche **Datenquelle** klicken, wird der Assistent zum **Auswählen einer Datenquelle** aufgerufen. Dieser Assistent unterstützt Sie dabei, eine Verbindung mit einer ODBC\-Datenquelle herzustellen.|  
  
 **Datenquelle**  
 Klicken Sie auf die Schaltfläche **Datenquelle**, um eine Datenquelle unter Verwendung des angegebenen Treibers oder Anbieters und der angegebenen Datenbank einzurichten.  Wenn Sie unter **Clienttyp** die Option OLE DB ausgewählt haben, wird durch Klicken auf diese Schaltfläche das Dialogfeld **Eigenschaften von Datenverknüpfung** geöffnet.  Wenn Sie unter **Clienttyp** die Option **ODBC** auswählen, wird durch Klicken auf diese Schaltfläche das Dialogfeld **Datenquelle auswählen** geöffnet.  Diese Option ist nur verfügbar, wenn Sie eine Datenbankansicht in die Anwendung aufnehmen.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Eigenschaften von Datenverknüpfung** \(OLE DB\)|Richtet die angegebene Datenquelle unter Verwendung des festgelegten OLE DB\-Anbieters ein.  Dabei sind folgende Angaben erforderlich: OLE DB\-Anbieter, der Speicherort der Daten, die Datenquelle, ein Benutzername und \(optional\) ein Kennwort.  Ausführliche Informationen zu diesem Dialogfeld finden Sie unter **Datenquelle** im [ATL\-OLE DB\-Consumer\-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Datenquelle auswählen** \(ODBC\)|Richtet die angegebene Datenquelle unter Verwendung des festgelegten ODBC\-Treibers ein.  Sie müssen eine Datenquelle benennen, um eine Tabelle für die Datenquelle auszuwählen.  Der Assistent bindet alle Spalten der Tabelle an die Membervariablen einer von `CRecordset` abgeleiteten Klasse.  Ausführliche Informationen zu diesem Dialogfeld finden Sie unter **Datenquelle** im [MFC\-ODBC\-Consumer\-Assistenten](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  In früheren Versionen wurde durch Drücken der UMSCHALTTASTE und gleichzeitiges Klicken auf die Schaltfläche **Datenquelle** ein Dialogfeld zum Öffnen von Dateien geöffnet, in dem eine Datenverknüpfungsdatei \(.udl\) ausgewählt werden konnte.  Diese Funktion wird nicht mehr unterstützt.  
  
 **Attributierte Datenbankklasse erstellen**  
 Nur für OLE DB\-Clients verfügbar.  Legt fest, ob die Datenbankklassen im erstellten Projekt Attribute verwenden.  
  
 **Alle Spalten binden**  
 Nur für ODBC\-Clients verfügbar.  Legt fest, ob alle Spalten in der ausgewählten Tabelle gebunden werden.  Wenn Sie dieses Kontrollkästchen aktivieren, werden alle Spalten gebunden. Andernfalls werden keine Spalten gebunden, und Sie müssen sie manuell in der Recordsetklasse binden.  
  
 **Typ**  
 Nur für ODBC\-Clients verfügbar.  Legt fest, ob es sich beim Recordset um ein Dynaset oder eine Momentaufnahme handelt. Siehe dazu folgende Tabelle.  
  
|Option|**Beschreibung**|  
|------------|----------------------|  
|**Dynaset**|Gibt an, dass das Recordset ein Dynaset ist.  Ein Dynaset ist das Ergebnis einer Abfrage, bei der die abgefragten Datenbankinformationen mithilfe einer indizierten Sicht dargestellt werden.  Durch ein Dynaset wird lediglich ein integraler Index der ursprünglichen Daten zwischengespeichert, wodurch Leistungsvorteile gegenüber einer Momentaufnahme erzielt werden.  Der Index zeigt direkt auf jeden einzelnen, im Ergebnis zurückgegebenen Datensatz und gibt an, ob ein Datensatz entfernt wurde.  Sie haben außerdem Zugriff auf aktualisierte Informationen in den abgefragten Datensätzen.|  
|Momentaufnahme|Gibt an, dass das Recordset eine Momentaufnahme ist.  Eine Momentaufnahme ist das Ergebnis einer Abfrage und stellt ein Abbild einer Datenbank zu einem bestimmten Zeitpunkt dar.  Alle durch die Abfrage gefundenen Datensätze werden zwischengespeichert, sodass Sie keine Änderungen gegenüber den ursprünglichen Datensätzen feststellen können.|  
  
## Siehe auch  
 [MFC\-Anwendungs\-Assistent](../../mfc/reference/mfc-application-wizard.md)