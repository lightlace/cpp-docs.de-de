---
title: "MFC-ActiveX-Steuerelemente: Weiterf&#252;hrende Themen"
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
  - "FireError-Methode"
  - "MFC-ActiveX-Steuerelemente, Zugreifen auf unsichtbare Dialogfeldsteuerelemente"
  - "MFC-ActiveX-Steuerelemente, Weiterführende Themen"
  - "MFC-ActiveX-Steuerelemente, Datenbankklassen"
  - "MFC-ActiveX-Steuerelemente, Fehlercodes"
  - "MFC-ActiveX-Steuerelemente, Parametrisierte Eigenschaften"
  - "MFC-ActiveX-Steuerelemente, Sondertasten"
  - "PreTranslateMessage-Methode"
  - "ThrowError-Methode"
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Weiterf&#252;hrende Themen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel enthält die erweiterten Themen, die zur Entwicklung von ActiveX\-Steuerelementen verknüpft werden.  Dazu gehören:  
  
-   [Verwenden von Datenbankklassen in ActiveX\-Steuerelemente](#_core_using_database_classes_in_activex_controls)  
  
-   [Implementieren einer parametrisierten Eigenschaft](#_core_implementing_a_parameterized_property)  
  
-   [Fehlerbehandlung im ActiveX\-Steuerelement](#_core_handling_errors_in_your_activex_control)  
  
-   [Behandeln von Special\-Tasten im Steuerelement](#_core_handling_special_keys_in_your_control)  
  
-   [Klicken Sie Dialogfeld\-Kontrollen zugreifen, die zur Laufzeit nicht sichtbar sind](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> Verwenden von Datenbankklassen in ActiveX\-Steuerelemente  
 Da die ActiveX\-Steuerelement\-Klassen Teil der Klassenbibliothek sind, können Sie die gleichen Verfahren und Regeln für die Verwendung der Datenbankklassen in einer Standard\-MFC\-Anwendung auf die Entwicklung der ActiveX\-Steuerelemente verwenden, die die MFC\-Datenbankklassen verwenden.  
  
 Eine allgemeine Übersicht der MFC\-Datenbankklassen, finden Sie unter [MFC\-Datenbankklassen \(DAO und ODBC\)](../data/mfc-database-classes-odbc-and-dao.md).  Der Artikel stellt die MFC\-ODBC\- und MFC\-DAO\-Klassen vor und verweist Sie auf Details zu jedem.  
  
> [!NOTE]
>  Ab Visual C\+\+ .NET wird DAO von der Visual C\+\+\-Umgebung und den Assistenten nicht mehr unterstützt. \(Die DAO\-Klassen sind allerdings weiterhin enthalten und können verwendet werden.\)  Microsoft empfiehlt, dass Sie [OLE DB\-Vorlagen](../data/oledb/ole-db-programming.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte verwenden.  DAO sollte lediglich zur Verwaltung bereits bestehender Anwendungen eingesetzt werden.  
  
##  <a name="_core_implementing_a_parameterized_property"></a> Implementieren einer parametrisierten Eigenschaft  
 Eine parametrisierte Eigenschaft \(gelegentlich aufgerufen ein Eigenschaftenarray\) ist eine Methode für das Verfügbarmachen einer homogenen Auflistung Werte als einzelne Eigenschaft des Steuerelements.  Beispielsweise können Sie eine parametrisierte Eigenschaft verwenden, um ein Array oder ein Wörterbuch als Eigenschaft verfügbar machen.  In Visual Basic wird auf eine solche Eigenschaft mithilfe der Arraynotation zugegriffen:  
  
 [!CODE [NVC_MFC_AxVb#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxVb#1)]  
  
 Verwenden Sie den Assistenten zum Hinzufügen von Eigenschaften, um eine parametrisierte Eigenschaft zu implementieren.  Der Assistent zum Hinzufügen von Eigenschaften implementiert die Eigenschaft, indem ein Paar Get\/Set\-Funktionen hinzufügen, die dem Steuerelementbenutzer ermöglichen, auf die Eigenschaft mithilfe der oben erwähnten Notation oder in der Standardweise zuzugreifen.  
  
 Ähnlich den Methoden und Eigenschaften, über parametrisierte Eigenschaften auch eine Begrenzung für die Anzahl der zulässigen Parameter.  Im Fall von parametrisierten Eigenschaften ist die Grenze 15 Parameter \(wenn ein Parameter zum Speichern des Eigenschaftswerts, reserviert ist\).  
  
 Im folgenden Verfahren wird eine parametrisierte Eigenschaft hinzu, aufgerufen Array, auf das als zweidimensionales Array von Ganzzahlen zugegriffen werden kann.  
  
#### So fügen Sie eine parametrisierte Eigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
5.  Im Feld **Eigenschaftenname** geben Sie `Array` ein.  
  
6.  Im Feld **Eigenschaftentyp** die Option **short** aus.  
  
7.  Für **Implementierung**\-Typ auf **Get\/Set\-Methoden**.  
  
8.  In den Feldern **Get\-Funktion**  und **Set\-Funktion** geben Sie eindeutigen Namen für das abrufen und festlegen Funktionen oder übernehmen die Standardnamen ein.  
  
9. Fügen Sie einen Parameter hinzu, die `row`\-Typ \( `short`\), mit **Parametername** und **Parametertyp** \-Steuerelemente.  
  
10. Fügen Sie einen zweiten Parameter hinzu, der `column`\-Typ \( `short`\) aufgerufen wird.  
  
11. Klicken Sie auf **Fertig stellen**.  
  
### Änderungen vom Assistenten zum Hinzufügen von Eigenschaften  
 Wenn Sie eine benutzerdefinierte Eigenschaft hinzugefügt, wird der Assistent zum Hinzufügen von Eigenschaften Änderungen an der Steuerelementklassenkopfzeile vor \(.H\) und Dateien die Implementierungsdatei \(.CPP\).  
  
 Die folgenden Zeilen werden der Steuerelementklasse hinzugefügt. Außerdem:  
  
 [!CODE [NVC_MFC_AxUI#35](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#35)]  
  
 Dieser Code deklariert zwei Funktionen aufgerufen `GetArray` und `SetArray`, die dem Benutzer ermöglichen, eine bestimmte Zeile und eine Spalte zu anfordern, wenn sie auf die Eigenschaft zugreifen.  
  
 Darüber hinaus fügt der Assistent zum Hinzufügen von Eigenschaften die folgenden Zeilen der Steuerdispatchzuordnung hinzu, in der Steuerelementklasse \(.CPP\):  
  
 [!CODE [NVC_MFC_AxUI#36](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#36)]  
  
 Schließlich werden Implementierungen die `GetArray` und `SetArray` Features zum Ende der CPP\-Datei hinzugefügt.  In den meisten Fällen ändern Sie die Abrufensfunktion, um den Wert der Eigenschaft zurückgegeben.  Die festgelegte Funktion enthält normalerweise Code, der ausgeführt werden soll, einen, vor oder nach der Eigenschaft ändert.  
  
 Damit diese Eigenschaft ist hilfreich, können Sie eine Membervariable des zweidimensionalen Arrays in der Steuerelementklasse, des Typs **short**, den mittels für die parametrisierte Eigenschaft deklarieren.  Sie können die Abrufensfunktion dann ändern, um den Wert zurückzugeben, der an der richtigen Zeile und in der Spalte gespeichert wurde, wie durch die Parameter angegeben und die festgelegte Funktion, um den Wert zu aktualisieren, der durch die Zeilen\- und Spaltenparameter verwiesen wurde.  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> Fehlerbehandlung im ActiveX\-Steuerelement  
 Wenn Fehlerzustände im Steuerelement auftreten, müssen Sie möglicherweise den Fehler den Steuerelementcontainer melden.  Es gibt zwei Methoden für das Melden von Fehlern, abhängig von der Situation, in der der Fehler auftritt.  Wenn der Fehler in einer Eigenschaft auftritt, get oder set Funktion fest, oder in der Implementierung einer OLE\-Automatisierungs\-Methode, sollte das Steuerelement die [COleControl::ThrowError](../Topic/COleControl::ThrowError.md) aufrufen, das z Steuerelementbenutzer signalisiert, dass ein Fehler aufgetreten ist.  Wenn der Fehler zu jeder anderen Zeitpunkt auftritt, sollte das Steuerelement die [COleControl::FireError](../Topic/COleControl::FireError.md) aufrufen, ein vordefiniertes Fehlerereignis auslöst.  
  
 Um der Fehlertyp anzugeben die aufgetreten ist, muss das Steuerelement einen Fehlercode an `ThrowError` oder `FireError` übergeben.  Ein Fehlercode ist ein OLE\-Statuscode, der einen 32\-Bit\-Wert hat.  Wenn möglich, wählen Sie einen Fehlercode aus Standardsatz mit Codes aus, die in der OLECTL.H\-Headerdatei definiert werden.  In der folgenden Tabelle werden diese Code zusammen.  
  
### ActiveX\-Steuerelement\-Fehlercodes  
  
|Fehler|**Beschreibung**|  
|------------|----------------------|  
|**CTL\_E\_ILLEGALFUNCTIONCALL**|Ungültiger Funktionsaufruf|  
|**CTL\_E\_OVERFLOW**|Overflow|  
|**CTL\_E\_OUTOFMEMORY**|Nicht genügend Arbeitsspeicher|  
|**CTL\_E\_DIVISIONBYZERO**|Division durch Null|  
|**CTL\_E\_OUTOFSTRINGSPACE**|Aus Zeichenfolgenleerzeichen Auschecken|  
|**CTL\_E\_OUTOFSTACKSPACE**|Aus Stapelspeicher Auschecken|  
|**CTL\_E\_BADFILENAMEORNUMBER**|Ungültiger Dateiname oder Zahl|  
|**CTL\_E\_FILENOTFOUND**|Die Datei wurde nicht gefunden.|  
|**CTL\_E\_BADFILEMODE**|Ungültiger Modus Alle Dateien|  
|**CTL\_E\_FILEALREADYOPEN**|Datei bereits geöffnet|  
|**CTL\_E\_DEVICEIOERROR**|Geräten\-E\/A\-Fehler|  
|**CTL\_E\_FILEALREADYEXISTS**|Datei ist bereits vorhanden|  
|**CTL\_E\_BADRECORDLENGTH**|Länge des schlechten Aufruf|  
|**CTL\_E\_DISKFULL**|Datenträger ist voll|  
|**CTL\_E\_BADRECORDNUMBER**|Nummer des schlechten Aufruf|  
|**CTL\_E\_BADFILENAME**|Ungültiger Dateiname|  
|**CTL\_E\_TOOMANYFILES**|Zu viele Dateien|  
|**CTL\_E\_DEVICEUNAVAILABLE**|Gerät nicht verfügbar|  
|**CTL\_E\_PERMISSIONDENIED**|Berechtigung verweigert|  
|**CTL\_E\_DISKNOTREADY**|Datenträger nicht bereit|  
|**CTL\_E\_PATHFILEACCESSERROR**|Pfad\/Dateizugriffsfehler|  
|**CTL\_E\_PATHNOTFOUND**|Pfad nicht gefunden|  
|**CTL\_E\_INVALIDPATTERNSTRING**|Ungültige Musterzeichenfolge|  
|**CTL\_E\_INVALIDUSEOFNULL**|Ungültiger Verwendung von NULL|  
|**CTL\_E\_INVALIDFILEFORMAT**|Ungültiges Dateiformat|  
|**CTL\_E\_INVALIDPROPERTYVALUE**|Ungültiger Eigenschaftswert|  
|**CTL\_E\_INVALIDPROPERTYARRAYINDEX**|Ungültiger Eigenschaftenarrayindex|  
|**CTL\_E\_SETNOTSUPPORTEDATRUNTIME**|Satz nicht zur Laufzeit unterstützt|  
|**CTL\_E\_SETNOTSUPPORTED**|Satz nicht unterstützt \(schreibgeschützte Eigenschaft\)|  
|**CTL\_E\_NEEDPROPERTYARRAYINDEX**|Anforderungseigenschaften\-Arrayindex|  
|**CTL\_E\_SETNOTPERMITTED**|Satz nicht zulässig|  
|**CTL\_E\_GETNOTSUPPORTEDATRUNTIME**|Rufen Sie nicht unterstütztes zur Laufzeit ab|  
|**CTL\_E\_GETNOTSUPPORTED**|Rufen Sie nicht unterstütztes ab \(lesegeschützte Eigenschaft\)|  
|**CTL\_E\_PROPERTYNOTFOUND**|Eigenschaft nicht gefunden|  
|**CTL\_E\_INVALIDCLIPBOARDFORMAT**|Ungültiges Zwischenablageformat|  
|**CTL\_E\_INVALIDPICTURE**|Ungültiges Bild|  
|**CTL\_E\_PRINTERERROR**|Druckerfehler|  
|**CTL\_E\_CANTSAVEFILETOTEMP**|Kann Datei zu speichern TEMP|  
|**CTL\_E\_SEARCHTEXTNOTFOUND**|Suchen Sie den gesuchten Text|  
|**CTL\_E\_REPLACEMENTSTOOLONG**|jeweiligen Ersatz zu lang|  
  
 Falls nötig verwenden Sie das Makro **CUSTOM\_CTL\_SCODE**, um einen benutzerdefinierten Fehlercode für eine Bedingung zu definieren, die nicht durch einen der Standardcodes abgedeckt wird.  Der Parameter für dieses Makros sollte eine ganze Zahl zwischen 1000 und 32767 sein, liegen.  Beispiel:  
  
 [!CODE [NVC_MFC_AxUI#37](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#37)]  
  
 Wenn Sie ein ActiveX\-Steuerelement erstellen, um ein vorhandenes VBX\-Steuerelement zu ersetzen, definieren Sie die ActiveX\-Steuerelement\-Fehlercodes mit den gleichen numerischen Werte, die das VBX\-Steuerelement verwendet, um sicherzustellen, dass die Fehlercodes kompatibel sind.  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> Behandeln von Special\-Tasten im Steuerelement  
 In einigen Fällen möchten Sie möglicherweise bestimmte Tastenkombinationen auf eine besondere Weise behandeln; beispielsweise fügen Sie eine neue Zeile ein, wenn der EINGABETASTE einem mehrzeiligen Textfeld\-Steuerelement oder eine Verschiebung zwischen einer Gruppe Bearbeitungssteuerelementen gedrückt wird, als eine gerichtetes Schlüssel\-ID geklickt hat.  
  
 Wenn die Basisklasse des ActiveX\-Steuerelements `COleControl` handelt, kann [CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) überschreiben, um Meldungen verarbeiten, bevor der Container sie verarbeitet.  Bei diesem Verfahren wird immer **TRUE** zurückgegeben, wenn Sie die Meldung in der Überschreibung der `PreTranslateMessage` bearbeiten.  
  
 Das folgende Codebeispiel zeigt eine beliebige Weise der Behandlung aller Nachrichten, die den direktionalen Schlüssel verknüpft werden.  
  
 [!CODE [NVC_MFC_AxUI#38](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#38)]  
  
 Weitere Informationen über Behandlungstastaturschnittstellen für ein ActiveX\-Steuerelement, finden Sie die ActiveX\-SDK\-Dokumentation.  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> Klicken Sie Dialogfeld\-Kontrollen zugreifen, die zur Laufzeit nicht sichtbar sind  
 Sie können Dialogfeldkontrollen erstellen, die keine Benutzeroberfläche aufweisen und zur Laufzeit nicht sichtbar sind.  Wenn Sie eine während der Laufzeit unsichtbar ActiveX\-Steuerelement einem Dialogfeld hinzufügen und [CWnd::GetDlgItem](../Topic/CWnd::GetDlgItem.md) verwenden, um auf das Steuerelement zugreifen, funktioniert das Steuerelement nicht richtig.  Stattdessen sollten Sie eine der folgenden Techniken verwenden, um ein Objekt abzurufen, das das Steuerelement darstellt:  
  
-   Mit dem Assistenten zum Hinzufügen von Membervariablen Option **Steuerelementvariable** und die ID des Steuerelements aus  Geben Sie einen Membervariablennamen ein und wählen Sie die Wrapperklasse des Steuerelements als **Steuerelementtyp**.  
  
     \- oder \-  
  
-   Deklarieren Sie eine lokale und ordnen Sie als das Dialogfeldelement unter.  Fügen Sie Code ein, der dem folgenden ähnelt \(`CMyCtrl` ist die Wrapperklasse, `IDC_MYCTRL1` ist die ID des Steuerelements\):  
  
     [!CODE [NVC_MFC_AxCont#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#19)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)