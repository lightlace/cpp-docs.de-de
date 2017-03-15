---
title: "Reihenfolge der Operationen zur Erstellung Datenbankanwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Anwendungen [MFC], Datenbank"
  - "Datenbankanwendungen [C++]"
  - "Datenbankanwendungen [C++], Erstellen"
  - "MFC [C++], Datenbankanwendungen"
ms.assetid: 9371da59-8536-43cd-8314-706ad320e2ec
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Reihenfolge der Operationen zur Erstellung Datenbankanwendungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle wird die Rolle und die Rolle des Frameworks in den Schreibendatenbank\-Anwendungen an.  
  
> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie ODBC für neue MFC\-Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
### Erstellen von Datenbankanwendungen  
  
|Aufgabe|Hierzu|Das Framework führt|  
|-------------|------------|-------------------------|  
|Entscheiden Sie, ob MFC ODBC\- oder DAO\-Klassen verwendet.|Verwenden Sie ODBC für neue MFC\-Projekte.  Mit DAO, um vorhandene Anwendungen nur beizubehalten.  Siehe [Sollte DAO oder ODBC verwenden?](../data/should-i-use-dao-or-odbc-q.md).  Allgemeine Informationen finden Sie im Artikel [Datenzugriffs\-Programmierung](../data/data-access-programming-mfc-atl.md).|Das Framework stellt Klassen bereit, die den Datenbankzugriff unterstützen.|  
|Erstellen Sie Ihr Anwendungsskelett mit Datenbankoptionen.|Führen Sie den MFC\-Anwendungs\-Assistenten aus.  Wählen Sie Optionen auf der Datenbank\-Supportseite aus.  Wenn eine Option auswählen, die eine Datensatzansicht erstellt, geben Sie auch an:<br /><br /> -   Datenquelle und Tabellenname oder Namen<br />-   Abfragenname oder \-Namen.|Der MFC\-Anwendungs\-Assistent erstellt Dateien und den notwendigen Include an.  Abhängig von Optionen, die Sie, die Dateien angeben, kann eine Recordset\-Klasse einschließen.|  
|Entwerfen Sie das Datenbankformular oder \-Formulare.|Verwenden Sie den Visual C\+\+\-Dialog\-Editor, um Steuerelemente auf den Dialogfeldvorlagenressourcen für die Datensatzansichts\-Klassen zu platzieren.|Der MFC\-Anwendungs\-Assistent erstellt eine leere Dialogfeldvorlagen\-Ressource, damit Sie füllen.|  
|Erstellen Sie zusätzliche Datensatzansicht und Recordset\-Klassen nach Bedarf.|Verwenden Sie die Klassenansicht, um die Klassen und den Dialog\-Editor erstellen, um die Ansichten zu entwerfen.|Klassenansicht erstellt zusätzliche Dateien für die neuen Klassen.|  
|Erstellen Sie Recordset\-Objekte nach Bedarf im Code.  Verwenden Sie ein Recordset, um Datensätze bearbeiten...|Recordset\-Klassen basieren auf die Klassen, die von [CRecordset](../mfc/reference/crecordset-class.md) mit den Assistenten abgeleitet werden.|ODBC Datensatzfeldaustausch \(RFX\) für den Datenaustausch den Felddatenmembern zwischen der Datenbank und des Recordsets.  Wenn Sie eine Datensatzansicht, Datenaustausch zwischen dem des Dialogdatenaustauschs \(DDX\) zwischen dem Recordset und die Steuerelemente der Datensatzansicht verwenden.|  
|... oder erstellen Sie explizites [CDatabase](../mfc/reference/cdatabase-class.md) in Code für jede Datenbank, die Sie öffnen möchten.|Basieren Sie die Recordset\-Objekte auf den Datenbankobjekten.|Das Datenbankobjekt stellt eine Schnittstelle zur Datenquelle.|  
|Bindungsdatenspalten für das Recordset dynamisch.|In ODBC fügen Sie Code der abgeleitete Recordset\-Klasse hinzu, um die Bindung zu verwalten.  Siehe den Artikel [Recordset: Dynamisches Binden von Datenspalten \(ODBC\)](../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||  
  
## Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC\-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Reihenfolge der Operationen zur Erstellung von OLE\-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Operationssequenz zur Erstellung von ActiveX\-Steuerelementen](../mfc/sequence-of-operations-for-creating-activex-controls.md)