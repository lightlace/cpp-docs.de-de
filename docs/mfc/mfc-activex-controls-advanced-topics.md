---
title: 'MFC-ActiveX-Steuerelemente: Weiterführende Themen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/12/2018
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
ms.openlocfilehash: fbebffa1bbec55e08cccafd387c44991ebe467ca
ms.sourcegitcommit: b4432d30f255f0cb58dce69cbc8cbcb9d44bc68b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45535238"
---
# <a name="mfc-activex-controls-advanced-topics"></a>MFC-ActiveX-Steuerelemente: Weiterführende Themen
Dieser Artikel behandelt die erweiterte Themen im Zusammenhang mit der Entwicklung von ActiveX-Steuerelemente. Dazu gehören:  
  
-   [Verwenden von Datenbankklassen in ActiveX-Steuerelementen](#_core_using_database_classes_in_activex_controls)  
  
-   [Implementieren eine parametrisierte Eigenschaft](#_core_implementing_a_parameterized_property)  
  
-   [Behandeln von Fehlern in das ActiveX-Steuerelement](#_core_handling_errors_in_your_activex_control)  
  
-   [Spezielle Schlüssel in das Steuerelement behandeln](#_core_handling_special_keys_in_your_control)  
  
-   [Zugriff auf Dialogfeld-Steuerelemente, die zur Laufzeit nicht sichtbar sind](#_core_accessing_dialog_controls_that_are_invisible_at_run_time)  

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen über moderne Technologien, die ActiveX Ersetzen eines finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).
  
##  <a name="_core_using_database_classes_in_activex_controls"></a> Verwenden von Datenbankklassen in ActiveX-Steuerelementen  
 Da die ActiveX-Steuerelementklassen der Class-Bibliothek angehören, können Sie anwenden, die gleichen Prozeduren und Regeln für die Verwendung von Datenbankklassen in einer standard-MFC-Anwendung mit der Entwicklung von ActiveX-Steuerelemente, die die MFC-Datenbankklassen verwendet werden.  
  
 Eine allgemeine Übersicht über die MFC-Datenbankklassen, finden Sie unter [MFC-Datenbankklassen (ODBC und DAO)](../data/mfc-database-classes-odbc-and-dao.md). Der Artikel beschreibt die MFC-ODBC-Klassen und der MFC-DAO-Klassen und leitet Sie zu weiteren Details an.  
  
> [!NOTE]
>  Die Visual C++-Umgebung und den Assistenten unterstützen DAO keine (obwohl die DAO-Klassen enthalten sind, und Sie können diese weiterhin verwenden). Microsoft empfiehlt die Verwendung von [OLE DB-Vorlagen](../data/oledb/ole-db-programming.md) oder [ODBC und MFC](../data/odbc/odbc-and-mfc.md) für neue Projekte. Sie sollten nur DAO Verwaltung bereits vorhandener Anwendungen verwenden.  
  
##  <a name="_core_implementing_a_parameterized_property"></a> Implementieren eine parametrisierte Eigenschaft  
 Eine parametrisierte Eigenschaft (manchmal eine Array-Eigenschaft genannt) ist eine Methode für eine homogene Auflistung von Werten als eine einzelne Eigenschaft des Steuerelements verfügbar zu machen. Sie können z. B. eine parametrisierte Eigenschaft verwenden, um ein Array oder ein Wörterbuch als Eigenschaft verfügbar zu machen. In Visual Basic ist eine solche Eigenschaft mithilfe der Arraynotation zugegriffen:  
  
 [!code-vb[NVC_MFC_AxVb#1](../mfc/codesnippet/visualbasic/mfc-activex-controls-advanced-topics_1.vb)]  
  
 Verwenden Sie den Assistenten zum Hinzufügen einer Eigenschaft, um eine parametrisierte Eigenschaft zu implementieren. Der Assistent zum Hinzufügen von Eigenschaften implementiert die Eigenschaft durch das Hinzufügen von ein Paar von Get/Set-Funktionen, mit die die Benutzer des Steuerelements auf die Eigenschaft, die mithilfe der oben genannten Notation zugreifen können oder die standardmäßige Art und Weise.  
  
 Ähnlich wie bei den Methoden und Eigenschaften, die parametrisierte Eigenschaften müssen auch eine Beschränkung der Anzahl der zulässigen Parameter. Im Fall von parametrisierten Eigenschaften liegt die Beschränkung 15 Parameter (mit einem Parameter, die zum Speichern des Eigenschaftswerts reserviert).  
  
 Das folgende Verfahren fügt eine parametrisierte Eigenschaft namens Array, das als ein zweidimensionales Array von ganzen Zahlen zugegriffen werden kann.  
  
#### <a name="to-add-a-parameterized-property-using-the-add-property-wizard"></a>Zum Hinzufügen einer parametrisierten Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
5.  In der **Eigenschaftennamen** geben `Array`.  
  
6.  In der **Eigenschaftentyp** Kontrollkästchen **kurze**.  
  
7.  Für **Implementierung** Typ, klicken Sie auf **Get/Set-Methoden**.  
  
8.  In der **Get-Funktion** und **Set-Funktion** Felder, geben Sie eindeutige Namen für die Get- und Set-Funktion, oder übernehmen Sie die Standardnamen.  
  
9. Fügen Sie einen Parameter namens *Zeile* (Typ *kurze*) unter Verwendung der **Parametername** und **Parametertyp** Steuerelemente.  
  
10. Fügen Sie einen zweiten Parameter wird aufgerufen, *Spalte* (Typ *kurze*).  
  
11. Klicken Sie auf **Fertig stellen**.  
  
### <a name="changes-made-by-the-add-property-wizard"></a>Änderungen durch die Eigenschaft Assistent zum Hinzufügen von  
 Wenn Sie eine benutzerdefinierte Eigenschaft hinzufügen, nimmt der Assistent zum Hinzufügen von Eigenschaften Änderungen an der Control-Header-Klasse (. H) und die Implementierung (. CPP)-Dateien.  
  
 Die Control-Klasse werden die folgenden Zeilen hinzugefügt. H-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#35](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_2.h)]  
  
 Dieser Code deklariert zwei aufgerufenen Funktionen `GetArray` und `SetArray` , bei denen der Benutzer zu einer bestimmten Zeile und Spalte angefordert wird, wenn die Eigenschaft zugreifen.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt außerdem die folgenden Zeilen an die Dispatch-steuerelementzuordnung, befindet sich in der Implementierung des Steuerelements-Klasse (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#36](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_3.cpp)]  
  
 Schließlich die Implementierungen der `GetArray` und `SetArray` Funktionen wurden hinzugefügt, bis zum Ende der. CPP-Datei. In den meisten Fällen ändern Sie die Get-Funktion, um den Wert der Eigenschaft zurückzugeben. Die Set-Funktion wird in der Regel Code enthalten, die entweder vor oder nach der Änderung der Eigenschaft ausführen soll.  
  
 Für diese Eigenschaft nützlich sein, Sie können eine zweidimensionales Array-Membervariable in die Control-Klasse des Typs deklarieren **kurze**, um Werte für die parametrisierte Eigenschaft zu speichern. Sie können die Get-Funktion, um den in der richtigen Zeile und der Spalte gespeicherten Wert zurück, wie durch die Parameter ändern und ändern Sie die Set-Funktion, um den Wert, der auf die verwiesen wird durch die Zeilen- und Parameter aktualisieren.  
  
##  <a name="_core_handling_errors_in_your_activex_control"></a> Behandeln von Fehlern in das ActiveX-Steuerelement  
 Wenn fehlerbedingungen im Steuerelement auftreten, müssen Sie möglicherweise den Fehler an den Steuerelementcontainer senden. Es gibt zwei Methoden zum Melden von Fehlern, je nach Situation, in der der Fehler aufgetreten. Wenn der Fehler auftritt, innerhalb einer Eigenschaft zu erhalten oder Set-Funktion, oder in der Implementierung einer Methode des OLE-Automatisierung, sollte das Steuerelement aufrufen [ThrowError](../mfc/reference/colecontrol-class.md#throwerror), welche signalisiert dem Benutzer des Steuerelements, die ein Fehler aufgetreten ist. Wenn der Fehler zu einem anderen Zeitpunkt auftritt, sollte das Steuerelement aufrufen [COleControl:: FireError](../mfc/reference/colecontrol-class.md#fireerror), die ein vordefinierten Error-Ereignis ausgelöst.  
  
 Um die Art des Fehlers anzugeben, der aufgetreten ist, muss das Steuerelement übergeben ein Fehlercodes an `ThrowError` oder `FireError`. Ein Fehlercode ist ein OLE-Statuscode, der einen 32-Bit-Wert hat. Wählen Sie aus den Standardsatz von Fehlercodes, die in der Headerdatei OLECTL einen Fehlercode, wenn möglich. H-Headerdatei. In der folgende Tabelle werden diese Codes zusammengefasst.  
  
### <a name="activex-control-error-codes"></a>ActiveX-Steuerelementfehlercodes  
  
|Fehler|Beschreibung|  
|-----------|-----------------|  
|CTL_E_ILLEGALFUNCTIONCALL|Ungültiger Funktionsaufruf|  
|CTL_E_OVERFLOW|Überlauf|  
|CTL_E_OUTOFMEMORY|Nicht genügend Arbeitsspeicher|  
|CTL_E_DIVISIONBYZERO|Division durch 0 (null)|  
|CTL_E_OUTOFSTRINGSPACE|Nicht genügend Zeichenfolgenspeicher|  
|CTL_E_OUTOFSTACKSPACE|Nicht genügend Stapelspeicher|  
|CTL_E_BADFILENAMEORNUMBER|Der Dateiname oder die Zahl ist ungültig.|  
|CTL_E_FILENOTFOUND|Die Datei wurde nicht gefunden.|  
|CTL_E_BADFILEMODE|Fehlerhafter Dateimodus.|  
|CTL_E_FILEALREADYOPEN|Die Datei ist bereits geöffnet.|  
|CTL_E_DEVICEIOERROR|Geräte-E/A-Fehler|  
|CTL_E_FILEALREADYEXISTS|Datei bereits vorhanden|  
|CTL_E_BADRECORDLENGTH|Ungültige Datensatzlänge.|  
|CTL_E_DISKFULL|Der Datenträger ist voll|  
|CTL_E_BADRECORDNUMBER|Ungültige Datensatznummer|  
|CTL_E_BADFILENAME|Ungültiger Dateiname|  
|CTL_E_TOOMANYFILES|Zu viele Dateien|  
|CTL_E_DEVICEUNAVAILABLE|Das Gerät ist nicht verfügbar|  
|CTL_E_PERMISSIONDENIED|Berechtigung verweigert|  
|CTL_E_DISKNOTREADY|Das Laufwerk ist nicht bereit|  
|CTL_E_PATHFILEACCESSERROR|Pfad-/Dateizugriffsfehler|  
|CTL_E_PATHNOTFOUND|Der Pfad wurde nicht gefunden|  
|CTL_E_INVALIDPATTERNSTRING|Ungültige Musterzeichenfolge|  
|CTL_E_INVALIDUSEOFNULL|Ungültige Verwendung von NULL|  
|CTL_E_INVALIDFILEFORMAT|Ungültiges Dateiformat|  
|CTL_E_INVALIDPROPERTYVALUE|Ungültiger Eigenschaftswert|  
|CTL_E_INVALIDPROPERTYARRAYINDEX|Ungültiger Eigenschaftenarrayindex|  
|CTL_E_SETNOTSUPPORTEDATRUNTIME|"Set" wird zur Laufzeit nicht unterstützt|  
|CTL_E_SETNOTSUPPORTED|"Set" wird nicht unterstützt (schreibgeschützte Eigenschaft)|  
|CTL_E_NEEDPROPERTYARRAYINDEX|Ein Eigenschaftenarrayindex wird benötigt|  
|CTL_E_SETNOTPERMITTED|"Set" ist unzulässig.|  
|CTL_E_GETNOTSUPPORTEDATRUNTIME|'Get' wird zur Laufzeit nicht unterstützt.|  
|CTL_E_GETNOTSUPPORTED|'Get' wird nicht unterstützt (lesegeschützte Eigenschaft).|  
|CTL_E_PROPERTYNOTFOUND|Die Eigenschaft wurde nicht gefunden|  
|CTL_E_INVALIDCLIPBOARDFORMAT|Ungültiges Zwischenablageformat.|  
|CTL_E_INVALIDPICTURE|Ungültiges Bild|  
|CTL_E_PRINTERERROR|Druckerfehler|  
|CTL_E_CANTSAVEFILETOTEMP|Datei kann nicht in TEMPORÄREN gespeichert werden.|  
|CTL_E_SEARCHTEXTNOTFOUND|Suchtext wurde nicht gefunden|  
|CTL_E_REPLACEMENTSTOOLONG|Die Ersetzungen sind zu lang|  
  
 Verwenden Sie bei Bedarf das CUSTOM_CTL_SCODE-Makro definieren Sie einen benutzerdefinierte Fehlercode für eine Bedingung, die nicht behandelt wird durch die standard-Codes. Der Parameter für dieses Makro muss eine ganze Zahl zwischen 1000 und 32767, inklusive. Zum Beispiel:  
  
 [!code-cpp[NVC_MFC_AxUI#37](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_4.cpp)]  
  
 Bei der Erstellung eines ActiveX-Steuerelements, um ein vorhandenes VBX-Steuerelement zu ersetzen, definieren Sie Ihr ActiveX-steuerelementfehlercodes mit den gleichen numerischen Werten, die das VBX-Steuerelement verwendet, um sicherzustellen, dass die Fehlercodes kompatibel sind.  
  
##  <a name="_core_handling_special_keys_in_your_control"></a> Spezielle Schlüssel in das Steuerelement behandeln  
 In einigen Fällen können Sie bestimmte Tastenkombinationen auf besondere Weise behandeln möchten; z. B. Insert, eine neue Zeile, wenn die EINGABETASTE gedrückt wird, in einem mehrzeiligen Textfeld-Steuerelements oder verschieben Sie zwischen einer Gruppe von bearbeiten, steuert, wenn ein direktionaler Schlüssel-ID, die gedrückt.  
  
 Ist die Basisklasse von ActiveX-Steuerelements `COleControl`, können Sie überschreiben [CWnd:: PreTranslateMessage](../mfc/reference/cwnd-class.md#pretranslatemessage) , Nachrichten zu verarbeiten, bevor der Container verarbeitet. Wenn Sie dieses Verfahren verwenden, immer zurückgegeben **"true"** verarbeitet die Nachricht in der Überschreibung der `PreTranslateMessage`.  
  
 Das folgende Codebeispiel veranschaulicht eine Möglichkeit, alle Nachrichten, die im Zusammenhang mit der direktionalen Schlüssel zu verarbeiten.  
  
 [!code-cpp[NVC_MFC_AxUI#38](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_5.cpp)]  
  
 Weitere Informationen zur Behandlung von Tastaturschnittstellen für ein ActiveX-Steuerelement finden Sie unter der ActiveX-SDK-Dokumentation.  
  
##  <a name="_core_accessing_dialog_controls_that_are_invisible_at_run_time"></a> Zugriff auf Dialogfeld-Steuerelemente, die zur Laufzeit nicht sichtbar sind  
 Sie können die Dialogfeld-Steuerelemente erstellen, die keine Benutzeroberfläche und zur Laufzeit nicht sichtbar sind. Wenn Sie ein unsichtbares zu einem Dialogfeld und die Verwendung zur Laufzeit ActiveX-Steuerelement hinzufügen [GetDlgItem](../mfc/reference/cwnd-class.md#getdlgitem) für den Zugriff auf das Steuerelement, das Steuerelement wird nicht ordnungsgemäß funktionieren. Stattdessen sollten Sie verwenden eine der folgenden Methoden auf um ein Objekt zu erhalten, die das Steuerelement darstellt:  
  
-   Wählen Sie die Variable Assistenten zum Hinzufügen, mit **Steuerelementvariable** und wählen Sie dann mit der ID des Steuerelements Geben Sie einen Member-Variable ein, und wählen Sie Wrapper-Klasse des Steuerelements als die **Steuerelementtyp**.  
  
     - oder -   
  
-   Deklarieren Sie eine lokale Variable und die Unterklasse, wie das Dialogfeldelement. Fügen Sie Code, der ähnlich wie die folgende (`CMyCtrl` ist die Wrapperklasse IDC_MYCTRL1 ist die ID des Steuerelements):  
  
     [!code-cpp[NVC_MFC_AxCont#19](../mfc/codesnippet/cpp/mfc-activex-controls-advanced-topics_6.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

