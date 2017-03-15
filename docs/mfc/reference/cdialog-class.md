---
title: CDialog-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDialog
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes, creating
- MFC dialog boxes, base class
- modeless dialog boxes, creating
- modeless dialog boxes, displaying
- CDialog class
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 0944d815e8aca591f2a09c09af60fa591a9b1a6d
ms.lasthandoff: 02/24/2017

---
# <a name="cdialog-class"></a>CDialog-Klasse
Die Basisklasse für die Anzeige von Dialogfeldern auf dem Bildschirm verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::CDialog](#cdialog)|Erstellt ein `CDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::Create](#create)|Initialisiert das `CDialog` Objekt. Erstellt ein modales Dialogfeld, und fügt es der `CDialog` Objekt.|  
|[CDialog::CreateIndirect](#createindirect)|Erstellt ein nicht modales Dialogfeld aus einer Vorlage im Dialogfeld im Speicher (nicht-Ressource-basiert).|  
|[Methode CDialog:: DoModal](#domodal)|Ruft ein modales Dialogfeld, und gibt anschließend.|  
|[CDialog::EndDialog](#enddialog)|Schließt ein modales Dialogfeld an.|  
|[CDialog::GetDefID](#getdefid)|Ruft die ID des Steuerelements pushbutton standardmäßig ein Dialogfeld ab.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Verschiebt den Fokus auf ein Steuerelement im angegebenen Dialogfeld im Dialogfeld.|  
|[DLGTEMPL](#initmodalindirect)|Erstellt ein modales Dialogfeld aus einer Vorlage im Dialogfeld im Speicher (nicht-Ressource-basiert). Die Parameter werden gespeichert, bis die Funktion `DoModal` aufgerufen wird.|  
|[CDialog::MapDialogRect](#mapdialogrect)|Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Bewegt den Fokus zum nächsten Steuerelement im Dialogfeld im Dialogfeld.|  
|[CDialog::](#oninitdialog)|Überschreiben Sie, um das Dialogfeld-Initialisierung zu erweitern.|  
|[CDialog::OnSetFont](#onsetfont)|Überschreiben Sie, um die Schriftart angeben, die ein Dialogfeld-Steuerelement zu verwenden, wenn der Text gezeichnet wird.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Verschiebt den Fokus in das vorherige Dialogfeld-Steuerelement im Dialogfeld.|  
|[CDialog::SetDefID](#setdefid)|Das Standardsteuerelement pushbutton für ein Dialogfeld in einer angegebenen Pushbutton geändert.|  
|[CDialog::SetHelpID](#sethelpid)|Legt eine kontextbezogene Hilfe-ID für das Dialogfeld.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|Überschreiben Sie, um die Schaltfläche "Abbrechen" oder der Schlüssel ESC-Aktion ausführen. Standardmäßig schließt das Dialogfeld und **DoModal** gibt **IDCANCEL**.|  
|[CDialog::OnOK](#onok)|Überschreiben Sie die Schaltfläche "OK"-Aktion in einem modalen Dialogfeld. Standardmäßig schließt das Dialogfeld und `DoModal` gibt **IDOK**.|  
  
## <a name="remarks"></a>Hinweise  
 Dialogfelder werden zwei Typen: modale und nicht modale. Ein modales Dialogfeld muss durch den Benutzer geschlossen werden, bevor die Anwendung fortgesetzt wird. Ein nicht modales Dialogfeld kann der Benutzer das Dialogfeld anzuzeigen und zu einem anderen Vorgang zurückgegeben wird, ohne Abbrechen oder entfernen das Dialogfeld.  
  
 Ein `CDialog` Objekt ist eine Kombination aus einer Dialogfeldvorlage und eine `CDialog`-Klasse. Dialog-Editor die Dialogfeldvorlage erstellen und speichern es in einer Ressource, und verwenden Sie dann den hinzufügen-Klassen-Assistenten zum Erstellen einer Klasse abgeleitet `CDialog`.  
  
 Ein Dialogfeld wie jedem anderen Fenster empfängt Nachrichten von Windows. In einem Dialogfeld werden Sie besonders interessiert, Behandeln von Benachrichtigungen von der Dialogfeld-Steuerelemente handelt wie die Benutzerinteraktion mit einem Dialogfeld. Verwenden Sie das Fenster Eigenschaften auswählen, welche Nachrichten sollen Handle und die entsprechenden Meldungszuordnungseinträge und Meldungshandler-Memberfunktionen der Klasse für Sie hinzufügt. Sie müssen nur die Handler-Memberfunktionen von anwendungsspezifischen Code schreiben.  
  
 Falls gewünscht, können Sie immer Meldungszuordnungseinträge und Memberfunktionen manuell schreiben.  
  
 In allen außer den einfachsten Dialogfeld fügen Sie Membervariablen zur abgeleiteten Dialogfeldklasse zum Speichern von Daten in das Dialogfeld Steuerelemente vom Benutzer eingegebenen oder Daten für den Benutzer angezeigt. Variable hinzufügen-Assistenten können Sie Member-Variablen erstellen und diese Steuerelemente zuordnen. Gleichzeitig wählen Sie einen Variablentyp und den zulässigen Wertebereich für jede Variable ein. Der Code-Assistenten wird die Membervariablen abgeleiteten Dialogfeldklasse hinzugefügt.  
  
 Eine Zuordnung wird generiert, um den Austausch von Daten zwischen der Membervariablen und das Dialogfeld-Steuerelementen automatisch behandelt. Die Zuordnung enthält Funktionen, die die Steuerelemente im Dialogfeld mit den richtigen Werten zu initialisieren, die Daten abzurufen und Daten überprüft werden.  
  
 Um ein modales Dialogfeld erstellen möchten, erstellen Sie ein Objekt auf dem Stapel mit dem Konstruktor für die abgeleiteten Dialogfeldklasse, und rufen Sie dann `DoModal` im Dialogfenster und seiner Steuerelemente zu erstellen. Wenn Sie ein nicht modales Dialogfeld erstellen möchten, rufen Sie **erstellen** im Konstruktor der Dialogfeldklasse.  
  
 Sie können auch eine Vorlage im Arbeitsspeicher erstellen, mit einem [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Datenstruktur, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Nach der Konstruktion einer `CDialog` -Objekt, rufen Sie [CreateIndirect](#createindirect) ein ohne Modus erstellen (Dialogfeld), oder rufen [InitModalIndirect](#initmodalindirect) und [DoModal](#domodal) um ein modales Dialogfeld zu erstellen.  
  
 Die Zuordnung Dialogdatenaustausch und-Validierung bezieht sich in einer Überschreibung der `CWnd::DoDataExchange` , die die neue Dialogfeldklasse hinzugefügt wird. Finden Sie unter der [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) -Memberfunktion `CWnd` Weitere Informationen über die Funktionalität von Exchange und Validierung.  
  
 Der Programmierer und der Framework-Aufruf `DoDataExchange` indirekt über einen Aufruf von [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Das Framework ruft `UpdateData` Wenn klickt der Benutzer die Schaltfläche "OK", um ein modales Dialogfeld zu schließen. (Die Daten werden nicht abgerufen, wenn auf die Schaltfläche Abbrechen geklickt wird.) Die standardmäßige Implementierung des [OnInitDialog](#oninitdialog) ruft auch `UpdateData` die Anfangswerte der Steuerelemente festgelegt. Überschreiben Sie i. d. r. `OnInitDialog` um Steuerelemente zu initialisieren. `OnInitDialog`wird aufgerufen, nachdem die Dialogfeld-Steuerelemente erstellt werden und noch bevor das Dialogfeld angezeigt wird.  
  
 Rufen Sie `CWnd::UpdateData` zu einem beliebigen Zeitpunkt während der Ausführung ein Dialogfeld mit oder ohne Modus.  
  
 Wenn Sie ein Dialogfeld von hand entwickeln, Sie die erforderlichen Membervariablen zur Klasse abgeleiteten Dialogfeld selbst hinzuzufügen, und Sie die Memberfunktionen zum Festlegen oder Abrufen dieser Werte hinzufügen.  
  
 Ein modales Dialogfeld wird automatisch geschlossen, wenn der Benutzer auf die Schaltfläche OK oder Abbrechen drückt oder wenn der Code Ruft die `EndDialog` -Memberfunktion.  
  
 Beim Implementieren eines nicht modalen Dialogfelds immer außer Kraft setzen der `OnCancel` -Memberfunktion und Aufruf `DestroyWindow` aus darin. Rufen Sie die Basisklasse nicht `CDialog::OnCancel`, da sie aufruft, `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch werden nicht gelöscht. Sie sollten auch überschreiben, `PostNcDestroy` für nicht modale Dialogfelder zum Löschen **dies**, da nicht modale Dialogfelder in der Regel zugeordnet sind, mit **neue**. Modale Dialogfelder werden in der Regel im Frame erstellt und müssen nicht `PostNcDestroy` bereinigen.  
  
 Weitere Informationen zu `CDialog` finden Sie unter:  
  
- [Dialogfelder](../../mfc/dialog-boxes.md)  
  
-   Knowledge Base-Artikel Q262954: So wird's gemacht: Erstellen Sie ein Dialogfeld Protokollanzeige mit Bildlaufleisten  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="a-namecdialoga--cdialogcdialog"></a><a name="cdialog"></a>CDialog::CDialog  
 Um ressourcenbasierte modales Dialogfeld zu konstruieren, rufen Sie entweder öffentlichen Form des Konstruktors.  
  
```  
explicit CDialog(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
explicit CDialog(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);  
  
CDialog();
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen des eine Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Eine Form des Konstruktors bietet Zugriff auf die Ressource nach dem Vorlagennamen. Der andere Konstruktor bietet Zugriff durch Vorlagen-ID-Nummer in der Regel mit einer **IDD_** Präfix (z. B. IDD_DIALOG1).  
  
 Um ein modales Dialogfeld aus einer Vorlage im Arbeitsspeicher zu konstruieren, zuerst die parameterlosen, geschützten Konstruktor aufrufen, und rufen Sie dann `InitModalIndirect`.  
  
 Nachdem Sie ein modales Dialogfeld mit einer der oben aufgeführten Methoden erstellen, rufen Sie `DoModal`.  
  
 Verwenden Sie zum Erstellen eines nicht modalen Dialogfelds geschützter Form der `CDialog` Konstruktor. Der Konstruktor ist geschützt, da Sie eine eigene Klasse im Dialogfeld zum Implementieren eines nicht modalen Dialogfelds abgeleitet werden müssen. Erstellen eines nicht modalen Dialogfelds ist ein zweistufiger Prozess. Rufen Sie zuerst den Konstruktor; Rufen Sie dann die **erstellen** Member-Funktion zum Erstellen einer Ressource-basiertes Dialogfeld oder rufen Sie `CreateIndirect` im Dialogfeld aus einer Vorlage im Arbeitsspeicher erstellen.  
  
##  <a name="a-namecreatea--cdialogcreate"></a><a name="create"></a>CDialog::Create  
 Rufen Sie **erstellen** ein nicht modales Dialogfeld mit einer Vorlage im Dialogfeld aus einer Ressource zu erstellen.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszTemplateName`  
 Enthält eine auf Null endende Zeichenfolge, die den Namen des eine Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
 `nIDTemplate`  
 Enthält die ID-Nummer einer Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Beide Formen zurückgeben, einen Wert ungleich NULL, wenn das Dialogfeld Erstellung und Initialisierung erfolgreich waren. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Aufruf von put **erstellen** in den Konstruktor oder rufen sie nach dem Konstruktor aufgerufen wird.  
  
 Zwei Formen von der **erstellen** Memberfunktion werden durch den Namen oder ID-Nummer für die Vorlage (z. B. "IDD_DIALOG1") für den Zugriff auf das Dialogfeld Dialogfeldvorlagen-Ressource bereitgestellt.  
  
 Übergeben Sie für beide Formen einen Zeiger auf das übergeordnete Fenster-Objekt. Wenn `pParentWnd` ist **NULL**, dessen übergeordnete Fenster oder das Besitzer festlegen, um das Hauptfenster der Anwendung das Dialogfeld erstellt werden.  
  
 Die **erstellen** -Memberfunktion zurückgegeben wird, unmittelbar nach Erstellen des Dialogfelds.  
  
 Verwenden der **WS_VISIBLE** in der Vorlage im Dialogfeld Format, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow`. Weiter im Dialogfeld Formatvorlagen und ihrer Anwendung finden Sie in der [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] und [Fensterstile](../../mfc/reference/window-styles.md) in der *MFC-Referenz*.  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt, indem die **erstellen** Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#62;](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="a-namecreateindirecta--cdialogcreateindirect"></a><a name="createindirect"></a>CDialog::CreateIndirect  
 Rufen Sie diese Memberfunktion, um ein nicht modales Dialogfeld aus einer Vorlage im Dialogfeld im Arbeitsspeicher zu erstellen.  
  
```  
virtual BOOL CreateIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
virtual BOOL CreateIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDialogTemplate`  
 Verweist auf Arbeitsspeicher, das Dialogfeld Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage ist in Form einer [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) -Struktur und Informationen, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pParentWnd`  
 Zeigt das Dialogfeldobjekt übergeordneten Fenster Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)). Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
 `lpDialogInit`  
 Verweist auf eine **DLGINIT** Ressource.  
  
 `hDialogTemplate`  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld. Diese Vorlage ist in Form einer **DLGTEMPLATE** Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld erstellt und wurde erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CreateIndirect` -Memberfunktion zurückgegeben wird, unmittelbar nach Erstellen des Dialogfelds.  
  
 Verwenden der **WS_VISIBLE** in der Vorlage im Dialogfeld Format, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow` verursachen angezeigt werden. Weitere Informationen dazu, wie Sie andere Dialogfeld-Stile in der Vorlage angeben können, finden Sie unter der [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt, indem die `CreateIndirect` Funktion.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten, erfordern zusätzliche Informationen einer **DLGINIT** Ressource. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage einen MFC-ActiveX-Steuerelemente erstellen." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namedomodala--cdialogdomodal"></a><a name="domodal"></a>Methode CDialog:: DoModal  
 Rufen Sie diese Memberfunktion zum Aufrufen des modale Dialogfelds und das Dialogfeld Ergebnis zurückgeben.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `int` -Wert, der der Wert gibt an der `nResult` zu übergebene Parameter der [CDialog::EndDialog](#enddialog) -Memberfunktion, die verwendet wird, um das Dialogfeld zu schließen. Der Rückgabewert ist -1, wenn die Funktion nicht im Dialogfeld erstellt werden konnte oder **IDABORT** Wenn ein anderer Fehler aufgetreten ist, in diesem Fall das Ausgabefenster enthält Fehlerinformationen von [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verarbeitet die gesamte Interaktion mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. der Benutzer kann nicht, also mit anderen Fenstern interagieren, bis das Dialogfeld geschlossen wird.  
  
 Wenn der Benutzer die Schaltflächen im Dialogfeld z. B. OK oder Abbrechen einer Meldungshandler-Memberfunktion, wie z. B. klickt [OnOK](#onok) oder [OnCancel](#oncancel), wird aufgerufen, um das Dialogfeld zu schließen. Die Standardeinstellung `OnOK` Memberfunktion überprüft und aktualisiert die Daten im Dialogfeld und schließen Sie das Dialogfeld mit dem Ergebnis **IDOK**, und der standardmäßige `OnCancel` Memberfunktion schließt das Dialogfeld Ergebnis **IDCANCEL** ohne überprüfen oder Aktualisieren der Daten im Dialogfeld. Sie können diese Meldungshandler-Funktionen, um deren Verhalten zu ändern, überschreiben.  
  
> [!NOTE]
> `PreTranslateMessage`wird jetzt für das modale Dialogfeld Feld Verarbeitung aufgerufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#63;](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="a-nameenddialoga--cdialogenddialog"></a><a name="enddialog"></a>CDialog::EndDialog  
 Rufen Sie diese Memberfunktion, um ein modales Dialogfeld zu beenden.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Parameter  
 `nResult`  
 Enthält den Wert aus dem Dialogfeld an den Aufrufer zurückgegeben werden `DoModal`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt `nResult` als Rückgabewert von `DoModal`. Verwenden Sie die `EndDialog` Funktion zum Abschließen der Verarbeitung, wenn ein modales Dialogfeld erstellt wird.  
  
 Rufen Sie `EndDialog` jederzeit selbst im [OnInitDialog](#oninitdialog), in diesem Fall schließen Sie das Dialogfeld, bevor es angezeigt wird oder bevor der Eingabefokus festgelegt wird.  
  
 `EndDialog`Das Dialogfeld wird nicht sofort geschlossen werden. Stattdessen wird ein Flag, das das Dialogfeld zu schließen, sobald der aktuelle Message-Handler gibt leitet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#64;](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog&#65;](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="a-namegetdefida--cdialoggetdefid"></a><a name="getdefid"></a>CDialog::GetDefID  
 Rufen Sie die `GetDefID` Memberfunktion, die die ID des Steuerelements pushbutton Standard für ein Dialogfeld zu erhalten.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Wert ( `DWORD`). Weist den Standardwert Pushbutton einen ID-Wert, das höherwertige Wort enthält **DC_HASDEFID** und das untere Wort den ID-Wert enthält. Wenn die Standard-Pushbutton keinen ID-Wert, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist normalerweise auf die Schaltfläche OK.  
  
##  <a name="a-namegotodlgctrla--cdialoggotodlgctrl"></a><a name="gotodlgctrl"></a>CDialog::GotoDlgCtrl  
 Verschiebt den Fokus auf das angegebene Steuerelement im Dialogfeld.  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Parameter  
 `pWndCtrl`  
 Identifiziert das Fenster (Steuerelement), das den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Um einen Zeiger auf das Steuerelement zu übergeben (untergeordneten Fensters) `pWndCtrl`, rufen Sie die `CWnd::GetDlgItem` Memberfunktion, die einen Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).  
  
##  <a name="a-nameinitmodalindirecta--cdialoginitmodalindirect"></a><a name="initmodalindirect"></a>DLGTEMPL  
 Rufen Sie diese Memberfunktion zum Initialisieren Sie ein modales Dialogfeld-Objekt, das mit einer im Dialogfeld Vorlage, die Sie im Speicher erstellen.  
  
```  
BOOL InitModalIndirect(
    LPCDLGTEMPLATE lpDialogTemplate,  
    CWnd* pParentWnd = NULL,  
    void* lpDialogInit = NULL);

 
    BOOL InitModalIndirect(
    HGLOBAL hDialogTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDialogTemplate`  
 Verweist auf Arbeitsspeicher, das Dialogfeld Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage ist in Form einer [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) -Struktur und Informationen, wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `hDialogTemplate`  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld. Diese Vorlage ist in Form einer **DLGTEMPLATE** Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
 `pParentWnd`  
 Verweist auf das übergeordnete Element oder Besitzer (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist dies **NULL**, wird das Dialogfeldobjekt übergeordnete Fenster zum Hauptfenster der Anwendung festgelegt.  
  
 `lpDialogInit`  
 Verweist auf eine **DLGINIT** Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeldobjekt erstellt und initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Um ein modales Dialogfeld indirekt zu erstellen, zunächst zuordnen Sie einen globale Speicherblock und füllen Sie es mit der Dialogfeldvorlage. Rufen Sie den leeren `CDialog` Konstruktor, um das Dialogfeld-Objekt zu erstellen. Anschließend rufen Sie `InitModalIndirect` das Handle zur in-Memory-Dialogfeld Vorlage zu speichern. Das Dialogfeld Windows erstellt und angezeigt höher, bei der [DoModal](#domodal) -Memberfunktion aufgerufen wird.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten, erfordern zusätzliche Informationen einer **DLGINIT** Ressource. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage einen MFC-ActiveX-Steuerelemente erstellen." Knowledge Base-Artikeln finden Sie in der MSDN Library Visual Studio-Dokumentation oder unter [http://support.microsoft.com](http://support.microsoft.com/).  
  
##  <a name="a-namemapdialogrecta--cdialogmapdialogrect"></a><a name="mapdialogrect"></a>CDialog::MapDialogRect  
 Rufen Sie die im Dialogfeld Einheiten eines Rechtecks Bildschirm Einheiten zu konvertieren.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpRect`  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält Koordinaten konvertiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet, die durchschnittliche Breite und Höhe der Zeichen in der Schriftart für Text im Dialogfeld angegeben. Eine horizontale Einheit ist ein Viertel der Einheit Base Breite im Dialogfeld, und eine vertikale Einheit ist ein Achtel der Dialogfeld-Basis Höhe Einheit.  
  
 Die **GetDialogBaseUnits** Windows-Funktion gibt Informationen zur Datenbankgröße für die Systemschriftart, aber Sie können eine andere Schriftart für jedes Dialogfeld angeben, wenn Sie verwenden die **DS_SETFONT** Stil in der Ressourcendefinition Datei. Die `MapDialogRect` -Funktion von Windows verwendet die passende Schriftart für das Dialogfeld zu öffnen.  
  
 Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten im `lpRect` mit Bildschirm Einheiten (Pixel), damit das Rechteck zum Erstellen eines Dialogfelds oder Positionieren Sie ein Steuerelement in einem Feld verwendet werden kann.  
  
##  <a name="a-namenextdlgctrla--cdialognextdlgctrl"></a><a name="nextdlgctrl"></a>CDialog::NextDlgCtrl  
 Bewegt den Fokus zum nächsten Steuerelement im Dialogfeld.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Fokus auf das letzte Steuerelement im Dialogfeld befindet, wird er auf das erste Steuerelement verschoben.  
  
##  <a name="a-nameoncancela--cdialogoncancel"></a><a name="oncancel"></a>CDialog::OnCancel  
 Das Framework ruft diese Methode auf, wenn der Benutzer klickt **Abbrechen** oder Drücken von ESC in einem Dialogfeld mit oder ohne Modus.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Aktionen (z. B. das Wiederherstellen von alten Daten) Wenn ein Benutzer das Dialogfeld schließt, indem Sie auf **Abbrechen** oder drücken die ESC-Taste. Standardmäßig schließt ein modales Dialogfeld durch Aufruf von [EndDialog](#enddialog) und [DoModal](#domodal) IDCANCEL zurückgegeben.  
  
 Bei der Implementierung der **Abbrechen** Schaltfläche in einem nicht modalen Dialogfeld müssen Sie überschreiben die `OnCancel` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Basisklassenmethode nicht, da er ruft `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch nicht zerstören.  
  
> [!NOTE]
>  Wenn Sie verwenden, überschreiben Sie diese Methode kann kein `CFileDialog` Objekt in einem Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#66;](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="a-nameoninitdialoga--cdialogoninitdialog"></a><a name="oninitdialog"></a>CDialog::  
 Diese Methode wird aufgerufen, als Antwort auf die `WM_INITDIALOG` Nachricht.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt. Wenn `OnInitDialog` gibt einen Wert ungleich NULL, Windows legt den Eingabefokus auf den Standardspeicherort an, das erste Steuerelement im Dialogfeld. Die Anwendung kann 0 nur zurück, wenn es explizit den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Windows sendet die `WM_INITDIALOG` Nachricht an das Dialogfeld während der [erstellen](#create), [CreateIndirect](#createindirect), oder [DoModal](#domodal) Aufrufe, die auftreten, unmittelbar bevor das Dialogfeld angezeigt wird.  
  
 Überschreiben Sie diese Methode, wenn Sie spezielle Verarbeitung bei der Initialisierung des Dialogfelds ausführen möchten. In der überschriebenen Version, rufen Sie zunächst die Basisklasse `OnInitDialog` jedoch ignoriert den Rückgabewert. Geben Sie in der Regel zurück, `TRUE` von der überschriebenen Methode.  
  
 Windows ruft die `OnInitDialog` Funktion mithilfe der globalen Dialogfelder-Prozedur, die häufig für alle Dialogfelder für die Microsoft Foundation Class-Bibliothek. Diese Funktion über die Zuordnung der Nachricht wird nicht aufgerufen, und Sie benötigen daher keine Eintrags für eine Zuordnung für diese Methode.  
  
> [!NOTE]
>  Wenn Sie verwenden, überschreiben Sie diese Methode kann kein `CFileDialog` Objekt in einem Programm, das unter kompiliert wird [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Weitere Informationen zur Änderung der `CFileDialog` unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#67;](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="a-nameonoka--cdialogonok"></a><a name="onok"></a>CDialog::OnOK  
 Wird aufgerufen, wenn der Benutzer klickt auf die **OK** Schaltfläche (die Schaltfläche mit einer ID IDOK).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Aktionen durchzuführen, wenn die **OK** Schaltfläche aktiviert ist. Wenn das Dialogfeld automatische Validierung und Exchange enthält, wird die standardmäßige Implementierung dieser Methode überprüft die Dialogfelddaten und die entsprechenden Variablen in der Anwendung aktualisiert.  
  
 Bei der Implementierung der **OK** Schaltfläche in einem nicht modalen Dialogfeld müssen Sie überschreiben die `OnOK` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Basisklassenmethode nicht, da er ruft [EndDialog](#enddialog) , wird das Dialogfeld ausgeblendet, jedoch nicht gelöscht.  
  
> [!NOTE]
>  Wenn Sie verwenden, überschreiben Sie diese Methode kann kein `CFileDialog` Objekt in einem Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog&#68;](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="a-nameonsetfonta--cdialogonsetfont"></a><a name="onsetfont"></a>CDialog::OnSetFont  
 Gibt die Schriftart, die ein Steuerelement im Dialogfeld beim Zeichnen von Text verwendet.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pFont`  
 Gibt einen Zeiger auf die Schriftart, die als Standardeinstellung für alle Steuerelemente in diesem Dialogfeld verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld wird die angegebene Schriftart als Standard für alle Steuerelemente verwenden.  
  
 Dialog-Editor wird die Schriftart im Dialogfeld in der Regel als Teil eines Dialogfeld Dialogfeldvorlagen-Ressource.  
  
> [!NOTE]
>  Wenn Sie verwenden, überschreiben Sie diese Methode kann kein `CFileDialog` Objekt in einem Programm, das unter kompiliert wird [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Weitere Informationen zur Änderung der `CFileDialog` unter [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="a-nameprevdlgctrla--cdialogprevdlgctrl"></a><a name="prevdlgctrl"></a>CDialog::PrevDlgCtrl  
 Setzt den Fokus in das vorherige Steuerelement in das Dialogfeld.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Fokus auf das erste Steuerelement im Dialogfeld befindet, verschiebt er bis zum letzten Steuerelement im Feld an.  
  
##  <a name="a-namesetdefida--cdialogsetdefid"></a><a name="setdefid"></a>CDialog::SetDefID  
 Ändert das pushbutton Standardsteuerelement für ein Dialogfeld an.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt die ID des Steuerelements pushbutton, die standardmäßig verwendet wird.  
  
##  <a name="a-namesethelpida--cdialogsethelpid"></a><a name="sethelpid"></a>CDialog::SetHelpID  
 Legt eine kontextbezogene Hilfe-ID für das Dialogfeld.  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDR*  
 Gibt die kontextbezogene Hilfe-ID an.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)   
 [MFC-Beispiel DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)


