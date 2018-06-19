---
title: 'MFC-ActiveX-Steuerelemente: Weiterführende Themen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], error codes
- MFC ActiveX controls [MFC], accessing invisible dialog controls
- MFC ActiveX controls [MFC], advanced topics
- FireError method [MFC]
- MFC ActiveX controls [MFC], database classes
- MFC ActiveX controls [MFC], special keys
- PreTranslateMessage method [MFC]
- MFC ActiveX controls [MFC], parameterized property
- ThrowError method [MFC]
ms.assetid: e9e34abb-8e2d-461e-bb9c-a1aec5dcecbd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb451abc3aabe52d9aeffbc92f80df38f02e0b99
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33354017"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC-ActiveX-Steuerelemente: Weiterführende Themen
Dieser Artikel umfasst erweiterte Themen im Zusammenhang mit der Entwicklung von ActiveX-Steuerelemente. Dazu gehören:  
  
-   [Verwenden von Datenbankklassen in ActiveX-Steuerelementen](#_core_using_database_classes_in_activex_controls)  
  
-   [Implementieren einer parametrisierten Eigenschaft](#_core_implementing_a_parameterized_property)  
  
-   [Behandeln von Fehlern in das ActiveX-Steuerelement](#_core_handling_errors_in_your_activex_control)  
  
-   [Behandlung von Sondertasten im Steuerelement](#_core_handling_special_keys_in_your_control)  
  
-   [Beim Zugriff auf Dialogfeld-Steuerelemente, die zur Laufzeit nicht sichtbar sind](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> Verwenden von Datenbankklassen in ActiveX-Steuerelementen  
 Da die ActiveX-Steuerelementklassen Teil der Klassenbibliothek sind, können Sie anwenden, die gleichen Prozeduren und Regeln für die Verwendung von Datenbankklassen in einer standard-MFC-Anwendung für die Entwicklung von ActiveX-Steuerelemente, die MFC-Datenbankklassen verwendet werden.  
  
 Eine allgemeine Übersicht über den MFC-Datenbankklassen finden Sie unter [MFC-Datenbankklassen (ODBC und DAO)](../data/mfc-database-classes-odbc-and-dao.md). Der Artikel beschreibt die MFC-ODBC-Klassen und der MFC-DAO-Klassen und leitet Sie zu ausführlicheren Details auf.  
  
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützt nicht DAO (obwohl die DAO-Klassen enthalten sind, und Sie weiterhin verwenden können,). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-programming.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO verwenden, in die Verwaltung bereits vorhandener Anwendungen.  
  
##  <a name="_core_implementing_a_parameterized_property"></a> Implementieren einer parametrisierten Eigenschaft  
 Eine parametrisierte Eigenschaft (eine Eigenschaftsarray bezeichnet) ist eine Methode zum Verfügbarmachen von eine homogene Auflistung von Werten als eine einzelne Eigenschaft des Steuerelements. Sie können z. B. eine parametrisierte Eigenschaft verwenden, um ein Array oder ein Wörterbuch als Eigenschaft verfügbar zu machen. In Visual Basic wird eine solche Eigenschaft mithilfe der Arraynotation zugegriffen:  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 Verwenden Sie den Assistenten zum Hinzufügen eine parametrisierte Eigenschaft implementiert. Den Assistenten zum Hinzufügen einer Eigenschaft implementiert die Eigenschaft, indem ein Klammernpaar Get/Set-Funktionen, mit denen die Benutzer des Steuerelements auf die Eigenschaft, die mithilfe der oben genannten Notation zugreifen können oder in die üblich Art und Weise hinzugefügt.  
  
 Ähnlich wie Methoden und Eigenschaften, die parametrisierte Eigenschaften haben auch eine Grenze für die Anzahl der zulässigen Parameter. Im Fall von parametrisierten Eigenschaften liegt die Beschränkung 15 Parameter (mit einem Parameter, die zum Speichern des Eigenschaftswerts reserviert).  
  
 Das folgende Verfahren fügt eine parametrisierte Eigenschaft mit dem Namen Array, das als zweidimensionales Array von ganzen Zahlen zugegriffen werden kann.  
  
#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Hinzufügen eine parametrisierte Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
5.  In der **Eigenschaftsname** geben `Array`.  
  
6.  In der **Eigenschaftentyp** wählen Sie im **kurze**.  
  
7.  Für **Implementierung** Typ, klicken Sie auf **Get/Set-Methoden**.  
  
8.  In der **Get-Funktion** und **Set-Funktion** Felder, geben Sie eindeutige Namen für die Get- und Set-Funktion, oder übernehmen Sie den Standardnamen.  
  
9. Fügen Sie einen Parameter namens `row` (Typ `short`) unter Verwendung der **Parametername** und **Parametertyp** Steuerelemente.  
  
10. Fügen Sie einen zweiten Parameter namens `column` (Typ `short`).  
  
11. Klicken Sie auf **Fertig stellen**.  
  
### <a name="changes-made-by-the-add-property-wizard"></a>Änderungen, die durch die Eigenschaft Assistent zum Hinzufügen von  
 Wenn Sie eine benutzerdefinierte Eigenschaft hinzufügen, nimmt der Assistent zum Hinzufügen von Eigenschaften Änderungen an der Control-Klasse-Header (. H) und die Implementierung (. CPP)-Dateien.  
  
 Die folgenden Zeilen werden der Control-Klasse hinzugefügt. H-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]  
  
 Dieser Code deklariert zwei aufgerufenen Funktionen `GetArray` und `SetArray` , mit denen Benutzer eine bestimmte Zeile und Spalte anfordern, beim Zugriff auf die Eigenschaft.  
  
 Darüber hinaus den Assistenten zum Hinzufügen einer Eigenschaft hinzugefügt die folgenden Zeilen Dispatchzuordnung des Steuerelements befindet sich in der Implementierung des Steuerelements-Klasse (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 Schließlich die Implementierungen der `GetArray` und `SetArray` Funktionen wurden hinzugefügt, bis zum Ende der. CPP-Datei. In den meisten Fällen ändern Sie die Get-Funktion, um den Wert der Eigenschaft zurück. Die Set-Funktion wird in der Regel Code enthalten, die entweder vor oder nach der eigenschaftenänderungen ausführen soll.  
  
 Für diese Eigenschaft sind aussagekräftig sind, konnten Sie eine zweidimensionales Array-Membervariable in der Control-Klasse des Typs deklarieren **kurze**, um Werte für die parametrisierte Eigenschaft zu speichern. Sie könnten dann ändern Sie die Get-Funktion, um die in der richtigen Zeile und Spalte gespeicherte Wert zurückzugeben, wie von den Parametern angegeben und ändern Sie die Set-Funktion zum Aktualisieren des Werts, der die Zeilen- und Parameter verweist.  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> Behandeln von Fehlern in das ActiveX-Steuerelement  
 Wenn es sich bei Auftreten von Fehlern im Steuerelement auftreten, müssen Sie möglicherweise den Fehler an den Steuerelementcontainer senden. Es gibt zwei Methoden zur Meldung von Fehlern, abhängig von der Situation, in der der Fehler auftritt. Wenn der Fehler auftritt, innerhalb einer Eigenschaft abzurufen, oder Set-Funktion, oder in der Implementierung einer Methode des OLE-Automatisierung, sollte das Steuerelement aufrufen [ThrowError](../mfc/reference/colecontrol-class.md#throwerror), welche Signale für den Benutzer des Steuerelements, das ein Fehler aufgetreten ist. Wenn der Fehler zu einem anderen Zeitpunkt auftritt, sollte das Steuerelement aufrufen [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror), die ein vordefinierten Error-Ereignis auslöst.  
  
 Um die Art des Fehlers anzugeben, der aufgetreten ist, muss das Steuerelement übergeben ein Fehlercodes an `ThrowError` oder `FireError`. Ein Fehlercode ist ein OLE-Statuscode, einen 32-Bit-Wert besitzt. Wenn möglich, wählen Sie einen Fehlercode aus den Standardsatz von Codes, die in der Headerdatei OLECTL ein. H-Headerdatei. In der folgenden Tabelle werden diese Codes zusammengefasst.  
  
### <a name="activex-control-error-codes"></a>ActiveX-Steuerelementfehlercodes  
  
|Fehler|Beschreibung|  
|-----------|-----------------|  
|**CTL_E_ILLEGALFUNCTIONCALL**|Ungültiger Funktionsaufruf|  
|**CTL_E_OVERFLOW**|Überlauf|  
|**CTL_E_OUTOFMEMORY**|Nicht genügend Arbeitsspeicher|  
|**CTL_E_DIVISIONBYZERO**|Division durch 0 (null)|  
|**CTL_E_OUTOFSTRINGSPACE**|Nicht genügend Zeichenfolgenspeicher|  
|**CTL_E_OUTOFSTACKSPACE**|Nicht genügend Stapelspeicher|  
|**CTL_E_BADFILENAMEORNUMBER**|Der Dateiname oder die Zahl ist ungültig.|  
|**CTL_E_FILENOTFOUND**|Datei wurde nicht gefunden.|  
|**CTL_E_BADFILEMODE**|Fehlerhafter Dateimodus.|  
|**CTL_E_FILEALREADYOPEN**|Die Datei ist bereits geöffnet.|  
|**CTL_E_DEVICEIOERROR**|Geräte-E/A-Fehler|  
|**CTL_E_FILEALREADYEXISTS**|Datei bereits vorhanden|  
|**CTL_E_BADRECORDLENGTH**|Ungültige Datensatzlänge.|  
|**CTL_E_DISKFULL**|Der Datenträger ist voll|  
|**CTL_E_BADRECORDNUMBER**|Ungültige Datensatznummer|  
|**CTL_E_BADFILENAME**|Ungültiger Dateiname|  
|**CTL_E_TOOMANYFILES**|Zu viele Dateien|  
|**CTL_E_DEVICEUNAVAILABLE**|Das Gerät ist nicht verfügbar|  
|**CTL_E_PERMISSIONDENIED**|Berechtigung verweigert|  
|**CTL_E_DISKNOTREADY**|Das Laufwerk ist nicht bereit|  
|**CTL_E_PATHFILEACCESSERROR**|Pfad-/Dateizugriffsfehler|  
|**CTL_E_PATHNOTFOUND**|Der Pfad wurde nicht gefunden|  
|**CTL_E_INVALIDPATTERNSTRING**|Ungültige Musterzeichenfolge|  
|**CTL_E_INVALIDUSEOFNULL**|Ungültige Verwendung von NULL|  
|**CTL_E_INVALIDFILEFORMAT**|Ungültiges Dateiformat|  
|**CTL_E_INVALIDPROPERTYVALUE**|Ungültiger Eigenschaftswert|  
|**CTL_E_INVALIDPROPERTYARRAYINDEX**|Ungültiger Eigenschaftenarrayindex.|  
|**CTL_E_SETNOTSUPPORTEDATRUNTIME**|"Set" wird zur Laufzeit nicht unterstützt|  
|**CTL_E_SETNOTSUPPORTED**|"Set" wird nicht unterstützt (schreibgeschützte Eigenschaft)|  
|**CTL_E_NEEDPROPERTYARRAYINDEX**|Ein Eigenschaftenarrayindex wird benötigt|  
|**CTL_E_SETNOTPERMITTED**|"Set" ist unzulässig.|  
|**CTL_E_GETNOTSUPPORTEDATRUNTIME**|'Get' wird zur Laufzeit nicht unterstützt.|  
|**CTL_E_GETNOTSUPPORTED**|'Get' wird nicht unterstützt (lesegeschützte Eigenschaft).|  
|**CTL_E_PROPERTYNOTFOUND**|Die Eigenschaft wurde nicht gefunden|  
|**CTL_E_INVALIDCLIPBOARDFORMAT**|Ungültige Zwischenablageformat|  
|**CTL_E_INVALIDPICTURE**|Ungültiges Bild|  
|**CTL_E_PRINTERERROR**|Druckerfehler|  
|**CTL_E_CANTSAVEFILETOTEMP**|Datei kann nicht in TEMP gespeichert werden.|  
|**CTL_E_SEARCHTEXTNOTFOUND**|Suchtext wurde nicht gefunden|  
|**CTL_E_REPLACEMENTSTOOLONG**|Die Ersetzungen sind zu lang|  
  
 Verwenden Sie bei Bedarf die **CUSTOM_CTL_SCODE** Makro, um eine benutzerdefinierte Fehlercode für eine Bedingung, die nicht behandelt wird von einer der standard-Codes zu definieren. Der Parameter für dieses Makro muss eine ganze Zahl zwischen 1000 und 32767 liegen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 Wenn Sie ein ActiveX-Steuerelement, um ein vorhandenes VBX-Steuerelement ersetzen erstellen, definieren Sie die ActiveX-steuerelementfehlercodes mit den gleichen numerischen Werten, die das VBX-Steuerelement verwendet, um sicherzustellen, dass die Fehlercodes kompatibel sind.  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> Behandlung von Sondertasten im Steuerelement  
 In einigen Fällen möchten Sie möglicherweise bestimmte Tastenkombinationen auf besondere Weise behandelt; Einfügen eine neue Zeile, wenn die EINGABETASTE gedrückt wird, in einem mehrzeiligen Textfeld Steuerelement oder Wechseln zwischen einer Gruppe von z. B. gesteuert wird, wenn eine direktionale gedrückt.  
  
 Wenn die Basisklasse des ActiveX-Steuerelements ist `COleControl`, können Sie überschreiben [CWnd:: PreTranslateMessage](../mfc/reference/cwnd-class.md#pretranslatemessage) Nachrichten zu verarbeiten, bevor der Container diese verarbeitet. Wenn Sie diese Technik verwenden, stets **"true"** , wenn Sie die Nachricht, in der Überschreibung der behandeln `PreTranslateMessage`.  
  
 Das folgende Codebeispiel veranschaulicht eine mögliche Verfahren zur Verarbeitung von Nachrichten im Zusammenhang mit der direktionalen Schlüssel.  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 Weitere Informationen zur Behandlung von Tastaturschnittstellen für ein ActiveX-Steuerelement finden Sie unter der ActiveX-SDK-Dokumentation.  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> Beim Zugriff auf Dialogfeld-Steuerelemente, die zur Laufzeit nicht sichtbar sind  
 Sie können die Dialogfeld-Steuerelemente erstellen, die keine Benutzeroberfläche und zur Laufzeit nicht sichtbar sind. Wenn Sie einer Dialogfeld und Verwenden einer unsichtbar zur Laufzeit ActiveX-Steuerelement hinzufügen [GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem) für den Zugriff auf das Steuerelement, das Steuerelement funktioniert nicht ordnungsgemäß. Stattdessen sollten Sie verwenden eine der folgenden Methoden ein Objekt abgerufen, die das Steuerelement darstellt:  
  
-   Wählen Sie die Variable Assistenten zum Hinzufügen, mit **Steuerelementvariable** und wählen Sie dann auf das Steuerelement-ID. Geben Sie einen Member Variablennamen ein, und wählen Sie das Steuerelement-Wrapperklasse als die **Steuerelementtyp**.  
  
     - oder -   
  
-   Deklarieren einer lokalen Variablen und die Unterklasse wie das Dialogfeldelement. Fügen Sie Code, der die folgenden ähnelt (`CMyCtrl` ist die Wrapperklasse `IDC_MYCTRL1` ist das Steuerelement-ID):  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

