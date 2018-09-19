---
title: 'MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten | Microsoft-Dokumentation'
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
ms.openlocfilehash: 999fa2e30a769f925555207675010cf1039bfb8b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101993"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten

In einigen Fällen können Sie nicht die Framework Dokument-/Ansichtarchitektur in datenbankanwendungen verwenden möchten. In diesem Thema wird Folgendes erläutert:  
  
- [Wenn Sie nicht möchten Dokumente](#_core_when_you_don.92.t_need_documents) z. B. die Dokumentserialisierung.  
  
- [Assistenten-Optionen für Anwendungen](#_core_appwizard_options_for_documents_and_views) zur Unterstützung von Anwendungen ohne Serialisierung und dokumentbezogene **Datei** Menübefehle, z. B. **neu**, **öffnen** , **Speichern**, und **speichern als**.  
  
- [Gewusst wie: Arbeiten mit einer Anwendung, die eine minimale Dokumente verwendet](#_core_applications_with_minimal_documents).  
  
- [Wie Sie eine Anwendung keine Dokumente oder Ansichten strukturieren](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a> Wann benötigen Sie keine Dokumente  

Einige Anwendungen verfügen, unterscheidet sich vom Konzept eines Dokuments. Diese Anwendungen in der Regel Laden einer Datei die meisten oder alle aus dem Speicher in den Arbeitsspeicher mit einem **Datei öffnen** Befehl. Die aktualisierte Datei wieder auf den Datenträger geschrieben gleichzeitig mit einer **Datei speichern** oder **speichern** Befehl. Welche dem Benutzer angezeigt wird, ist eine Datendatei.  
  
Einige Kategorien von Anwendungen ist ein Dokument jedoch nicht erforderlich. Datenbankanwendungen, die im Hinblick auf Transaktionen ausgeführt werden. Die Anwendung wählt die Datensätze einer Datenbank und präsentiert diese dem Benutzer, häufig jeweils einzeln. Welche dem Benutzer angezeigt wird, ist normalerweise ein einzelner aktueller Datensatz an, der möglicherweise die einzige im Arbeitsspeicher.  
  
Wenn Ihre Anwendung kein Dokuments zum Speichern von Daten erfordert, können Sie einige oder alle der Framework Dokument-/Ansichtarchitektur verzichten. Wie viel Sie verzichten, hängt von der von Ihnen bevorzugten Ansatz. Sie können:  
  
- Verwenden Sie minimale Dokumente als Ort, um eine Verbindung mit der Datenquelle zu speichern, aber mit normalen Dokumentfunktionen, z. B. die Serialisierung verteilen. Dies ist nützlich, wenn Sie mehrere Ansichten der Daten und synchronisiert werden alle Ansichten sollen, aktualisieren sie alle auf einmal und so weiter.  
  
- Verwenden Sie ein Rahmenfenster, in dem Sie direkt zeichnen, anstatt mit einer Ansicht. Sie können in diesem Fall lassen Sie das Dokument und Speichern von Daten oder die datenverbindungen in dem Rahmenfenster-Objekt.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a> Application-Assistent-Optionen für Dokumente und Ansichten  

Der MFC-Anwendung-Assistent bietet mehrere Optionen **wählen datenbankunterstützung**, die in der folgenden Tabelle aufgeführt sind. Wenn Sie den MFS-Anwendungsassistenten verwenden, um eine Anwendung zu erstellen, erzeugen alle Optionen Anwendungen mit Dokumenten und Ansichten. Einige Optionen bieten die Dokumente und Ansichten, die nicht benötigten Dokument Funktionalität auslassen. Weitere Informationen finden Sie unter [Datenbankunterstützung, MFC-Anwendungs-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Option|Ansicht|Dokument|  
|------------|----------|--------------|  
|**Keine**|Abgeleitet von `CView`.|Bietet keine datenbankunterstützung. Dies ist die Standardoption.<br /><br /> Bei Auswahl der **Unterstützung für die Dokument-/Ansicht** option die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite erhalten Sie vollständige Document-Unterstützung, einschließlich der Serialisierung und **neu** , **Öffnen**, **speichern**, und **speichern** von Befehlen auf die **Datei** Menü. Finden Sie unter [Anwendungen ohne Dokument](#_core_applications_with_no_document).|  
|**Nur Headerdateien**|Abgeleitet von `CView`.|Stellt die Basisebene der datenbankunterstützung für Ihre Anwendung bereit.<br /><br /> Enthält Afxdb.h. Fügt der DLLs, aber erstellt keine Datenbank-spezifische Klassen. Sie können die Recordsets später erstellen und verwenden diese zum Überprüfen und Aktualisieren von Datensätzen.|  
|**Datenbankansicht ohne dateiunterstützung**|Abgeleitet von `CRecordView`|Bietet dokumentunterstützung aber keine Serialisierungsunterstützung. Dokument speichern Recordset und Koordinieren von mehreren Ansichten; unterstützt keine Serialisierung oder **neu**, **öffnen**, **speichern**, und **speichern** Befehle. Finden Sie unter [Anwendungen mit minimalen Dokumente](#_core_applications_with_minimal_documents). Wenn Sie eine Ansicht einfügen, müssen Sie die Quelle der Daten angeben.<br /><br /> Enthält Datenbank-Header-Dateien, DLLs, einer Datensatzansicht und einem Recordset. (Nur für Anwendungen mit der **Unterstützung für die Dokument-/Ansicht** Option ausgewählt wird, auf die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite.)|  
|**Datenbankansicht mit dateiunterstützung**|Abgeleitet von `CRecordView`|Unterstützt vollständige Dokument, einschließlich Serialisierung und dokumentbezogene **Datei** Menübefehle. Datenbankanwendungen arbeiten in der Regel individuell für einzelne Datensätze, statt auf einer pro-Datei-Basis und daher keine Serialisierung erforderlich ist. Allerdings müssen Sie eine besondere Verwendung für die Serialisierung möglicherweise. Finden Sie unter [Anwendungen mit minimalen Dokumente](#_core_applications_with_minimal_documents). Wenn Sie eine Ansicht einfügen, müssen Sie die Quelle der Daten angeben.<br /><br /> Enthält Datenbank-Header-Dateien, DLLs, einer Datensatzansicht und einem Recordset. (Nur für Anwendungen mit der **Unterstützung für die Dokument-/Ansicht** Option ausgewählt wird, auf die [Anwendungstyp, MFC-Anwendungs-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) Seite.)|  
  
Eine Erläuterung der alternativen zur Serialisierung und andere Verwendungszwecke der Serialisierung, finden Sie unter [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a> Anwendungen mit minimalen Dokumente  

Der MFC-Anwendung-Assistent verfügt über zwei Optionen, die Unterstützung von formularbasierten datenzugriffsanwendungen. Jede Option erstellt eine `CRecordView`-abgeleiteten Ansichtsklasse und ein Dokument. Sie unterscheiden sich in was eine aus dem Dokument verlassen.  
  
###  <a name="_core_a_document_without_file_support"></a> Dokument ohne Dateiunterstützung  

Wählen Sie die Anwendung-Assistent-Datenbankoption **-Datenbanksicht ohne dateiunterstützung** Wenn Sie nicht die Dokumentserialisierung erforderlich ist. Das Dokument erfüllt folgende Zwecke hilfreich:  
  
- Es ist ein praktischer Ort zum Speichern einer `CRecordset` Objekt.  
  
     Diese Verwendung entspricht normalen Dokumentkonzepte: das Dokument speichert die Daten (oder in diesem Fall eine Gruppe von Datensätzen) und die Ansicht ist eine Ansicht des Dokuments.  
  
- Wenn Ihre Anwendung mehrere Ansichten (z. B. mehrere Datensatzansichten) vorweisen, unterstützt ein Dokument mit der Koordination der Ansichten.  
  
     Wenn mehrere Ansichten der gleichen Daten anzeigen möchten, können Sie mithilfe der `CDocument::UpdateAllViews` Memberfunktion zum Koordinieren von Updates für alle Ansichten bei Änderung von einer beliebigen Ansicht der Daten.  
  
In der Regel verwenden Sie diese Option für einfache, formularbasierte Anwendungen. Der Anwendungs-Assistent unterstützt eine einfache Struktur für solche Anwendungen automatisch.  
  
###  <a name="_core_a_document_with_file_support"></a> Dokument mit Dateiunterstützung  

Wählen Sie die Anwendung-Assistent-Datenbankoption **-Datenbanksicht mit dateiunterstützung** , wenn Sie haben eine alternative Verwendung für die dokumentbezogene **Datei** Menübefehle und Dokumentserialisierung. Für den Datenzugriff Teil des Programms, können Sie das Dokument auf die gleiche Weise wie in beschrieben [Dokument ohne Dateiunterstützung](#_core_a_document_without_file_support). Serialisierung-Funktion des Dokuments ab, können zum Beispiel lesen und Schreiben eines Dokuments der serialisierte Benutzer-Profil, das die Einstellungen des Benutzers und weitere nützliche Informationen speichert. Weitere Ideen finden Sie unter [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).  
  
Der Anwendungs-Assistent unterstützt diese Option, aber Sie müssen den Code, der das Dokument serialisiert schreiben. Store die serialisierte Informationen im Dokument-Datenmember.  
  
##  <a name="_core_applications_with_no_document"></a> Anwendungen ohne Dokument  

Möglicherweise möchten Sie manchmal eine Anwendung schreiben, die keine Dokumente oder Ansichten verwendet. Ohne Dokumente, die Sie speichern Ihre Daten (z. B. eine `CRecordset` Objekt) in Ihrer Klasse oder Ihrer Anwendungsklasse. Ggf. zusätzlichen Anforderungen hängen davon ab, ob die Anwendung eine Benutzeroberfläche verfügt.  
  
###  <a name="_core_database_support_with_a_user_interface"></a> Unterstützung von Datenbanken mit einer Benutzeroberfläche  

Wenn Sie eine Benutzeroberfläche (außer, z. B. eine Konsole-Befehlszeilen-Schnittstelle) verfügen, zeichnet die Anwendung direkt in den Clientbereich des Rahmenfensters statt in einer Ansicht. Eine solche Anwendung verwendet keine `CRecordView`, `CFormView`, oder `CDialog` für die primäre Benutzeroberfläche, aber normalerweise verwenden `CDialog` für normale Dialogfelder.  
  
###  <a name="_core_writing_applications_without_documents"></a> Schreiben von Anwendungen ohne Dokumente  

Da Sie der Assistenten zum Erstellen von Anwendungen ohne Dokumente nicht unterstützt, müssen Sie schreiben Ihre eigenen `CWinApp`-abgeleiteten Klasse, und erstellen Sie bei Bedarf auch einen `CFrameWnd` oder `CMDIFrameWnd` Klasse. Außer Kraft setzen `CWinApp::InitInstance` und ein Anwendungsobjekt als deklarieren:  
  
```cpp  
CYourNameApp theApp;  
```  
  
Das Framework stellt immer noch der meldungszuordnungsmechanismus und viele weitere Funktionen bereit.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a> Datenbank-Unterstützung von separaten über die Benutzeroberfläche  

Einige Anwendungen benötigen keine Benutzeroberfläche oder nur eine minimale ein. Nehmen wir beispielsweise an, dass Sie schreiben:  
  
- Ein intermediate Datenzugriff-Objekt, das Aufrufen von anderen Anwendungen (Clients) zur speziellen Verarbeitung von Daten zwischen der Anwendung und der Datenquelle.  
  
- Eine Anwendung, die Daten ohne Eingreifen des Benutzers, z. B. eine Anwendung verarbeitet werden, die Daten aus einem Datenbankformat in ein anderes oder ein, die Berechnungen und führt BatchUpdates durch verschoben.  
  
Da kein Dokument besitzt die `CRecordset` Objekt, möchten Sie wahrscheinlich als eine eingebettete Datenmember in speichern Ihre `CWinApp`-Application-Klasse abgeleitet. Alternativen sind:  
  
- Kein permanentes `CRecordset` überhaupt Objekt. Sie können NULL an die Konstruktoren der Recordset-Klasse übergeben. In diesem Fall erstellt das Framework eine temporäre `CDatabase` Objekt anhand der Informationen in der Recordsets `GetDefaultConnect` Member-Funktion. Dies ist die am wahrscheinlichsten alternative Vorgehensweise.  
  
- Wodurch die `CRecordset` -Objekt eine globale Variable. Diese Variable muss ein Zeiger auf ein Recordsetobjekt, das Sie dynamisch erstellen Ihre `CWinApp::InitInstance` außer Kraft setzen. Dadurch wird vermieden, es wird versucht, die das Objekt zu erstellen, bevor das Framework initialisiert wird.  
  
- Recordset-Objekte verwenden, wie Sie innerhalb des Kontexts eines Dokuments oder einer Ansicht. Erstellen Sie durch Recordsets im Member Funktionen Ihrer Anwendung oder ein Rahmenfenster Objekte.  
  
## <a name="see-also"></a>Siehe auch  

[MFC-Datenbankklassen](../data/mfc-database-classes-odbc-and-dao.md)