---
title: Datenbankunterstützung, MFC-Anwendungs-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.database
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
ms.openlocfilehash: 94ed75ffd59294d5beb076ef4d66e57ef763f10e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525453"
---
# <a name="database-support-mfc-application-wizard"></a>Datenbankunterstützung, MFC-Anwendungs-Assistent

Diese Seite enthält Optionen, die Ihnen die Angabe die Ebene der Datenbank zu ermöglichen (plus einer Datenquelle, falls erforderlich) für das Projekt unterstützt.

- **Datenbankunterstützung**

   Legt die Ebene der datenbankunterstützung für das Projekt fest.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Keine**|Bietet keine datenbankunterstützung. Dies ist die Standardoption.|
   |**Nur Headerdateien**|Stellt die Basisebene der datenbankunterstützung für Ihre Anwendung bereit. Bei Auswahl von ODBC-Unterstützung unter **Clienttyp**, MFS-Anwendungsassistenten, der in Ihrem Projekt die Headerdatei AFXDB enthält. H. Linkbibliotheken hinzugefügt, aber alle datenbankspezifische Klassen wird nicht erstellt. Sie können die Recordsets später erstellen und verwenden diese zum Überprüfen und Aktualisieren von Datensätzen. Bei Auswahl von OLE DB-Unterstützung unter **Clienttyp**, die folgenden Headerdateien enthalten sind: ATLBASE.H AFXOLEDB.H ATLPLUS.H|
   |**Datenbankansicht ohne dateiunterstützung**|Enthält Datenbank-Header-Dateien, DLLs, einer Datensatzansicht und einem Recordset. (Nur für Anwendungen mit der **Unterstützung für die Dokument-/Ansicht** gewählten Option in der [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite.) Bei dieser Option sind dokumentunterstützung jedoch keine Serialisierungsunterstützung. Wenn Sie eine Datenbankansicht einschließen möchten, müssen Sie die Quelle der Daten angeben.|
   |**Datenbankansicht mit dateiunterstützung**|Enthält Datenbank-Header-Dateien, DLLs, einer Datensatzansicht und einem Recordset. (Nur für Anwendungen mit der **Unterstützung für die Dokument-/Ansicht** gewählten Option in der **Anwendungstyp** Seite.) Diese Option unterstützt Dokumentserialisierung, die Sie zum Beispiel, verwenden können eine Profildatei aktualisieren. Datenbankanwendungen arbeiten in der Regel individuell für einzelne Datensätze, statt auf einer pro-Datei-Basis und daher keine Serialisierung erforderlich ist. Allerdings müssen Sie eine besondere Verwendung für die Serialisierung. Wenn Sie eine Datenbankansicht einschließen möchten, müssen Sie die Quelle der Daten angeben.|

   > [!NOTE]
   > Unter **-Datenbanken unterstützen**, wenn Sie eine auswählen **-Datenbanksicht ohne dateiunterstützung** oder **-Datenbanksicht mit dateiunterstützung**, die Ansicht klassenableitung im Detail variiert, je nachdem, auf Ihre **Clienttyp** Auswahl wie folgt:

   - Bei Auswahl von **ODBC** unter **Clienttyp**, und klicken Sie dann die Ansichtsklasse der Anwendung abgeleitet [CRecordView](../../mfc/reference/crecordview-class.md). Diese Klasse zugeordnet ist eine [CRecordset](../../mfc/reference/crecordset-class.md)-abgeleitete Klasse, die die MFC-Anwendungs-Assistent auch für Sie erstellt. Diese Option erhalten Sie eine formularbasierte Anwendung, in der die Datensatzansicht zum Anzeigen und Aktualisieren von Datensätzen durch die Recordset verwendet wird.

   - Bei Auswahl von **OLE DB** unter **Clienttyp**, und klicken Sie dann die View-Klasse abgeleitet [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), und es zugeordnet ist eine [CTable](../../data/oledb/ctable-class.md) oder [CCommand](../../data/oledb/ccommand-class.md)-abgeleitete Klasse.

- **Clienttyp**

   Gibt an, ob das Projekt OLEDB- oder ODBC-Klassen verwendet.

   |Option|Beschreibung|
   |------------|-----------------|
   |**OLE DB**|Wenn diese Option ausgewählt ist, durch Klicken auf die **Datenquelle** Schaltfläche rufen Sie die **Datenlinkeigenschaften** Assistenten können Sie eine Verbindung mit einer OLE DB-Datenquelle erstellen.|
   |**ODBC**|Wenn diese Option ausgewählt ist, durch Klicken auf die **Datenquelle** Schaltfläche rufen Sie die **Auswählen einer Datenquelle** Assistenten können Sie eine Verbindung mit einer ODBC-Datenquelle herzustellen.|

- **Datenquelle**

   > [!NOTE]
   > Die ATL-OLE DB-Consumer-Assistenten und der MFC-ODBC-Consumer-Assistenten sind nicht in Visual Studio-2019 und höher verfügbar. Sie können die Funktionalität trotzdem manuell hinzufügen. Weitere Informationen finden Sie unter [Erstellen eines Consumers ohne mithilfe eines Assistenten](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

   Klicken Sie auf die **Datenquelle** Schaltfläche, um eine Datenquelle mithilfe der angegebenen Treiber oder Anbieter und der Datenbank einzurichten. Bei Auswahl von OLE DB in der **Clienttyp** auswählen, zeigt diese Schaltfläche den **Datenlinkeigenschaften** Dialogfeld. Bei Auswahl von ODBC in die **Clienttyp** option, diese Schaltfläche bietet die **Auswählen einer Datenquelle** Dialogfeld. Diese Option ist nur verfügbar, wenn Sie eine Ansicht in Ihre Anwendung einbinden möchten.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Datenverknüpfungseigenschaften** (OLE DB)|Legt die angegebene Datenquelle, die mit dem angegebenen OLE DB-Anbieter. Sie müssen die OLE DB-Anbieter, den Speicherort der Daten, die die Datenquelle, Anmelde-ID und (optional) ein Kennwort angeben. Weitere Informationen in diesem Dialogfeld finden Sie unter **Datenquelle** in [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).|
   |**Wählen Sie die Datenquelle** (ODBC)|Legt die angegebene Datenquelle, die mit dem angegebenen ODBC-Treiber. Sie müssen einen Datenquellennamen ein, wählen Sie eine Tabelle für die Datenquelle auswählen. Der Assistent alle Spalten der Tabelle an der Membervariablen des bindet ein `CRecordset`-abgeleitete Klasse. Weitere Informationen in diesem Dialogfeld finden Sie unter **Datenquelle** in [MFC-ODBC-Consumer-Assistenten](../../mfc/reference/mfc-odbc-consumer-wizard.md).|

- **Attributierte Datenbankklasse generieren**

   Für OLE DB-Client ist nur verfügbar. Gibt an, ob die Datenbankklassen in das generierte Projekt Attribute verwenden.

- **Binden Sie alle Spalten**

   ODBC-nur für Clients verfügbar. Gibt an, ob alle Spalten in der ausgewählten Tabelle gebunden sind. Wenn Sie dieses Feld auswählen, werden alle Spalten gebunden. Wenn Sie dieses Kontrollkästchen nicht auswählen, werden keine Spalten gebunden, und Sie müssen diese manuell in die Recordset-Klasse binden.

- **Type**

   ODBC-nur für Clients verfügbar. Gibt an, ob das Recordset ein Dynaset oder eine Momentaufnahme ist in der folgenden Tabelle beschrieben.

   |Option|Beschreibung|
   |------------|-----------------|
   |**Dynaset**|Gibt an, dass das Recordset ein Dynaset ist. Ein Dynaset ist das Ergebnis einer Abfrage, die eine indizierte Sicht in der abgefragten Datenbank Daten bereitstellt. Ein Dynaset speichert nur ganzzahligen Index für die ursprünglichen Daten, und daher Leistungsvorteile erhalten, über eine Momentaufnahme aus. Die Index-verweist direkt auf jeden Datensatz gefunden, die als Ergebnis einer Abfrage und gibt an, ob ein Eintrag entfernt wird. Sie haben auch Zugriff auf aktualisierte Informationen in den abgefragten Einträgen an.|
   |**Snapshot**|Gibt an, dass das Recordset eine Momentaufnahme ist. Eine Momentaufnahme ist das Ergebnis einer Abfrage und einen Einblick in einer Datenbank an einem bestimmten Punkt ist, in Zeit. Alle Datensätze gefunden wurden, als Ergebnis der Abfrage werden zwischengespeichert, sodass keine Änderungen an den ursprünglichen Datensätzen angezeigt wird.|

## <a name="see-also"></a>Siehe auch

[MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)
