---
title: "MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten"
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
  - "Anwendungsassistenten [C++], Erstellen von Datenbankanwendungen"
  - "CDaoRecordView-Klasse, Verwenden in Datenbankanwendungen"
  - "CRecordView-Klasse, Verwenden in Datenbankanwendungen"
  - "DAO [C++], Dateiunterstützung in Datenbankanwendungen"
  - "DAO [C++], Schreiben von Anwendungen"
  - "Datenbankanwendungen [C++], Anwendungs-Assistent-Optionen"
  - "Datenbankanwendungen [C++], Ohne Dokumente"
  - "Datenbankanwendungen [C++], Ohne Ansichten"
  - "Datenbankklassen [C++], MFC"
  - "Dokument-/Ansichtsarchitektur [C++], In Datenbanken"
  - "Dokumente [C++], Anwendungen ohne"
  - "Dateien [C++], MFC"
  - "ODBC [C++], Dateiunterstützung in Datenbankanwendungen"
  - "ODBC-Anwendungen [C++]"
  - "ODBC-Anwendungen [C++], Ohne Dokumente"
  - "ODBC-Anwendungen [C++], Ohne Ansichten"
  - "Benutzeroberfläche [C++], Entwerfen von Informationen"
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Möglicherweise möchten Sie die Dokument\-\/\-Ansichtarchitektur der Grundstruktur in bestimmten Fällen nicht in Ihrer Datenbankanwendung verwenden.  In diesem Thema wird Folgendes erläutert:  
  
-   [Fälle, in denen Sie keine Dokumente verwenden müssen](#_core_when_you_don.92.t_need_documents), z. B. die Dokumentserialisierung.  
  
-   [Optionen des Anwendungs\-Assistenten](#_core_appwizard_options_for_documents_and_views) zur Unterstützung von Anwendungen ohne Serialisierung und ohne dokumentbezogene Befehle im Menü **Datei** \(z. B. **Neu**, **Öffnen**, **Speichern** und **Speichern unter**\).  
  
-   [Arbeiten mit einer Anwendung, die minimale Dokumente erfordert](#_core_applications_with_minimal_documents).  
  
-   [Strukturieren einer Anwendung ohne Dokumente oder Ansichten](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a> Fälle, in denen Sie keine Dokumente benötigen  
 In einigen Anwendungen gibt es ein genau umrissenes Konzept des Dokuments.  In solchen Anwendungen wird mit dem Befehl Öffnen im Menü **Datei** normalerweise eine ganze Datei oder zumindest ein großer Teil davon aus dem Speicher in den Arbeitsspeicher geladen.  Die aktualisierte Datei wird mit den Befehlen **Speichern** oder **Speichern unter** als Ganzes wieder auf den Datenträger geschrieben.  Das Ergebnis wird dem Benutzer als Datei angezeigt.  
  
 Manche Anwendungskategorien benötigen jedoch kein Dokument.  Datenbankanwendungen arbeiten mit so genannten Transaktionen.  Die Anwendung wählt aus einer Datenbank Datensätze aus und zeigt diese dem Benutzer meist einzeln an.  Dem Benutzer wird in der Regel ein einzelner aktueller Datensatz angezeigt. Dieser ist möglicherweise der einzige Datensatz im Hauptspeicher.  
  
 Falls Ihre Anwendung zum Speichern von Daten kein Dokument benötigt, können Sie auf die Dokument\-\/Ansichtarchitektur der Grundstruktur ganz oder teilweise verzichten.  Auf welche Teile Sie verzichten, hängt von dem von Ihnen bevorzugten Ansatz ab.  Es gibt folgende Möglichkeiten:  
  
-   Sie verwenden ein minimales Dokument für die Speicherung einer Verbindung zur Datenquelle, verzichten aber auf normale Dokumentfunktionen, z. B. die Serialisierung.  Dies ist sinnvoll, wenn Sie verschiedene Ansichten der Daten wünschen und alle Ansichten synchronisieren und dabei alle gleichzeitig aktualisieren möchten usw.  
  
-   Sie verwenden anstelle einer Ansicht ein Rahmenfenster, in das Sie direkt zeichnen.  In diesem Fall lassen Sie das Dokument weg und speichern alle Daten oder Datenverbindungen im Rahmenfensterobjekt.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a> Optionen des Anwendungs\-Assistenten für Dokumente und Ansichten  
 Im MFC\-Anwendungs\-Assistenten stehen Ihnen unter **Datenbankunterstützung** die in der folgenden Liste aufgeführten Optionen zur Verfügung.  Wenn Sie den MFC\-Anwendungs\-Assistenten zum Erstellen einer Anwendung verwenden, werden durch alle hier aufgeführten Optionen Anwendungen mit Dokumenten und Ansichten generiert.  Einige dieser Optionen stellen Dokumente und Ansichten zur Verfügung, die auf nicht benötigte Dokumentenfunktionen verzichten.  Weitere Informationen finden Sie unter [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Option|Ansicht|Document|  
|------------|-------------|--------------|  
|**Kein**|Abgeleitet von `CView`.|Bietet keine Datenbankunterstützung.  Dies ist die Standardoption.<br /><br /> Wenn Sie auf der Seite [Anwendungstyp, MFC\-Anwendungs\-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** auswählen, stehen Ihnen die vollständige Dokumentunterstützung einschließlich der Serialisierung sowie die im Menü **Datei** enthaltenen Befehle `New`, **Öffnen**, **Speichern** und **Speichern unter** zur Verfügung.  Siehe [Anwendungen ohne Dokumente](#_core_applications_with_no_document).|  
|**Nur Headerdateien**|Abgeleitet von `CView`.|Bietet grundlegende Datenbankunterstützung für die Anwendung.<br /><br /> Enthält Afxdb.h.  Fügt Linkbibliotheken hinzu, erstellt jedoch keine datenbankspezifischen Klassen.  Später können Sie Recordsets für die Überprüfung und Aktualisierung von Datensätzen erstellen.|  
|**Datenbankansicht ohne Dateiunterstützung**|Abgeleitet von CRecordView|Bietet Dokumentunterstützung, jedoch keine Serialisierungsunterstützung.  Das Dokument kann Recordsets speichern und mehrere Ansichten koordinieren; unterstützt weder Serialisierung noch die Befehle `New`, **Öffnen**, **Speichern** oder **Speichern unter**.  Siehe [Anwendungen mit minimalen Dokumenten](#_core_applications_with_minimal_documents).  Wenn Sie eine Datenbankansicht einschließen, müssen Sie die Datenquelle angeben.<br /><br /> Umfasst Datenbank\-Headerdateien, Linkbibliotheken, eine Datensatzansicht und ein Recordset. \(Nur für Anwendungen verfügbar, für die auf der Seite [Anwendungstyp, MFC\-Anwendungs\-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert wurde.\)|  
|**Datenbankansicht mit Dateiunterstützung**|Abgeleitet von CRecordView|Bietet vollständige Dokumentunterstützung einschließlich Serialisierung und der dokumentbezogenen Befehle des Menüs **Datei**.  Datenbankanwendungen arbeiten in der Regel auf der Basis einzelner Datensätze und nicht auf der Basis einzelner Dateien. Aus diesem Grund müssen sie nicht serialisiert werden.  Unter Umständen benötigen Sie die Serialisierung jedoch für andere Aufgaben.  Siehe [Anwendungen mit minimalen Dokumenten](#_core_applications_with_minimal_documents).  Wenn Sie eine Datenbankansicht einschließen, müssen Sie die Datenquelle angeben.<br /><br /> Umfasst Datenbank\-Headerdateien, Linkbibliotheken, eine Datensatzansicht und ein Recordset. \(Nur für Anwendungen verfügbar, für die auf der Seite [Anwendungstyp, MFC\-Anwendungs\-Assistent](../mfc/reference/application-type-mfc-application-wizard.md) die Option **Unterstützung für die Dokument\-\/Ansichtarchitektur** aktiviert wurde.\)|  
  
 Informationen über Alternativen zur Serialisierung und den alternativen Gebrauch der Serialisierung finden Sie unter [Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a> Anwendungen mit minimalen Dokumenten  
 Der MFC\-Anwendungs\-Assistent verfügt über zwei Optionen zur Unterstützung von formularbasierten Datenzugriffsanwendungen.  Jede Option erstellt eine von CRecordView abgeleitete Ansichtsklasse und ein Dokument.  Sie unterscheiden sich durch die Elemente, die im Dokument ausgelassen werden.  
  
###  <a name="_core_a_document_without_file_support"></a> Dokumente ohne Dateiunterstützung  
 Wählen Sie im Anwendungs\-Assistenten die Datenbankoption **Datenbankansicht ohne Dateiunterstützung** aus, wenn Sie keine Dokumentserialisierung benötigen.  Das Dokument kann zu folgenden Zwecken genutzt werden:  
  
-   Als geeigneter Ort zum Speichern eines CRecordset\-Objekts.  
  
     Diese Verwendung entspricht dem üblichen Dokumentkonzept: Das Dokument speichert die Daten \(bzw. in diesem Fall ein Recordset\), und die Ansicht ist eine Ansicht des Dokuments.  
  
-   Falls Ihre Anwendung mehrere Ansichten anzeigt \(beispielsweise mehrere Datensatzansichten\), unterstützt ein Dokument die Koordination der Ansichten.  
  
     Werden in mehreren Ansichten dieselben Daten angezeigt, können Sie mit der Memberfunktion `CDocument::UpdateAllViews` die Aktualisierung aller Ansichten auslösen, sobald die Daten in einer der Ansichten geändert werden.  
  
 Normalerweise verwenden Sie diese Option für einfache formularbasierte Anwendungen.  Der Anwendungs\-Assistent unterstützt eine geeignete Struktur für solche Anwendungen automatisch.  
  
###  <a name="_core_a_document_with_file_support"></a> Dokumente mit Dateiunterstützung  
 Wählen Sie im Anwendungs\-Assistenten die Datenbankoption **Datenbankansicht mit Dateiunterstützung**, wenn Sie eine alternative Verwendungsmöglichkeit für die dokumentbezogenen Befehle des Menüs **Datei** und die Dokumentserialisierung haben.  Für die Datenzugriffselemente Ihres Programms können Sie das Dokument genauso verwenden, wie es unter [Dokumente ohne Dateiunterstützung](#_core_a_document_without_file_support) beschrieben ist.  Sie können die Serialisierungsfunktionen des Dokuments z. B. zum Lesen und Schreiben eines serialisierten Benutzerprofildokuments verwenden, das die Benutzervoreinstellungen oder andere nützliche Daten speichert.  Weitere Anregungen finden Sie unter [Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Der Anwendungs\-Assistent unterstützt diese Option, Sie müssen den Code zur Serialisierung des Dokuments jedoch selbst eingeben.  Speichern Sie die serialisierten Informationen in den Datenmembers des Dokuments.  
  
##  <a name="_core_applications_with_no_document"></a> Anwendungen ohne Dokumente  
 Möglicherweise möchten Sie auch Anwendungen entwickeln, die weder Dokumente noch Ansichten verwenden.  Ohne Dokumente speichern Sie die Daten \(z. B. ein CRecordset\-Objekt\) in der Rahmenfensterklasse oder in der Anwendungsklasse.  Ob zusätzliche Elemente benötigt werden, hängt davon ab, ob die Anwendung über eine Benutzeroberfläche verfügt.  
  
###  <a name="_core_database_support_with_a_user_interface"></a> Datenbankunterstützung mit Benutzeroberfläche  
 Falls Ihre Anwendung über eine Benutzeroberfläche verfügt \(die beispielsweise über eine Befehlszeilenschnittstelle hinausgeht\), zeichnet die Anwendung nicht in eine Ansicht, sondern direkt in den Clientbereich des Rahmenfensters.  Eine solche Anwendung verwendet für die primäre Benutzeroberfläche weder `CRecordView`, `CFormView` noch `CDialog`. Für gewöhnliche Dialoge wird in der Regel jedoch `CDialog` verwendet.  
  
###  <a name="_core_writing_applications_without_documents"></a> Schreiben von Anwendungen ohne Dokumente  
 Der Anwendungs\-Assistent unterstützt nicht die Erstellung von Anwendungen ohne Dokumente, deshalb müssen Sie eine eigene, von `CWinApp` abgeleitete Klasse schreiben und bei Bedarf außerdem eine `CFrameWnd`\-Klasse oder `CMDIFrameWnd`\-Klasse anlegen.  Überschreiben Sie CWinApp::InitInstance und deklarieren Sie ein Anwendungsobjekt als:  
  
```  
CYourNameApp theApp;  
```  
  
 Das Framework unterstützt weiterhin den Mechanismus zur Meldungszuordnung und viele weitere Funktionen.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a> Datenbankunterstützung von Benutzeroberfläche getrennt  
 Manche Anwendungen benötigen überhaupt keine oder nur eine minimale Benutzeroberfläche.  Nehmen wir beispielsweise Folgendes an:  
  
-   Sie schreiben ein Datenzugriffsobjekt, das von anderen Anwendungen \(Clients\) zur speziellen Verarbeitung von Daten zwischen der Anwendung und der Datenquelle aufgerufen wird.  
  
-   Sie schreiben eine Anwendung, die Daten ohne Benutzereingaben verarbeitet, z. B. eine Anwendung, die Daten von einem Datenbankformat in ein anderes konvertiert oder Berechnungen und Batchaktualisierungen durchführt.  
  
 Da kein Dokument das `CRecordset`\-Objekt oder `CDaoRecordset`\-Objekt besitzt, sollten Sie es als eingebetteten Datenmember in der von `CWinApp` abgeleiteten Anwendungsklasse speichern.  Alternativen dazu wären:  
  
-   Sie verwenden überhaupt kein permanentes `CRecordset`\- oder `CDaoRecordset`\-Objekt.  Sie können an die Konstruktoren der Recordset\-Klasse **NULL** übergeben.  In diesem Fall legt die Grundstruktur mithilfe der Informationen in der `GetDefaultConnect`\-Memberfunktion des Recordsets ein temporäres `CDatabase`\- oder `CDaoDatabase`\-Objekt an.  Dies ist der gebräuchlichste alternative Ansatz.  
  
-   Sie machen das `CRecordset`\- oder `CDaoRecordset`\-Objekt zu einer globalen Variablen.  Diese Variable sollte ein Zeiger auf ein Recordset\-Objekt sein, das Sie beim Überschreiben von `CWinApp::InitInstance` dynamisch erstellen.  Dadurch wird verhindert, dass das Objekt vor der Initialisierung der Grundstruktur konstruiert wird.  
  
-   Sie können die Recordset\-Objekte genau wie im Kontext eines Dokuments oder einer Ansicht verwenden.  Sie erstellen Recordsets in den Memberfunktionen der Anwendungs\- oder Rahmenfensterobjekte.  
  
## Siehe auch  
 [MFC\-Datenbankklassen \(ODBC und DAO\)](../data/mfc-database-classes-odbc-and-dao.md)