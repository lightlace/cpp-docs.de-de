---
title: MFC-ODBC-Consumer-Assistent
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.class.mfc.consumer.overview
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: b6009a1e6b6100eabaa2ed05404217c0d2906be0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310310"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC-ODBC-Consumer-Assistent

> [!WARNING]
> Ab Version 15.9 von Visual Studio 2017 ist dieser Codeassistent veraltet. Er wird in einer zukünftigen Version von Visual Studio entfernt. Dieser Assistent wird nur selten verwendet. Die Entfernung dieses Assistenten wirkt sich nicht auf die allgemeine Unterstützung für Active Template Library (ATL) und Microsoft Foundation Classes (MFC) aus. In [dieser Umfrage](https://www.surveymonkey.com/r/QDWKKCN) können Sie Ihr Feedback zu dieser Veraltung mitteilen. Ihr Feedback ist uns wichtig.

Dieser Assistent richtet eine ODBC-Recordset-Klasse und datenbindungen, die zum Zugriff auf die angegebene Datenquelle.

## <a name="uielement-list"></a>UIElement-Liste

- **Datenquelle**

  Die **Datenquelle** Schaltfläche können Sie festlegen, um die angegebene Datenquelle, die mit dem angegebenen ODBC-Treiber. Weitere Informationen zu Datenquellendateien (DSN), finden Sie unter [Dateidatenquellen](/sql/odbc/reference/file-data-sources) im ODBC-SDK.

  Die **Auswählen einer Datenquelle** Dialogfeld verfügt über zwei Registerkarten:

  - **Datei-Datenquelle** Registerkarte:

     Die **Suchen in** Feld gibt das Verzeichnis, wählen Sie die Dateien als Datenquellen verwendet werden soll. Der Standardwert ist \Programme\Gemeinsame Dateien\ODBC\Data Sources. Die vorhandene Datei-Datenquellen (DSN-Dateien) werden in der wichtigsten Listenfelder angezeigt. Können Sie entweder die Datenquellen vor der Nutzung der **Datei-DSN** Registerkarte die [ODBC-Datenquellenadministrator](/sql/odbc/admin/odbc-data-source-administrator), oder erstellen Sie mithilfe dieses Dialogfelds neue.

     In diesem Dialogfeld eine neue Datenquelle erstellen, klicken Sie auf `New` an einen DSN-Namen, den **neue Datenquelle erstellen** Dialogfeld wird angezeigt. In der **neue Datenquelle erstellen** Dialogfeld Feld, wählen Sie einen geeigneten Treiber aus, und klicken Sie auf `Next`; klicken Sie auf **Durchsuchen**, und wählen Sie den Namen der Datei, die als Datenquelle verwendet werden (Sie haben "Alle Dateien" auswählen keine DSN-Dateien anzeigen, wie z. B. xls-Dateien); Klicken Sie auf `Next`, und klicken Sie dann auf **Fertig stellen**. (Wenn Sie eine nicht-DSN-Datei ausgewählt haben, erhalten Sie ein Dialogfeld treiberspezifische, z. B. "ODBC Microsoft Excel Setup" die Datei in einem DSN konvertiert.)

     > [!NOTE]
     > Sie können auch eine neue Datei-Datenquelle, die zuvor mit der ODBC-Datenquellen-Administrator erstellen. Von der **starten** , wählen Sie im Menü **Einstellungen**, **Systemsteuerung**, **Verwaltung**, **Datenquellen (ODBC)**, und klicken Sie dann **ODBC-Datenquellenadministrator**.

     Die **DSN-Namen** im können Sie einen Namen für die Datei als Datenquelle angeben. Sie müssen sicherstellen, dass die entsprechende Dateierweiterung, z. B. xls für Excel-Dateien oder MDB für den Zugriff auf Dateien der DSN-Namen endet.

     Weitere Informationen zu DSNs, finden Sie unter [Dateidatenquellen](/sql/odbc/reference/file-data-sources) im ODBC-SDK.

  - **Computer-Datenquelle** Registerkarte:

     Auf dieser Registerkarte werden die System- und Benutzer-Datenquellen aufgelistet. Benutzerdatenquellen sind spezifisch für einen Benutzer auf diesem Computer. System-Datenquellen können von allen Benutzern, die auf diesem Computer oder in einem systemweiten-Dienst verwendet werden. Finden Sie unter [Computerdatenquellen](/sql/odbc/reference/machine-data-sources) in ODBC-SDK

     Weitere Informationen zu ODBC-Datenquellen, finden Sie unter [Datenquellen](/sql/odbc/reference/data-sources) im ODBC-SDK.

  Klicken Sie auf **OK** um den Vorgang abzuschließen. Die **Datenbankobjekt auswählen** Dialogfeld wird angezeigt. Wählen Sie in diesem Dialogfeld die Tabelle, oder zeigen Sie an, die vom Consumer verwendet wird. Beachten Sie, dass Sie mehrere Ansichten und Tabellen auswählen können, durch die Control-Taste gedrückt halten, während Sie auf die Elemente auf. Klicken Sie auf **OK** um den Vorgang abzuschließen.

- **Klasse**

      The name of the consumer class, based by default on the name of the file or machine data source that you selected.

- **H-Datei**

   Der Name der Headerdatei der Consumer, der standardmäßig anhand des Namens der Datei oder der Computer-Datenquelle, die Sie ausgewählt.

- **CPP-Datei**

   Der Name der Implementierungsdatei die Consumer, der standardmäßig anhand des Namens der Datei oder der Computer-Datenquelle, die Sie ausgewählt.

- **Type**

   Gibt an, ob das Recordset ein Dynaset (Standard) oder eine Momentaufnahme ist.

   - **Dynaset**: Gibt an, dass das Recordset ein Dynaset ist. Ein Dynaset ist das Ergebnis einer Abfrage, die eine indizierte Sicht in der abgefragten Datenbank Daten bereitstellt. Ein Dynaset speichert nur ganzzahligen Index für die ursprünglichen Daten, und daher Leistungsvorteile erhalten, über eine Momentaufnahme aus. Die Index-verweist direkt auf jeden Datensatz gefunden, die als Ergebnis einer Abfrage und gibt an, ob ein Eintrag entfernt wird. Sie haben auch Zugriff auf aktualisierte Informationen in den abgefragten Einträgen an. Dies ist die Standardeinstellung.

   - **Snapshot**: Gibt an, dass das Recordset eine Momentaufnahme ist. Eine Momentaufnahme ist das Ergebnis einer Abfrage und einen Einblick in einer Datenbank an einem bestimmten Punkt ist, in Zeit. Alle Datensätze gefunden wurden, als Ergebnis der Abfrage werden zwischengespeichert, sodass keine Änderungen an den ursprünglichen Datensätzen angezeigt wird.

- **Binden Sie alle Spalten**

   Gibt an, ob alle Spalten in der ausgewählten Tabelle gebunden sind. Wenn Sie dieses Kontrollkästchen (Standard) auswählen, werden alle Spalten gebunden. Wenn Sie dieses Kontrollkästchen nicht auswählen, werden keine Spalten gebunden, und Sie müssen diese manuell in die Recordset-Klasse binden.

## <a name="see-also"></a>Siehe auch

[MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Adding Functionality with Code Wizards (Hinzufügen neuer Funktionen mit Code-Assistenten)](../../ide/adding-functionality-with-code-wizards-cpp.md)
