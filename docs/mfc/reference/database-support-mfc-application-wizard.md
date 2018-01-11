---
title: "Datenbankunterstützung, MFC-Anwendung-Assistenten | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.appwiz.mfc.exe.database
dev_langs: C++
helpviewer_keywords: MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7b7c9aaa6389f5e86a51348a8b5423260c4c76e3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="database-support-mfc-application-wizard"></a>Datenbankunterstützung, MFC-Anwendungs-Assistent
Diese Seite enthält Optionen, mit denen Sie die Ebene der Datenbank angeben können (plus einer Datenquelle, falls erforderlich) für das Projekt zu unterstützen.  
  
 **Datenbankunterstützung**  
 Legt die Ebene der datenbankunterstützung für das Projekt fest.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Keine**|Bietet keine datenbankunterstützung. Dies ist die Standardoption.|  
|**Nur die Header-Dateien**|Bietet die grundlegenden datenbankunterstützung für Ihre Anwendung. Bei Auswahl von ODBC-Unterstützung unter **Clienttyp**, der MFC-Anwendung-Assistent umfasst in Ihrem Projekt die Headerdatei AFXDB. H. Linkbibliotheken hinzugefügt, jedoch werden keine datenbankspezifische Klassen erstellt. Sie können später Recordsets erstellen und verwenden diese zum Überprüfen und Aktualisieren von Datensätzen. Bei Auswahl von OLE DB-Unterstützung unter **Clienttyp**, die folgenden Headerdateien sind enthalten: ATLBASE. H AFXOLEDB. H-DATEI ATLPLUS. H|  
|**Datenbanksicht ohne dateiunterstützung**|Enthält Datenbank-Headerdateien, Linkbibliotheken, einer Datensatzansicht und ein Recordset. (Nur für Anwendungen mit der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** die Option der [Anwendungstyp](../../mfc/reference/application-type-mfc-application-wizard.md) Seite.) Diese Option umfasst, unterstützt jedoch keine Serialisierungsunterstützung. Falls gewünscht, eine Datenbanksicht einschließen, müssen Sie die Quelle der Daten angeben.|  
|**Datenbanksicht mit dateiunterstützung**|Enthält Datenbank-Headerdateien, Linkbibliotheken, einer Datensatzansicht und ein Recordset. (Nur für Anwendungen mit der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** die Option der **Anwendungstyp** Seite.) Diese Option unterstützt die Dokumentserialisierung, die Sie zum Beispiel verwenden können, zum Aktualisieren von einer Benutzerdatei-Profil. Datenbankanwendungen arbeiten in der Regel für pro-Datensätze, statt auf eine Headerdatei Basis und daher keine Serialisierung benötigen. Allerdings müssen möglicherweise eine besondere Verwendung für die Serialisierung. Falls gewünscht, eine Datenbanksicht einschließen, müssen Sie die Quelle der Daten angeben.|  
  
> [!NOTE]
>  Unter **-Datenbanken unterstützen**, wenn Sie eine auswählen **-Datenbanksicht ohne Unterstützung der** oder **-Datenbanksicht mit Unterstützung der**, die klassenableitung Ansicht im Detail variiert, je nachdem, auf Ihrem **Clienttyp** Auswahl wie folgt:  
  
-   Bei Auswahl des **ODBC** unter **Clienttyp**, und klicken Sie dann die Anwendung View-Klasse abgeleitet [CRecordView](../../mfc/reference/crecordview-class.md). Diese Klasse zugeordnet ist ein [CRecordset](../../mfc/reference/crecordset-class.md)-abgeleitete Klasse, die die MFC-Anwendungs-Assistent auch für Sie erstellt. Diese Option bietet Ihnen eine formularbasierte Anwendung, die in der die Datensatzansicht zum Anzeigen und Aktualisieren von Datensätzen durch seine Recordset verwendet wird.  
  
-   Bei Auswahl des **OLE DB-** unter **Clienttyp**, und klicken Sie dann die View-Klasse abgeleitet [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), und er zugeordnet ist ein [CTable](../../data/oledb/ctable-class.md) oder [CCommand](../../data/oledb/ccommand-class.md)-Klasse.  
  
 **Clienttyp**  
 Gibt an, ob das Projekt OLE DB- oder ODBC-Klassen verwendet.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**OLE-DB**|Wenn diese Option aktiviert ist, klicken Sie auf die **Datenquelle** Schaltfläche aufruft der **Datenlinkeigenschaften** Assistenten helfen Ihnen beim Erstellen einer Verbindungs mit einer OLE DB-Datenquelle.|  
|**ODBC**|Wenn diese Option aktiviert ist, klicken Sie auf der **Datenquelle** Schaltfläche ruft der **Auswählen einer Datenquelle** Assistenten helfen Ihnen beim Erstellen einer Verbindungs mit einer ODBC-Datenquelle.|  
  
 **Datenquelle**  
 Klicken Sie auf die **Datenquelle** Schaltfläche, um eine Datenquelle mithilfe der angegebenen Treiber oder der Anbieter und der Datenbank einzurichten. Bei Auswahl von OLE DB in der **Clienttyp** Option, diese Schaltfläche zeigt den **Datenlinkeigenschaften** (Dialogfeld). Bei Auswahl von ODBC in die **Clienttyp** option, diese Schaltfläche bietet die **Auswählen einer Datenquelle** (Dialogfeld). Diese Option ist nur verfügbar, wenn Sie die Möglichkeit, eine Datenbanksicht in Ihrer Anwendung einzuschließen.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Daten "Datenverknüpfungseigenschaften"** (OLE DB)|Stellt die angegebene Datenquelle mithilfe des angegebenen OLE DB-Anbieters her. Sie müssen den OLE DB-Anbieter, den Speicherort der Daten, die Datenquelle, Anmelde-ID und (optional) ein Kennwort angeben. Weitere Informationen zu diesem Dialogfeld finden Sie unter **Datenquelle** in [ATL-OLE DB-Consumer-Assistenten](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Auswählen einer Datenquelle** (ODBC)|Legt die angegebene Datenquelle mit dem angegebenen ODBC-Treiber. Sie müssen einen Datenquellennamen ein, wählen eine Tabelle für die Datenquelle auswählen. Der Assistent bindet alle Spalten der Tabelle an die Membervariablen des eine `CRecordset`-Klasse. Weitere Informationen zu diesem Dialogfeld finden Sie unter **Datenquelle** in [MFC-ODBC-Consumer-Assistent](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  In früheren Versionen, die UMSCHALT-Taste die **Datenquelle** Schaltfläche Öffnen ein Dialogfeld, öffnen Sie eine Datei Data Link (UDL) auswählen können. Diese Funktionalität wird nicht mehr unterstützt.  
  
 **Attributierte Datenbankklasse generieren**  
 OLE DB-nur für Clients verfügbar. Gibt an, ob die Datenbankklassen im generierten Projekt Attribute verwendet werden.  
  
 **Alle Spalten binden**  
 ODBC-nur für Clients verfügbar. Gibt an, ob alle Spalten in der ausgewählten Tabelle gebunden sind. Wenn Sie dieses Kontrollkästchen aktivieren, werden alle Spalten gebunden. Wenn Sie dieses Kontrollkästchen nicht aktivieren, werden keine Spalten gebunden, und Sie müssen diese manuell in die Recordset-Klasse binden.  
  
 **Type**  
 ODBC-nur für Clients verfügbar. Gibt an, ob das Recordset ein Dynaset oder eine Momentaufnahme ist, wie in der folgenden Tabelle beschrieben.  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**Dynaset**|Gibt an, dass das Recordset ein Dynaset ist. Ein Dynaset ist das Ergebnis einer Abfrage, die eine indizierte Sicht in der abgefragten Datenbank Daten bereitstellt. Ein Dynaset wird lediglich einen integralen Index auf die ursprünglichen Daten zwischengespeichert, und daher Leistungsvorteile gegenüber einer Momentaufnahme erhalten. Der Index-verweist direkt auf jeden Datensatz gefunden, die als Ergebnis einer Abfrage und gibt an, ob ein Eintrag entfernt wird. Sie haben auch Zugriff auf aktualisierte Informationen in den abgefragten Datensätzen.|  
|Momentaufnahme|Gibt an, dass das Recordset eine Momentaufnahme ist. Eine Momentaufnahme ist das Ergebnis einer Abfrage und einen Einblick in einer Datenbank an einem Punkt zeitlich ist. Alle Datensätze, die als Ergebnis der Abfrage gefunden werden zwischengespeichert, sodass keine Änderungen an den ursprünglichen Datensätzen angezeigt.|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Anwendungs-Assistent](../../mfc/reference/mfc-application-wizard.md)
