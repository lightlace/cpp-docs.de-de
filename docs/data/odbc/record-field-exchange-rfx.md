---
title: "Datensatzfeldaustausch (RFX)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Daten [MFC]"
  - "Daten [MFC], Verschieben zwischen Quellen und Recordsets"
  - "Datenbankklassen [C++], RFX"
  - "ODBC [C++], RFX"
  - "RFX (ODBC) [C++]"
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Datensatzfeldaustausch (RFX)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die MFC\-ODBC\-Datenbankklassen automatisieren die Übertragung von Daten zwischen der Datenquelle und einem [Recordset](../../data/odbc/recordset-odbc.md)\-Objekt.  Wenn Sie eine Klasse von [CRecordset](../../mfc/reference/crecordset-class.md) ableiten und das gesammelte Abrufen von Zeilen nicht verwenden, werden die Daten mit dem Datensatzfeldaustausch\-Mechanismus \(Record Field Exchange, RFX\) übertragen.  
  
> [!NOTE]
>  Wenn Sie in einer abgeleiteten `CRecordset`\-Klasse das gesammelte Abrufen von Zeilen implementiert haben, überträgt das Framework Daten mithilfe des Sammel\-Datensatzfeldaustauschs \(Bulk\-RFX\).  Weitere Informationen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX ähnelt dem Dialogdatenaustausch \(Dialog Data Exchange, DDX\).  Die Übertragung von Daten zwischen einer Datenquelle und den Felddatenmembern eines Recordsets erfordert mehrere Aufrufe der Recordsetfunktion [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) und beträchtliche Interaktion zwischen dem Framework und [ODBC](../../data/odbc/odbc-basics.md).  Der RFX\-Mechanismus ist typsicher und erspart Ihnen den Aufruf von ODBC\-Funktionen, z. B. **::SQLBindCol**.  Weitere Informationen über DDX finden Sie unter [Dialogdatenaustausch \(DDX, Dialog Data Exchange\) und Dialogdatenvalidierung \(DDV, Dialog Data Validation\)](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX ist größtenteils transparent für den Benutzer.  Wenn Sie Recordset\-Klassen mit dem MFC\-Anwendungs\-Assistenten oder **Klasse hinzufügen** deklarieren \(wie beschrieben unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\), wird RFX automatisch integriert.  Die Recordset\-Klasse muss von der **CRecordset\-**Basisklasse abgeleitet sein, die vom Framework zur Verfügung gestellt wird.  Mit dem MFC\-Anwendungs\-Assistenten können Sie eine erste Recordset\-Klasse erstellen.  Mit **Klasse hinzufügen** können Sie bei Bedarf weitere Recordset\-Klassen hinzufügen.  Weitere Informationen und Beispiele hierzu finden Sie unter [Hinzufügen eines MFC\-ODBC\-Consumers](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 In den folgenden drei Fällen müssen Sie ein paar Zeilen RFX\-Code einfügen:  
  
-   Sie möchten parametrisierte Abfragen verwenden.  Weitere Informationen hierzu finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   Sie möchten Joins ausführen, also ein Recordset für Spalten aus zwei oder mehr Tabellen verwenden.  Weitere Informationen hierzu finden Sie unter [Recordset: Ausführen eines Joins \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Sie möchten Datenspalten dynamisch binden.  Dies ist seltener als die Parametrisierung.  Weitere Informationen finden Sie unter [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Eine detaillierte Erklärung der Funktionsweise von RFX finden Sie unter [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 In den folgenden Themen wird die Verwendung der Recordset\-Objekte ausführlich erläutert:  
  
-   [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Datensatzfeldaustausch: Verwenden der RFX\-Funktionen](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## Siehe auch  
 [Open Database Connectivity \(ODBC\)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Nutzen von MFC\-ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)