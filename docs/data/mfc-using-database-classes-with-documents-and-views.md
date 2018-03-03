---
title: 'MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d3e2286c10d83b25576474692b5a7faeb9bb332
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-using-database-classes-with-documents-and-views"></a>MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten
Sie können die MFC-Datenbankklassen mit oder ohne die Dokument-/Ansichtarchitektur. Dieses Thema hebt hervor, arbeiten mit Dokumenten und Ansichten. Es wird Folgendes erläutert:  
  
-   [Gewusst wie: Schreiben einer formularbasierten Anwendung](#_core_writing_a_form.2d.based_application) mit einem `CRecordView` Objekt als die Hauptansicht im Dokument.  
  
-   [Gewusst wie: Verwenden des Recordset-Objekte in Ihre Dokumente und Ansichten](#_core_using_recordsets_in_documents_and_views).  
  
-   [Andere Aspekte](#_core_other_factors).  
  
 Alternativen für finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
##  <a name="_core_writing_a_form.2d.based_application"></a>Schreiben einer formularbasierten Anwendung  
 Viele formularbasierten datenzugriffsanwendungen basieren auf Formularen. Die Benutzeroberfläche wird ein Formular mit Steuerelementen, die in denen der Benutzer überprüft, eingibt, oder Bearbeiten von Daten. Verwenden Sie die Klasse, um Ihre Anwendung formularbasiert zu machen, `CRecordView`. Wenn Sie den MFC-Anwendung-Assistenten ausführen und **ODBC** Clienttyp auf die **Datenbankunterstützung** Seite im Projekt verwendet `CRecordView` für die Ansichtsklasse.
  
 In einer formularbasierten Anwendung speichert jedes Datensatzansichts-Objekt einen Zeiger auf eine `CRecordset` Objekt. Das Framework Datensatzfeldaustausch (RFX)-Mechanismus tauscht Daten zwischen des Recordsets und der Datenquelle. Der Dialogdatenaustausch (DDX) Mechanismus Austausch von Daten zwischen den Felddatenmembern eines Recordset-Objekts und den Steuerelementen im Formular. `CRecordView`stellt auch befehlshandlerfunktionen für die Navigation zwischen Datensätzen auf dem Formular.  
  
 Zum Erstellen einer formularbasierten Anwendung mit dem Anwendungs-Assistenten finden Sie unter [Erstellen einer formularbasierten MFC-Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) und [Datenbankunterstützung, MFC-Anwendungs-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Eine vollständige Erläuterung der Formen, finden Sie unter [Datensatzansichten](../data/record-views-mfc-data-access.md).  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a>Verwenden von Recordsets in Dokumenten und Ansichten  
 Viele einfache formularbasierte Anwendungen ist die Dokumente nicht erforderlich. Wenn Ihre Anwendung komplexer ist, wahrscheinlich ein Dokument als Proxy für die Datenbank verwenden möchten, das Speichern einer `CDatabase` , mit der Datenquelle verbunden wird. Formularbasierte Anwendungen speichern normalerweise einen Zeiger auf einem Recordset-Objekt in der Ansicht. Andere Arten von datenbankanwendungen speichern Recordsets und `CDatabase` Objekt in das Dokument. Hier sind einige Möglichkeiten zum Verwenden von Dokumenten in datenbankanwendungen:  
  
-   Wenn Sie ein Recordset in einem lokalen Kontext zugreifen, erstellen Sie eine `CRecordset` -Objekt lokal in Memberfunktionen des Dokuments oder der Sicht, nach Bedarf.  
  
     Deklarieren Sie ein Recordset-Objekt als eine lokale Variable in einer Funktion. Übergeben Sie **NULL** an den Konstruktor, wodurch das Framework zum Erstellen und öffnen einen temporären `CDatabase` Objekt für Sie. Als Alternative, übergeben Sie einen Zeiger auf eine `CDatabase` Objekt. Verwenden Sie das Recordset innerhalb der Funktion, und lassen Sie ihn automatisch zerstört werden, wenn die Funktion beendet wird.  
  
     Beim übergeben **NULL** an einem Recordset-Konstruktor verwendet das Framework durch des Recordsets zurückgegebenen Informationen `GetDefaultConnect` Memberfunktion zum Erstellen einer `CDatabase` Objekt, und öffnen Sie ihn. Implementieren Sie die Assistenten `GetDefaultConnect` für Sie.  
  
-   Wenn Sie während der Lebensdauer des Dokuments auf einem Recordset zugreifen einbetten, eine oder mehrere `CRecordset` Objekte in Ihrem Dokument.  
  
     Recordset-Objekte zu erstellen, wenn Sie das Dokument initialisieren oder nach Bedarf. Sie können eine Funktion schreiben, die einen Zeiger auf das Recordset zurückgibt, wenn er bereits vorhanden ist oder erstellt und öffnet das Recordset, wenn sie noch nicht vorhanden ist. Schließen, löschen, und das Recordset nach Bedarf neu erstellen oder Aufrufen seiner **Requery** Memberfunktion versucht, die Datensätze zu aktualisieren.  
  
-   Wenn Sie während der Lebensdauer des Dokuments auf eine Datenquelle zugreifen, einbetten eine `CDatabase` -Objekt oder einen Zeiger auf Speichern eine `CDatabase` -Objekt.  
  
     Die `CDatabase` -Objekt verwaltet eine Verbindung mit Ihrer Datenquelle. Das Objekt wird automatisch während der Erstellung des Dokuments erstellt, und rufen Sie die **öffnen** Memberfunktion, wenn Sie das Dokument initialisieren. Erstellen der Recordset-Objekte im Dokument-Memberfunktionen übergeben Sie einen Zeiger auf des Dokuments `CDatabase` Objekt. Dies ordnet jeder Recordset mit ihrer Datenquelle. Das Datenbankobjekt ist in der Regel zerstört, wenn das Dokument geschlossen wird. Recordset-Objekte werden in der Regel zerstört werden, wenn den Bereich einer Funktion zu beenden.  
  
##  <a name="_core_other_factors"></a>Andere Faktoren  
 Formularbasierte Anwendungen häufig keine Verwendung für das Framework Dokument Serialisierungsmechanismus verwenden Grund sollten Sie zu entfernen, deaktivieren oder Ersetzen der `New` und **öffnen** Befehle auf den **Datei**Menü. Finden Sie im Artikel [Serialisierung: Serialisierung im Vergleich. Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Möchten Sie möglicherweise auch Stellen verwenden, die viele Benutzeroberfläche Möglichkeiten, die das Framework unterstützt werden. Beispielsweise können Sie mehrere `CRecordView` Objekte in einem Splitterfenster kann mehrere Recordsets in verschiedenen öffnen, mehrere Document Interface (MDI) untergeordnete Fenster und So weiter.  
  
 Möglicherweise Drucken des Inhalts in der Ansicht implementieren möchten, sei es implementiert ein Formular mit `CRecordView` oder etwas anderes. Abgeleitete Klassen `CFormView`, `CRecordView` Drucken nicht unterstützt, aber Sie können überschreibt die `OnPrint` Memberfunktion Drucken zulässig. Weitere Informationen finden Sie in der Klasse [CFormView](../mfc/reference/cformview-class.md).  
  
 Sie möchten möglicherweise keine Dokumente und Ansichten überhaupt nicht verwendet. In diesem Fall finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Datenbankklassen (.. / data/mfc-database-classes-odbc-and-dao.md)