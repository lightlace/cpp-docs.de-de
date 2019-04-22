---
title: 'MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten'
ms.date: 11/04/2016
helpviewer_keywords:
- documents [C++], database applications
- recordsets [C++], documents and views
- CRecordView class, using in database forms
- views [C++], database applications
- forms [C++], database applications
- record views [C++], form-based applications
- document/view architecture [C++], in databases
- database applications [C++], forms
- database classes [C++], MFC
- ODBC recordsets [C++], documents and views
- ODBC [C++], forms
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
ms.openlocfilehash: 78765d17b52889123f13c492699230834decba66
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59026291"
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten

Sie können die MFC-Datenbankklassen mit oder ohne die Dokument-/Ansichtarchitektur verwenden. In diesem Thema hebt hervor, arbeiten mit Dokumenten und Ansichten. Es wird erläutert:

- [Gewusst wie: Schreiben einer formularbasierten Anwendung](#_core_writing_a_form.2d.based_application) mithilfe einer `CRecordView` -Objekt als die Hauptansicht in Ihr Dokument.

- [Wie Sie mit der Recordsets in Dokumenten und Ansichten](#_core_using_recordsets_in_documents_and_views).

- [Weitere Überlegungen zur](#_core_other_factors).

Alternativen, finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).

##  <a name="_core_writing_a_form.2d.based_application"></a> Das Schreiben einer formularbasierten Anwendung

Viele Datenzugriffs-Anwendungen basieren auf Formularen. Die Benutzeroberfläche ist ein Formular mit Steuerelementen, die in denen der Benutzer überprüft wird, gibt, oder Bearbeiten von Daten. Verwenden Sie die Klasse, um Ihre Anwendung formularbasiert zu machen, `CRecordView`. Wenn Sie den Assistenten zum MFC-Anwendungen ausführen und **ODBC** Clienttyp auf die **Datenbankunterstützung** Seite das Projekt verwendet `CRecordView` für die Ansichtsklasse.

In einer formularbasierten Anwendung jedes Datensatzansichts-Objekt speichert einen Zeiger auf eine `CRecordset` Objekt. Die Framework Datensatzfeldaustausch (RFX)-Mechanismus Datenaustausch zwischen dem Recordset und der Datenquelle an. Die Dialogdatenaustausch (DDX)-Mechanismus eine Übertragung von Daten zwischen den Felddatenmembern des Recordset-Objekts und den Steuerelementen im Formular. `CRecordView` Standardmäßig bietet auch befehlshandlerfunktionen für die Navigation zwischen Datensätzen auf dem Formular an.

Zum Erstellen einer formularbasierten Anwendung mit der Anwendungs-Assistenten finden Sie unter [Erstellen einer formularbasierten MFC-Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) und [Datenbankunterstützung, MFC-Anwendungs-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).

Eine vollständige Erläuterung der Formulare, finden Sie unter [Datensatzansichten](../data/record-views-mfc-data-access.md).

##  <a name="_core_using_recordsets_in_documents_and_views"></a> Verwenden von Recordsets in Dokumenten und Ansichten

Viele einfache formularbasierte Anwendungen ist die Dokumente nicht erforderlich. Wenn Ihre Anwendung komplexer ist, wahrscheinlich ein Dokument als Proxy für die Datenbank verwenden möchten, Speichern einer `CDatabase` -Objekt, das eine Verbindung mit der Datenquelle herstellt. Formularbasierte Anwendungen speichern normalerweise einen Zeiger auf einem Recordset-Objekt in der Ansicht. Andere Arten von datenbankanwendungen speichern Recordsets und `CDatabase` Objekt im Dokument. Hier sind einige Möglichkeiten für die Verwendung von Dokumenten in datenbankanwendungen:

- Wenn Sie ein Recordset in einem lokalen Kontext zugreifen möchten, erstellen Sie eine `CRecordset` Objekt lokal in Memberfunktionen des Dokuments oder der Ansicht, je nach Bedarf.

   Deklarieren Sie ein Recordset-Objekt als eine lokale Variable in einer Funktion an. Übergeben Sie NULL an den Konstruktor, der bewirkt, dass das Framework zum Erstellen und öffnen eine temporäre `CDatabase` -Objekt für Sie. Als Alternative, übergeben Sie einen Zeiger auf eine `CDatabase` Objekt. Verwenden Sie das Recordset in der Funktion, und lassen sie die automatisch zerstört, wenn die Funktion beendet wird.

   Wenn Sie NULL an den Recordset-Konstruktor übergeben, wird durch das Framework verwendet, von der Recordsets zurückgegebenen Informationen `GetDefaultConnect` Member-Funktion zum Erstellen einer `CDatabase` Objekt aus, und öffnen Sie sie. Implementieren Sie die Assistenten `GetDefaultConnect` für Sie.

- Wenn Sie während der Lebensdauer des Dokuments auf einem Recordset zugreifen, betten Sie eine oder mehrere `CRecordset` Objekte in Ihrem Dokument.

   Erstellen Sie das Recordset-Objekte, bei der Initialisierung des Dokuments oder nach Bedarf. Sie können eine Funktion schreiben, die einen Zeiger auf das Recordset zurückgibt, wenn er bereits vorhanden ist oder erstellt und öffnet das Recordset aus, wenn sie noch nicht vorhanden ist. Schließen, löschen, und das Recordset nach Bedarf neu erstellen oder rufen Sie die `Requery` Memberfunktion versucht, die Datensätze zu aktualisieren.

- Wenn Sie während der Lebensdauer des Dokuments auf eine Datenquelle zugreifen, Einbetten einer `CDatabase` Objekt oder einen Zeiger auf eine `CDatabase` -Objekt.

   Die `CDatabase` Objekt verwaltet eine Verbindung mit Ihrer Datenquelle. Das Objekt wird automatisch während der Erstellung des Dokuments erstellt, und rufen Sie die `Open` Member-Funktion, die beim Initialisieren des Dokuments. Erstellen der Recordset-Objekte im Dokument-Memberfunktionen übergeben Sie einen Zeiger auf des Dokuments des `CDatabase` Objekt. Dies ordnet jedes Recordset, mit dessen Datenquelle. In der Regel wird das Datenbankobjekt, das zerstört, wenn das Dokument geschlossen wird. Das Recordset-Objekte in der Regel zerstört, wenn sie den Bereich einer Funktion beenden.

##  <a name="_core_other_factors"></a> Andere Faktoren

Formularbasierte Anwendungen häufig verfügen nicht über keine Verwendung für die Framework Dokument-Serialisierungsmechanismus, daher Sie sollten zu entfernen, deaktivieren oder zu ersetzen die **neu** und **öffnen** Befehle in der **Datei** Menü. Finden Sie im Artikel [Serialisierung: Serialisierung im Vergleich zu Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).

Möchten Sie möglicherweise auch, verwenden Sie die vielen Benutzeroberflächen-Möglichkeiten, die das Framework unterstützt werden. Beispielsweise können Sie mehrere `CRecordView` Objekte in einem Splitterfenster kann mehrere Recordsets in verschiedenen öffnen, mehrere Document Interface (MDI) untergeordnete Fenster und So weiter.

Drucken des Inhalts in der Ansicht implementieren möchten, sei es ein Formular implementiert, mit `CRecordView` oder etwas anderes. Abgeleitete Klassen `CFormView`, `CRecordView` Drucken nicht unterstützt, aber Sie können überschreibt die `OnPrint` Member-Funktion mit dem Drucken zulässig. Weitere Informationen finden Sie in der Klasse [CFormView](../mfc/reference/cformview-class.md).

Sie möchten keine Dokumente und Ansichten verwenden. In diesem Fall finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).

## <a name="see-also"></a>Siehe auch

[MFC-Datenbankklassen](../data/mfc-database-classes-odbc-and-dao.md)