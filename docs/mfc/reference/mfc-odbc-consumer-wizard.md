---
title: "MFC-ODBC-Consumer-Assistent | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.class.mfc.consumer.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ODBC-Consumer-Assistent"
  - "Assistenten [MFC]"
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC-ODBC-Consumer-Assistent
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fügen Sie die Zusammenfassung der Suchergebnisse hier ein.  
  
 Dieser Assistent richtet eine ODBC\-Recordsetklasse und die Datenbindungen ein, die für den Zugriff auf die angegebene Datenquelle erforderlich sind.  
  
## UIElement-Liste  
 **Datenquelle**  
 Über die Schaltfläche **Datenquelle** können Sie die angegebene Datenquelle unter Verwendung des jeweiligen ODBC\-Treibers einrichten.  Weitere Informationen über Datenquellendateien \(DSN\) finden Sie im ODBC\-SDK unter [Dateidatenquellen](https://msdn.microsoft.com/en-us/library/ms715401.aspx).  Das Dialogfeld **Datenquelle auswählen** verfügt über zwei Registerkarten:  
  
-   Registerkarte **Dateidatenquelle**: Im Feld **Suchen in** ist das Verzeichnis angegeben, in dem die als Datenquellen zu verwendenden Dateien ausgewählt werden.  Standardmäßig wird das Verzeichnis **\\Programme\\Gemeinsame Dateien\\ODBC\\Data Sources** verwendet.  Die vorhandenen Dateidatenquellen \(**.dsn**\) werden im Hauptlistenfeld angezeigt.  Sie können die Datenquellen entweder im [ODBC\-Datenquellenadministrator](https://msdn.microsoft.com/en-us/library/ms714024.aspx) auf der Registerkarte **Datei\-DSN** im Voraus einrichten, oder Sie erstellen in diesem Dialogfeld neue Datenquellen.  
  
     Um in diesem Dialogfeld eine neue Dateidatenquelle zu erstellen, klicken Sie auf **Neu**, um einen DSN\-Namen festzulegen. Das Dialogfeld **Neue Datenquelle erstellen** wird angezeigt.  Im Dialogfeld **Neue Datenquelle erstellen** wählen Sie einen geeigneten Treiber aus und klicken auf **Weiter**. Klicken Sie auf **Durchsuchen**, und wählen Sie den Namen der Datei aus, die als Datenquelle verwendet werden soll \(um andere Dateien als DSN\-Dateien, z. B. XLS\-Dateien, anzuzeigen, müssen Sie **Alle Dateien** auswählen\). Klicken Sie auf **Weiter** und dann auf **Fertig stellen**. \(Wenn Sie keine DSN\-Datei ausgewählt haben, wird ein treiberspezifisches Dialogfeld, z. B. "ODBC Microsoft Excel Setup" angezeigt und die Datei in eine DSN\-Datei konvertiert.\)  
  
    > [!NOTE]
    >  Sie können eine neue Dateidatenquelle auch im Voraus erstellen, indem Sie den ODBC\-Datenquellenadministrator ausführen.  Wählen Sie im **Startmenü** die Option **Einstellungen**, **Systemsteuerung**, **Verwaltung**, **Datenquellen \(ODBC\)** und dann **ODBC\-Datenquellenadministrator**.  
  
     Im Feld **DSN\-Name** können Sie einen Namen für die Dateidatenquelle angeben.  Dabei müssen Sie sicherstellen, dass der DSN\-Name mit der richtigen Dateierweiterung endet, z. B. **.xls** für Excel\-Dateien oder **.mdb** für Access\-Dateien.  
  
     Weitere Informationen über Datenquellendateien \(DSN\) finden Sie im ODBC\-SDK unter [Dateidatenquellen](https://msdn.microsoft.com/en-us/library/ms715401.aspx).  
  
-   Registerkarte **Computerdatenquelle**: Auf dieser Registerkarte sind System\- und Benutzerdatenquellen aufgelistet.  Benutzerdatenquellen sind spezifisch für einen bestimmten Benutzer dieses Computers.  Systemdatenquellen können von allen Benutzern dieses Computers oder innerhalb eines systemweiten Dienstes verwendet werden.  Weitere Informationen finden Sie im ODBC\-SDK unter [Computerdatenquellen](https://msdn.microsoft.com/en-us/library/ms710952.aspx).  
  
 Weitere Informationen über ODBC\-Datenquellen finden Sie im ODBC\-SDK unter [Datenquellen](https://msdn.microsoft.com/en-us/library/ms711688.aspx).  
  
 Klicken Sie zum Fertigstellen auf **OK**.  Das Dialogfeld **Datenbankobjekt auswählen** wird geöffnet.  In diesem Dialogfeld wählen Sie die Tabelle oder Ansicht aus, die vom Consumer verwendet wird.  Sie können mehrere Ansichten und Tabellen auswählen, indem Sie die STRG\-TASTE gedrückt halten, während Sie auf die einzelnen Elemente klicken.  
  
 **Klasse**  
 Der Name der Consumerklasse, der standardmäßig auf dem Namen der ausgewählten Datei\- oder Computerdatenquelle basiert.  
  
 **.h\-Datei**  
 Der Name der Headerdatei der Consumerklasse, der standardmäßig auf dem Namen der ausgewählten Datei\- oder Computerdatenquelle basiert.  
  
 **.cpp\-Datei**  
 Der Name der Implementierungsdatei der Consumerklasse, der standardmäßig auf dem Namen der ausgewählten Datei\- oder Computerdatenquelle basiert.  
  
 **Typ**  
 Gibt an, ob das Recordset ein Dynaset \(Standard\) oder eine Momentaufnahme ist.  
  
-   **Dynaset**: Gibt an, dass das Recordset ein Dynaset ist.  Ein Dynaset ist das Ergebnis einer Abfrage, bei der die abgefragten Datenbankinformationen mithilfe einer indizierten Sicht dargestellt werden.  Durch ein Dynaset wird lediglich ein integraler Index der ursprünglichen Daten zwischengespeichert, wodurch Leistungsvorteile gegenüber einer Momentaufnahme erzielt werden.  Der Index zeigt direkt auf jeden einzelnen, im Ergebnis zurückgegebenen Datensatz und gibt an, ob ein Datensatz entfernt wurde.  Sie haben außerdem Zugriff auf aktualisierte Informationen in den abgefragten Datensätzen.  Dies ist der Standardwert.  
  
-   **Momentaufnahme**: Gibt an, dass das Recordset eine Momentaufnahme ist.  Eine Momentaufnahme ist das Ergebnis einer Abfrage und stellt ein Abbild einer Datenbank zu einem bestimmten Zeitpunkt dar.  Alle durch die Abfrage gefundenen Datensätze werden zwischengespeichert, sodass Sie keine Änderungen gegenüber den ursprünglichen Datensätzen feststellen können.  
  
 **Alle Spalten binden**  
 Legt fest, ob alle Spalten in der ausgewählten Tabelle gebunden werden.  Wenn Sie dieses Kontrollkästchen aktivieren \(Standard\), werden alle Spalten gebunden. Andernfalls werden keine Spalten gebunden, und Sie müssen sie manuell in der Recordsetklasse binden.  
  
## Siehe auch  
 [Nutzen von MFC\-ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)