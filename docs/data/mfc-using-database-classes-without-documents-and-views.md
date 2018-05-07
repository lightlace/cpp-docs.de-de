---
title: 'MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC applications [C++], without views
- documents [C++], applications without
- ODBC applications [C++]
- document/view architecture [C++], in databases
- files [C++], MFC
- database classes [C++], MFC
- CRecordView class, using in database applications
- database applications [C++], without views
- database applications [C++], application wizard options
- application wizards [C++], creating database applications
- ODBC [C++], file support in database applications
- ODBC applications [C++], without documents
- database applications [C++], without documents
- user interface [C++], drawing information
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ba2e59b53524975f87e4ad7ffe99b9a4a3cc870d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten
In einigen Fällen können Sie nicht das Framework Dokument-/Ansichtarchitektur in datenbankanwendungen verwenden möchten. In diesem Thema wird Folgendes erläutert:  
  
-   [Wenn Sie müssen nicht auf die Verwendung von Dokumenten](#_core_when_you_don.92.t_need_documents) z. B. Dokumentserialisierung.  
  
-   [Assistenten Anwendungsoptionen](#_core_appwizard_options_for_documents_and_views) zur Unterstützung von Anwendungen, Serialisierung und ohne zu Dokument-bezogene **Datei** Menübefehle wie z. B. **neu**, **öffnen** , **Speichern**, und **speichern als**.  
  
-   [Gewusst wie: Arbeiten mit einer Anwendung, die eine minimale Dokument verwendet](#_core_applications_with_minimal_documents).  
  
-   [Eine Anwendung ohne Dokument oder eine Ansicht strukturieren](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a> Wenn benötigen Sie keine Dokumente  
 Einige Anwendungen verfügen über ein distinct Konzept eines Dokuments. Diese Anwendungen in der Regel alle oder Großteil einer Datei aus dem Speicher in den Speicher geladen mit einem **Datei öffnen** Befehl. Die aktualisierte Datei wieder auf den Datenträger geschrieben alle auf einmal mit einem **speichern** oder **speichern unter** Befehl. Was dem Benutzer angezeigt wird, ist eine Datendatei.  
  
 Einige Anwendungskategorien erfordern ein Dokument jedoch nicht. Datenbankanwendungen, die im Hinblick auf Transaktionen ausgeführt werden. Die Anwendung wählt Datensätze aus einer Datenbank und stellt sie dem Benutzer, häufig einzeln nacheinander. Erkennt, was der Benutzer ist in der Regel einen einzelnen aktuellen Datensatz, der möglicherweise die einzige im Arbeitsspeicher.  
  
 Wenn Ihre Anwendung kein Dokument zum Speichern von Daten erfordert, können Sie einige oder alle der Dokument-/Ansichtarchitektur für das Framework verzichten. Wie viel Sie verzichten, hängt von der von Ihnen bevorzugten Ansatz ab. Sie können:  
  
-   Verwenden Sie eine minimale Dokument als Ort, um eine Verbindung mit Ihrer Datenquelle zu speichern, aber mit normalen Dokumentfunktionen, z. B. Serialisierung verzichten. Dies ist hilfreich, wenn Sie mehrere Sichten der Daten und alle Ansichten synchronisieren sie alle auf einmal und so weiter zu aktualisieren möchten.  
  
-   Verwenden eines Rahmenfensters, in dem Sie direkt zeichnen anstatt mit einer Ansicht an. In diesem Fall lassen Sie das Dokument und Speichern von Daten oder datenverbindungen in dem Rahmenfenster Objekt.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a> Assistenten Anwendungsoptionen für Dokumente und Ansichten  
 Die MFC-Anwendung-Assistent bietet mehrere Optionen im **wählen datenbankunterstützung**, die in der folgenden Tabelle aufgeführt sind. Wenn Sie die MFC-Anwendung-Assistent zum Erstellen einer Anwendung verwenden, erzeugen alle diese Optionen Anwendungen mit Dokumenten und Ansichten. Einige Optionen bieten die Dokumenten und Ansichten, die nicht benötigte Dokument Funktionalität weglassen. Weitere Informationen finden Sie unter [Datenbankunterstützung, MFC-Anwendungs-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Option|Ansicht|Dokument|  
|------------|----------|--------------|  
|**Keine**|Abgeleitet von `CView`.|Bietet keine datenbankunterstützung. Dies ist die Standardoption.<br /><br /> Bei Auswahl der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** option die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite erhalten Sie Unterstützung von vollständigen Dokuments einschließlich der Serialisierung und `New`,  **Open**, **speichern**, und **speichern unter** Befehle die **Datei** Menü. Finden Sie unter [Anwendungen kein Dokument](#_core_applications_with_no_document).|  
|**Nur die Header-Dateien**|Abgeleitet von `CView`.|Bietet die grundlegenden datenbankunterstützung für Ihre Anwendung.<br /><br /> Enthält Afxdb.h. Link Librarys hinzugefügt, aber keine datenbankspezifische Klassen erstellt. Sie können später Recordsets erstellen und verwenden diese zum Überprüfen und Aktualisieren von Datensätzen.|  
|**Datenbanksicht ohne dateiunterstützung**|Abgeleitet wurde. `CRecordView`|Bietet Unterstützung für aber keine Serialisierungsunterstützung. Dokument Recordset speichern und mehrere Ansichten koordinieren; unterstützt keine Serialisierung oder der `New`, **öffnen**, **speichern**, und **speichern unter** Befehle. Finden Sie unter [Anwendungen mit minimalen Dokumenten](#_core_applications_with_minimal_documents). Wenn Sie eine Datenbanksicht einschließen, müssen Sie die Quelle der Daten angeben.<br /><br /> Schließt ein Datenbank-Headerdateien, Link Librarys einer Datensatzansicht und ein Recordset. (Nur für Anwendungen mit der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Option ausgewählt wird, auf die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite.)|  
|**Datenbanksicht mit dateiunterstützung**|Abgeleitet wurde. `CRecordView`|Bietet Unterstützung für vollständiges Dokument, einschließlich der Serialisierung und der dokumentbezogenen **Datei** Menübefehle. Datenbankanwendungen arbeiten in der Regel für pro-Datensätze, statt auf eine Headerdatei Basis und daher keine Serialisierung benötigen. Allerdings müssen Sie möglicherweise eine besondere Verwendung für die Serialisierung. Finden Sie unter [Anwendungen mit minimalen Dokumenten](#_core_applications_with_minimal_documents). Wenn Sie eine Datenbanksicht einschließen, müssen Sie die Quelle der Daten angeben.<br /><br /> Schließt ein Datenbank-Headerdateien, Link Librarys einer Datensatzansicht und ein Recordset. (Nur für Anwendungen mit der **Unterstützung der Dokument-/Ansichtarchitektur-Architektur** Option ausgewählt wird, auf die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite.)|  
  
 Eine Erläuterung der alternativen zur Serialisierung und alternative verwendet für die Serialisierung, finden Sie unter [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a> Anwendungen mit minimalen Dokumente  
 Die MFC-Anwendung-Assistent verfügt über zwei Optionen zur Verfügung, die Unterstützung von formularbasierten datenzugriffsanwendungen. Jede Option erstellt eine `CRecordView`-abgeleitete Ansichtsklasse und ein Dokument. Sie unterscheiden sich in was sie nicht in das Dokument aufgenommen.  
  
###  <a name="_core_a_document_without_file_support"></a> Dokument ohne Unterstützung der  
 Wählen Sie die Anwendung Assistenten-Datenbankoption **-Datenbanksicht ohne Unterstützung der** , wenn Sie nicht über die Dokumentserialisierung benötigen. Das Dokument erfüllt folgende Zwecke nützlich:  
  
-   Es ist eine bequeme Möglichkeit zum Speichern einer `CRecordset` Objekt.  
  
     Diese Art der Verwendung entspricht Standarddokument-Konzepte: das Dokument speichert die Daten (oder in diesem Fall kann eine Gruppe von Datensätzen) und die Ansicht ist eine Ansicht des Dokuments.  
  
-   Wenn Ihre Anwendung mehrere Ansichten (z. B. mehrere Datensatzansichten) darstellt, unterstützt ein Dokument mit der Koordination der Ansichten.  
  
     Wenn mehrere Ansichten die gleichen Daten anzuzeigen, können Sie mithilfe der `CDocument::UpdateAllViews` Memberfunktion zum Koordinieren der Updates auf alle Sichten bei Änderung von einer beliebigen Ansicht der Daten.  
  
 Sie verwenden diese Option in der Regel für einfache formularbasierten Anwendungen. Der Anwendungs-Assistent unterstützt eine einfache Struktur automatisch für solche Anwendungen an.  
  
###  <a name="_core_a_document_with_file_support"></a> Dokument mit Dateiunterstützung  
 Wählen Sie die Anwendung Assistenten-Datenbankoption **-Datenbanksicht mit dateiunterstützung** , wenn Sie haben eine alternative Verwendung für das Dokument bezogene **Datei** Menübefehle und Dokumentserialisierung. Für den Datenzugriff Teil des Programms, können Sie das Dokument auf die gleiche Weise wie in beschrieben [Dokument ohne Dateiunterstützung](#_core_a_document_without_file_support). Sie können das Dokument Serialisierung-Funktion, z. B. verwenden, zum Lesen und schreiben eine serialisierte Benutzer Profil-Dokument, das die Einstellungen des Benutzers oder andere nützliche Informationen speichert. Weitere Ideen, finden Sie unter [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Der Anwendungs-Assistent unterstützt diese Option, jedoch müssen Sie den Code, der das Dokument serialisiert schreiben. Speichern Sie die serialisierte Informationen im Dokument-Datenmember.  
  
##  <a name="_core_applications_with_no_document"></a> Anwendungen ohne Dokument  
 Möglicherweise möchten Sie eine Anwendung schreiben, die keine Dokumente oder Sichten verwendet wird. Ohne Dokumente speichern Sie Ihre Daten (z. B. eine `CRecordset` Objekt) in Ihrer Klasse Rahmenfenster oder Ihrer Anwendungsklasse. Ggf. zusätzlichen Anforderungen hängen davon ab, ob die Anwendung eine Benutzeroberfläche verfügt.  
  
###  <a name="_core_database_support_with_a_user_interface"></a> Unterstützung für Datenbanken mit einer Benutzeroberfläche  
 Wenn Sie eine Benutzeroberfläche (außer, z. B. eine Befehlszeilenschnittstelle) verfügen, zeichnet die Anwendung direkt in das Rahmenfenster Clientbereich statt in einer Ansicht. Eine solche Anwendung verwendet keine `CRecordView`, `CFormView`, oder `CDialog` für die primäre Benutzeroberfläche, aber normalerweise verwenden `CDialog` für gewöhnliche Dialoge.  
  
###  <a name="_core_writing_applications_without_documents"></a> Schreiben von Anwendungen ohne Dokumente  
 Da Sie der Assistenten zum erstellende von Anwendungen ohne Dokumente nicht unterstützt, Sie müssen einen eigenen Handler erstellen `CWinApp`-abgeleitete Klasse, und erstellen Sie bei Bedarf auch eine `CFrameWnd` oder `CMDIFrameWnd` Klasse. Überschreiben Sie `CWinApp::InitInstance` und ein Anwendungsobjekt als deklarieren:  
  
```  
CYourNameApp theApp;  
```  
  
 Das Framework verwendet weiterhin den meldungszuordnungsmechanismus und viele weitere Funktionen.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a> Datenbank-Unterstützung getrennt von der Benutzeroberfläche  
 Einige Anwendungen benötigen keine Benutzeroberfläche oder nur für eine minimale. Nehmen wir beispielsweise an, dass Sie schreiben:  
  
-   Ein intermediate Datenzugriff-Objekt, das Aufrufen von anderen Anwendungen (Clients) zur speziellen Verarbeitung von Daten zwischen der Anwendung und der Datenquelle.  
  
-   Eine Anwendung, die Daten ohne Eingreifen des Benutzers, z. B. eine Anwendung verarbeitet, die verschiebt Verwendungsdaten aus einem Datenbankformat in ein anderes oder ein, die Berechnungen und BatchUpdates ausführt.  
  
 Da kein Dokument besitzt die `CRecordset` -Objekt, möchten Sie wahrscheinlich als eingebetteten Datenmember in zu speichern Ihre `CWinApp`-Application-Klasse abgeleitet. Alternativen schließen:  
  
-   Kein permanentes `CRecordset` überhaupt-Objekt. Sie können übergeben **NULL** an die Konstruktoren der Recordset-Klasse. In diesem Fall erstellt das Framework eine temporäre `CDatabase` -Objekt anhand der Informationen in des Recordsets `GetDefaultConnect` Memberfunktion. Dies ist die wahrscheinlichste alternativer Ansatz.  
  
-   Machen die `CRecordset` -Objekt eine globale Variable. Diese Variable muss ein Zeiger auf ein Recordset-Objekt, das Sie dynamisch erstellen Ihrer `CWinApp::InitInstance` außer Kraft setzen. Dadurch wird vermieden, bei dem Versuch, das Objekt zu erstellen, bevor das Framework initialisiert wird.  
  
-   Verwenden Recordset-Objekte, wie Sie innerhalb des Kontexts eines Dokuments oder einer Sicht. Erstellen Sie Recordsets im Element Funktionen Ihrer Anwendung oder das Rahmenfenster Objekte.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Datenbankklassen](../data/mfc-database-classes-odbc-and-dao.md)