---
title: MFC-ODBC-Consumer-Assistenten | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.mfc.consumer.overview
dev_langs: C++
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad9e4aeb15d2af04987883b6554d569e3cc16b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC-ODBC-Consumer-Assistent
"Suchergebnisse" Zusammenfassung hier einfügen.  
  
 Dieser Assistent richtet eine ODBC-Recordset-Klasse und datenbindungen, die zum Zugriff auf die angegebene Datenquelle.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Datenquelle**  
 Die **Datenquelle** Schaltfläche können Sie die angegebene Datenquelle mit dem angegebenen ODBC-Treiber einrichten. Weitere Informationen zu Datenquellendateien (DSN), finden Sie unter [Dateidatenquellen](https://msdn.microsoft.com/library/ms715401.aspx) im ODBC-SDK. Die **Auswählen einer Datenquelle** Dialogfeld verfügt über zwei Registerkarten:  
  
-   **Dateidatenquelle** Registerkarte: die **Suchen in** Feld gibt das Verzeichnis, in dem Auswählen von Dateien, die als Datenquellen verwendet werden. Der Standardwert ist \Programme\Gemeinsame Dateien\ODBC\Data Sources. Die vorhandenen Dateidatenquellen (DSN-Dateien) werden im Hauptfenster Listenfeld angezeigt. Sie können entweder Einrichten der Datenquellen mit der **Datei-DSN** Registerkarte die [ODBC-Datenquellen-Administrator](https://msdn.microsoft.com/library/ms714024.aspx), oder neue erstellen mithilfe dieses Dialogfelds.  
  
     In diesem Dialogfeld eine neue Datenquelle erstellen, klicken Sie auf `New` zum Angeben eines Namens DSN; die **neue Datenquelle erstellen** Dialogfeld wird angezeigt. In der **neue Datenquelle erstellen** Dialogfeld Feld, wählen Sie einen geeigneten Treiber aus, und klicken Sie auf `Next`; klicken Sie auf **Durchsuchen**, und wählen Sie den Namen der Datei, die als Datenquelle verwendet werden (Sie haben "Alle Dateien" auswählen keine DSN-Dateien anzeigen, z. B. xls-Dateien); Klicken Sie auf `Next`, und klicken Sie dann auf **Fertig stellen**. (Wenn Sie eine nicht-DSN-Datei ausgewählt haben, erhalten Sie ein Dialogfeld treiberspezifische, z. B. "ODBC Microsoft Excel Setup" die Datei in einem DSN konvertiert wird.)  
  
    > [!NOTE]
    >  Sie können auch eine neue Datei-Datenquelle, die vorher mit dem ODBC-Datenquellen-Administrator erstellen. Aus der **starten** klicken Sie im Menü **Einstellungen**, **Systemsteuerung**, **Verwaltung**, **Datenquellen (ODBC)**, und klicken Sie dann **ODBC-Datenquellenadministrator**.  
  
     Die **DSN-Name** das können Sie einen Namen für die Datei als Datenquelle angeben. Sie müssen sicherstellen, dass der DSN-Name mit der entsprechenden Dateierweiterung, z. B. xls für Excel-Dateien oder MDB für den Zugriff auf Dateien endet.  
  
     Weitere Informationen zu DSNs, finden Sie unter [Dateidatenquellen](https://msdn.microsoft.com/library/ms715401.aspx) im ODBC-SDK.  
  
-   **Computer-Datenquelle** Registerkarte: auf dieser Registerkarte sind System- und Benutzerdatenquellen aufgelistet. Benutzerdatenquellen sind spezifisch für einen Benutzer auf diesem Computer. System-Datenquellen können von allen Benutzern, die auf diesem Computer oder auf einer systemweiten-Dienst verwendet werden. Finden Sie unter [Computer Datenquellen](https://msdn.microsoft.com/library/ms710952.aspx) in ODBC-SDK  
  
 Weitere Informationen über ODBC-Datenquellen finden Sie unter [Datenquellen](https://msdn.microsoft.com/library/ms711688.aspx) im ODBC-SDK.  
  
 Klicken Sie auf **OK** um den Vorgang abzuschließen. Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt. Wählen Sie in diesem Dialogfeld die Tabelle oder Sicht, die vom Consumer verwendet wird. Beachten Sie, dass Sie mehrere Sichten und Tabellen auswählen können, indem Sie die Steuerelement-Taste gedrückt halten, während Sie auf die Elemente auf.  
  
 **Klasse**  
 Der Name der Consumerklasse, die standardmäßig anhand des Namens der Datei oder der Computer-Datenquelle, die Sie ausgewählt haben.  
  
 **.h-Datei**  
 Der Name der Headerdatei der Consumer, der standardmäßig anhand des Namens der Datei oder der Computer-Datenquelle, die Sie ausgewählt haben.  
  
 **CPP-Datei**  
 Der Name der Implementierungsdatei der Consumer, der standardmäßig anhand des Namens der Datei oder der Computer-Datenquelle, die Sie ausgewählt haben.  
  
 **Type**  
 Gibt an, ob das Recordset ein Dynaset (Standard) oder eine Momentaufnahme ist.  
  
-   **Dynaset**: Gibt an, dass das Recordset ein Dynaset ist. Ein Dynaset ist das Ergebnis einer Abfrage, die eine indizierte Sicht in der abgefragten Datenbank Daten bereitstellt. Ein Dynaset wird lediglich einen integralen Index auf die ursprünglichen Daten zwischengespeichert, und daher Leistungsvorteile gegenüber einer Momentaufnahme erhalten. Der Index-verweist direkt auf jeden Datensatz gefunden, die als Ergebnis einer Abfrage und gibt an, ob ein Eintrag entfernt wird. Sie haben auch Zugriff auf aktualisierte Informationen in den abgefragten Datensätzen. Dies ist die Standardeinstellung.  
  
-   **Momentaufnahme**: Gibt an, dass das Recordset eine Momentaufnahme ist. Eine Momentaufnahme ist das Ergebnis einer Abfrage und einen Einblick in einer Datenbank an einem Punkt zeitlich ist. Alle Datensätze, die als Ergebnis der Abfrage gefunden werden zwischengespeichert, sodass keine Änderungen an den ursprünglichen Datensätzen angezeigt.  
  
 **Alle Spalten binden**  
 Gibt an, ob alle Spalten in der ausgewählten Tabelle gebunden sind. Wenn Sie dieses Kontrollkästchen (Standard) auswählen, werden alle Spalten gebunden. Wenn Sie dieses Kontrollkästchen nicht aktivieren, werden keine Spalten gebunden, und Sie müssen diese manuell in die Recordset-Klasse binden.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)

