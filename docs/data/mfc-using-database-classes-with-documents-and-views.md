---
title: "MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordView-Klasse, Verwenden in Datenbankanwendungen"
  - "CDaoRecordView-Klasse, Verwenden in Datenbankformularen"
  - "CRecordView-Klasse, Verwenden in Datenbankformularen"
  - "DAO [C++], Formulare in Datenbankanwendungen"
  - "DAO-Recordsets [C++]"
  - "DAO-Recordsets [C++], Dokumente und Ansichten"
  - "Datenbankanwendungen [C++], Formulare"
  - "Datenbankklassen [C++], MFC"
  - "Dokument-/Ansichtsarchitektur [C++], In Datenbanken"
  - "Dokumente [C++], Datenbankanwendungen"
  - "Formulare [C++], Datenbankanwendungen"
  - "ODBC [C++], Formulare"
  - "ODBC-Recordsets [C++], Dokumente und Ansichten"
  - "Datensatzansichten [C++], Formularbasierte Anwendungen"
  - "Recordsets [C++], Dokumente und Ansichten"
  - "Ansichten [C++], Datenbankanwendungen"
ms.assetid: 83979974-fc63-46ac-b162-e8403a572e2c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die MFC\-Datenbankklassen \(DAO oder ODBC\) mit oder ohne Dokument\-\/Ansichtarchitektur verwenden.  Der Schwerpunkt dieses Themas liegt auf dem Arbeiten mit Dokumenten und Ansichten.  Er behandelt folgende Themen:  
  
-   [Erstellen einer formularbasierten Anwendung](#_core_writing_a_form.2d.based_application) mithilfe eines `CRecordView`\-Objekts oder eines `CDaoRecordView`\-Objekts als Hauptansicht im Dokument.  
  
-   [Verwenden von Recordsets in Dokumenten und Ansichten](#_core_using_recordsets_in_documents_and_views).  
  
-   [Andere Faktoren](#_core_other_factors).  
  
 Alternativen finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
##  <a name="_core_writing_a_form.2d.based_application"></a> Erstellen einer formularbasierten Anwendung  
 Viele Datenzugriffsanwendungen basieren auf Formularen.  Die Benutzeroberfläche besteht aus einem Formular, das Steuerelemente enthält, in denen der Benutzer Daten überprüft, eingibt oder bearbeitet.  Verwenden Sie die CRecordView\-Klasse oder die CDaoRecordView\-Klasse, um Ihre Anwendung formularbasiert zu gestalten.  Wenn Sie den MFC\-Anwendungs\-Assistenten ausführen und auf der Seite **Datenbankunterstützung** den Clienttyp **ODBC** auswählen, verwendet das Projekt `CRecordView` als Ansichtsklasse.  Da die Assistenten DAO nicht mehr unterstützen, können Sie `CDaoRecordView` nur verwenden, wenn Sie eine manuelle Codierung vornehmen.  
  
 In einer formularbasierten Anwendung speichert jedes Datensatzansichtsobjekt einen Zeiger auf ein `CRecordset`\-Objekt oder ein `CDaoRecordset`\-Objekt.  Durch den Datensatzfeldaustausch \(RFX, Record Field Exchange\) der Grundstruktur werden Daten zwischen dem Recordset und der Datenquelle ausgetauscht.  Durch den Dialogdatenaustausch \(DDX, Dialog Data Exchange\) erfolgt eine Übertragung von Daten zwischen den Felddatenmembern des Recordset\-Objekts und den Steuerelementen des Formulars.  `CRecordView` und `CDaoRecordView` enthalten auch Standard\-Befehlsbehandlungsroutinen für die Navigation zwischen Datensätzen im Formular.  
  
 Informationen zum Erstellen formularbasierter Anwendungen mithilfe des Anwendungs\-Assistenten finden Sie in den Themen [Erstellen einer formularbasierten MFC\-Anwendung](../mfc/reference/creating-a-forms-based-mfc-application.md) und [Datenbankunterstützung, MFC\-Anwendungs\-Assistent](../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Eine umfassende Erläuterung zu Formularen finden Sie unter [Datensatzansichten](../data/record-views-mfc-data-access.md).  
  
##  <a name="_core_using_recordsets_in_documents_and_views"></a> Verwenden von Recordsets in Dokumenten und Ansichten  
 Viele einfache formularbasierte Anwendungen benötigen keine "Dokumente."  Wenn die Anwendung komplexer ist, wird häufig ein Dokument als Proxy für die Datenbank verwendet, in dem dann ein `CDatabase`\-Objekt oder ein `CDaoDatabase`\-Objekt gespeichert wird, das die Verbindung zur Datenquelle herstellt.  Formularbasierte Anwendungen speichern in der Ansicht gewöhnlich einen Zeiger auf ein Recordset\-Objekt.  Andere Datenbankanwendungsarten speichern Recordsets und `CDatabase`\-Objekte oder `CDaoDatabase`\-Objekte im Dokument.  Einige Einsatzmöglichkeiten für Dokumente in Datenbankanwendungen sind:  
  
-   Wenn Sie in einem lokalen Kontext auf ein Recordset zugreifen, erstellen Sie ein `CRecordset`\-Objekt oder `CDaoRecordset`\-Objekt nach Bedarf lokal in Memberfunktionen des Dokuments oder der Ansicht.  
  
     Deklarieren Sie ein Recordset\-Objekt als lokale Variable in einer Funktion.  Durch die Übergabe von **NULL** an den Konstruktor legt die Grundstruktur ein temporäres `CDatabase`\- oder `CDaoDatabase`\-Objekt an und öffnet es.  Alternativ können Sie auch einen Zeiger auf ein `CDatabase`\- oder `CDaoDatabase`\-Objekt übergeben.  Verwenden Sie das Recordset innerhalb der Funktion, und lassen Sie es beim Verlassen automatisch zerstören.  
  
     Wenn Sie **NULL** an den Recordset\-Konstruktor übergeben, verwendet die Grundstruktur zum Erstellen und Öffnen eines `CDatabase`\- oder `CDaoDatabase`\-Objekts Daten, die von der `GetDefaultConnect`\-Memberfunktion des Recordsets zurückgegeben werden.  Die Assistenten implementieren `GetDefaultConnect` automatisch.  
  
-   Betten Sie ein oder mehrere CRecordset\- oder CDaoRecordset\-Objekte in das Dokument ein, falls Sie während der Gültigkeitsdauer des Dokuments auf ein Recordset zugreifen.  
  
     Legen Sie die Recordset\-Objekte entweder beim Initialisieren des Dokuments oder erst bei Bedarf an.  Sie können eine Funktion schreiben, die einen Zeiger auf das Recordset zurückgibt, falls dieses bereits vorhanden ist, oder das Recordset andernfalls konstruiert und öffnet.  Schließen und löschen Sie ggf. das Recordset, bzw. legen Sie es neu an, oder rufen Sie die entsprechende Requery\-Memberfunktion auf, um die Datensätze zu aktualisieren.  
  
-   Falls Sie während der Gültigkeitsdauer des Dokuments auf eine Datenquelle zugreifen, betten Sie ein CDatabase\- oder ein CDaoDatabase\-Objekt ein, oder speichern Sie einen Zeiger auf ein CDatabase\- oder ein CDaoDatabase\-Objekt.  
  
     Das `CDatabase`\- bzw. das `CDaoDatabase`\-Objekt verwaltet eine Verbindung zur Datenquelle.  Das Objekt wird während des Anlegens des Dokuments automatisch konstruiert; Sie rufen seine **Open**\-Memberfunktion auf, wenn Sie das Dokument initialisieren.  Wenn Sie in Memberfunktionen des Dokuments Recordset\-Objekte konstruieren, übergeben Sie einen Zeiger an das `CDatabase`\- oder `CDaoDatabase`\-Objekt des Dokuments.  Dadurch wird jedes Recordset mit der entsprechenden Datenquelle verknüpft.  Das Datenbankobjekt wird normalerweise beim Schließen des Dokuments zerstört.  Die Recordset\-Objekte werden normalerweise zerstört, wenn der Gültigkeitsbereich einer Funktion verlassen wird.  
  
##  <a name="_core_other_factors"></a> Andere Faktoren  
 In formularbasierten Anwendungen gibt es oft keinen Bedarf für den Serialisierungsmechanismus des Dokuments, sodass Sie im Menü **Datei** die Befehle **Neu** und **Öffnen** entfernen, deaktivieren oder ersetzen können.  Informationen hierzu finden Sie im Artikel [Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Sie können auch die zahlreichen Möglichkeiten bezüglich der Benutzeroberfläche nutzen, die die Grundstruktur unterstützen kann.  Sie können beispielsweise mehrere `CRecordView`\- oder `CDaoRecordView`\-Objekte in einem unterteilten Fenster verwenden, mehrere Recordsets in verschiedenen untergeordneten MDI\-Fenstern \(MDI \- Multiple Document Interface\) öffnen usw.  
  
 Darüber hinaus können Sie den Ausdruck der in der Ansicht angezeigten Daten implementieren. Dabei kann es sich um ein mit `CRecordView` oder `CDaoRecordView` implementiertes Formular oder um etwas anderes handeln.  Von CFormView, CRecordView und CDaoRecordView abgeleitete Klassen unterstützen das Drucken nicht. Sie können jedoch die OnPrint\-Memberfunktion überschreiben und so das Drucken ermöglichen.  Weitere Informationen finden Sie in der Dokumentation der [CFormView](../mfc/reference/cformview-class.md)\-Klasse.  
  
 Möglicherweise möchten Sie weder Dokumente noch Ansichten verwenden.  Die in diesem Fall notwendigen Informationen finden Sie unter [MFC: Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## Siehe auch  
 [MFC\-Datenbankklassen \(ODBC und DAO\)](../data/mfc-database-classes-odbc-and-dao.md)