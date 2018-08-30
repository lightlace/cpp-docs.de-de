---
title: CDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDialog
- AFXWIN/CDialog
- AFXWIN/CDialog::CDialog
- AFXWIN/CDialog::Create
- AFXWIN/CDialog::CreateIndirect
- AFXWIN/CDialog::DoModal
- AFXWIN/CDialog::EndDialog
- AFXWIN/CDialog::GetDefID
- AFXWIN/CDialog::GotoDlgCtrl
- AFXWIN/CDialog::InitModalIndirect
- AFXWIN/CDialog::MapDialogRect
- AFXWIN/CDialog::NextDlgCtrl
- AFXWIN/CDialog::OnInitDialog
- AFXWIN/CDialog::OnSetFont
- AFXWIN/CDialog::PrevDlgCtrl
- AFXWIN/CDialog::SetDefID
- AFXWIN/CDialog::SetHelpID
- AFXWIN/CDialog::OnCancel
- AFXWIN/CDialog::OnOK
dev_langs:
- C++
helpviewer_keywords:
- CDialog [MFC], CDialog
- CDialog [MFC], Create
- CDialog [MFC], CreateIndirect
- CDialog [MFC], DoModal
- CDialog [MFC], EndDialog
- CDialog [MFC], GetDefID
- CDialog [MFC], GotoDlgCtrl
- CDialog [MFC], InitModalIndirect
- CDialog [MFC], MapDialogRect
- CDialog [MFC], NextDlgCtrl
- CDialog [MFC], OnInitDialog
- CDialog [MFC], OnSetFont
- CDialog [MFC], PrevDlgCtrl
- CDialog [MFC], SetDefID
- CDialog [MFC], SetHelpID
- CDialog [MFC], OnCancel
- CDialog [MFC], OnOK
ms.assetid: ca64b77e-2cd2-47e3-8eff-c2645ad578f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff3bc9ea331be6c25be80b21c14a309d47718c8e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217332"
---
# <a name="cdialog-class"></a>CDialog-Klasse
Die Basisklasse für die Anzeige von Dialogfeldern auf dem Bildschirm verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDialog : public CWnd  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::CDialog](#cdialog)|Erstellt ein `CDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::Create](#create)|Initialisiert das `CDialog`-Objekt. Erstellt ein nicht modales Dialogfeld, und fügt es der `CDialog` Objekt.|  
|[CDialog::CreateIndirect](#createindirect)|Wird ein nicht modales Dialogfeld aus einer Vorlage im Dialogfeld im Arbeitsspeicher (nicht ressourcenbasiert) erstellt.|  
|[Methode CDialog:: DoModal](#domodal)|Ruft ein modales Dialogfeld, und gibt zurück, wenn Sie fertig.|  
|[CDialog::EndDialog](#enddialog)|Schließt ein modales Dialogfeld an.|  
|[CDialog::GetDefID](#getdefid)|Ruft die ID des das standardmäßige pushbutton-Steuerelement für ein Dialogfeld an.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Verschiebt den Fokus auf ein im angegebenen Dialogfeld-Steuerelement im Dialogfeld an.|  
|[DLGTEMPL](#initmodalindirect)|Erstellt ein modales Dialogfeld aus einer Vorlage im Dialogfeld im Arbeitsspeicher (nicht ressourcenbasiert) wird. Die Parameter werden gespeichert, bis die Funktion `DoModal` aufgerufen wird.|  
|[CDialog::MapDialogRect](#mapdialogrect)|Konvertiert die Dialogfeld-Einheiten eines Rechtecks Bildschirm Einheiten.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Verschiebt den Fokus auf das nächste Dialogfeld-Steuerelement im Dialogfeld an.|  
|[CDialog::](#oninitdialog)|Außer Kraft setzen Sie, um das Dialogfeld Initialisierung zu erweitern.|  
|[CDialog::OnSetFont](#onsetfont)|Überschreiben Sie, um die Schriftart angeben, die ein Dialogfeld-Steuerelement verwenden, wenn es sich um Text zeichnet.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Verschiebt den Fokus auf das vorherige Dialogfeld-Steuerelement im Dialogfeld.|  
|[CDialog::SetDefID](#setdefid)|Die standardmäßige pushbutton-Steuerelement für ein Dialogfeld wird in einem angegebenen Pushbutton geändert.|  
|[CDialog::SetHelpID](#sethelpid)|Legt eine kontextbezogene Hilfe-ID für das Dialogfeld fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|Überschreiben Sie, um die Schaltfläche "Abbrechen" oder die ESC-Taste Aktion auszuführen. Standardmäßig wird das Dialogfeld geschlossen und `DoModal` IDCANCEL zurückgibt.|  
|[CDialog::OnOK](#onok)|Überschreiben Sie, um die Schaltfläche "OK"-Aktion in einem modalen Dialogfeld. Standardmäßig wird das Dialogfeld geschlossen und `DoModal` IDOK zurückgibt.|  
  
## <a name="remarks"></a>Hinweise  
 Dialogfelder sind zwei Typen: modale und nicht modale. Ein modales Dialogfeld muss vom Benutzer geschlossen werden, bevor die Anwendung fortgesetzt wird. Ein nicht modales Dialogfeld ermöglicht den Benutzer das Dialogfeld anzuzeigen und zu einem anderen Vorgang zurückzugeben, ohne Abbrechen oder entfernen Sie das Dialogfeld.  
  
 Ein `CDialog` Objekt ist eine Kombination aus einer Dialogfeldvorlage und einem `CDialog`-abgeleitete Klasse. Den Dialog-Editor zum Erstellen der Dialogfeldvorlage und speichern es in einer Ressource verwenden und dann den Assistenten zum Hinzufügen von Klassen zum Erstellen einer Klasse abgeleitet `CDialog`.  
  
 Ein Dialogfeld wie jedem anderen Fenster empfängt Nachrichten von Windows. In einem Dialogfeld interessieren Sie insbesondere bei der Verarbeitung von Benachrichtigungen von der Dialogfeld-Steuerelemente, weil es sich handelt, wie der Benutzer mit einem Dialogfeld interagiert. Verwenden Sie das Fenster "Eigenschaften" auswählen, welche Nachrichten Sie möchten Handle und die entsprechenden Meldungszuordnungseinträge und Meldungshandler-Memberfunktionen der Klasse hinzugefügt. Sie müssen nur die anwendungsspezifischen Code in die Ereignishandler-Member-Funktionen zu schreiben.  
  
 Falls gewünscht, können Sie immer Meldungszuordnungseinträge und Memberfunktionen manuell schreiben.  
  
 In allen außer den einfachsten Dialogfeld fügen Sie der abgeleiteten Dialogfeld-Klasse, die zum Speichern von Daten in das Dialogfeld-Steuerelemente vom Benutzer eingegebenen oder zum Anzeigen von Daten für den Benutzer Membervariablen hinzu. Sie können die Variable hinzufügen Assistent Member-Variablen erstellen, und ordnen sie Steuerelemente verwenden. Zur gleichen Zeit wählen Sie eine Variable vom Typ und die zulässigen Wertebereich für jede Variable ein. Der Code-Assistent fügt die Membervariablen abgeleiteten Dialogfeldklasse hinzu.  
  
 Eine datenzuordnung wird generiert, um den Austausch von Daten zwischen der Membervariablen und das Dialogfeld-Steuerelementen automatisch zu behandeln. Die datenzuordnung bietet Funktionen, die die Steuerelemente im Dialogfeld mit den richtigen Werten zu initialisieren, die Daten abrufen und überprüfen Sie die Daten.  
  
 Um ein modales Dialogfeld erstellen möchten, erstellen Sie ein Objekt im Stapel mithilfe des Konstruktors für die Dialogfeldklasse abgeleiteten, und rufen Sie anschließend `DoModal` um das Dialogfeld und dessen Steuerelemente zu erstellen. Wenn Sie ein nicht modales Dialogfeld erstellen möchten, rufen Sie `Create` im Konstruktor der Dialogfeldklasse.  
  
 Sie können auch eine Vorlage im Speicher erstellen, mit einem [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Daten strukturieren, wie im Windows SDK beschrieben. Wenn Sie erstellt haben, eine `CDialog` Objekt, rufen Sie [CreateIndirect](#createindirect) ein ohne Modus zu erstellen (Dialogfeld), oder rufen [InitModalIndirect](#initmodalindirect) und [DoModal](#domodal) zum Erstellen eines modales Das Dialogfeld.  
  
 Die datenzuordnung Dialogdatenaustausch und-Validierung hat eine Überschreibung der `CWnd::DoDataExchange` , die die neue Dialogfeldklasse hinzugefügt wird. Finden Sie unter den [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) -Memberfunktion im `CWnd` Weitere Informationen zu den Dialogdatenaustausch und-Validierung-Funktionalität.  
  
 Sowohl der Programmierer und der Aufruf Framework `DoDataExchange` indirekt durch einen Aufruf von [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Das Framework ruft `UpdateData` Wenn klickt der Benutzer die Schaltfläche "OK", um ein modales Dialogfeld zu schließen. (Die Daten werden nicht abgerufen, wenn auf die Schaltfläche "Abbrechen" geklickt wird.) Die standardmäßige Implementierung des [OnInitDialog](#oninitdialog) ruft auch `UpdateData` die Anfangswerte der Steuerelemente festgelegt. Überschreiben Sie i. d. r. `OnInitDialog` um Steuerelemente zu initialisieren. `OnInitDialog` wird aufgerufen, nachdem alle die Dialogfeldsteuerelemente erstellt werden und noch bevor das Dialogfeld wird angezeigt.  
  
 Rufen Sie `CWnd::UpdateData` zu einem beliebigen Zeitpunkt während der Ausführung ein modales oder nicht modales Dialogfeld.  
  
 Wenn Sie ein Dialogfeld, das manuell entwickeln, Sie die erforderlichen Membervariablen die Dialogfeld-abgeleiteten Klasse selbst hinzufügen, und Sie die Member-Funktionen, um festzulegen, oder rufen Sie diese Werte hinzufügen.  
  
 Ein modales Dialogfeld wird automatisch geschlossen, wenn der Benutzer die Schaltflächen OK oder Abbrechen drückt oder wenn Ihr Code Ruft die `EndDialog` Member-Funktion.  
  
 Wenn Sie ein nicht modales Dialogfeld implementieren, immer außer Kraft setzen der `OnCancel` Member-Funktion und rufen `DestroyWindow` aus darin. Rufen Sie die Basisklasse nicht `CDialog::OnCancel`, da er aufruft `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch wird nicht zerstört. Sie sollten auch überschreiben, `PostNcDestroy` für nicht modale Dialogfelder zum Löschen **dies**, da nicht modale Dialogfelder in der Regel zugeordnet sind **neue**. Modale Dialogfelder sind in der Regel auf den Frame erstellt und müssen nicht `PostNcDestroy` bereinigen.  
  
 Weitere Informationen zu `CDialog` finden Sie unter:  
  
- [Dialogfelder](../../mfc/dialog-boxes.md)  
  
-   Knowledge Base-Artikel Q262954: So wird's gemacht: Erstellen Sie ein Dialogfeld Protokollanzeige mit Bildlaufleisten  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="cdialog"></a>  CDialog::CDialog  
 Um ein modales Dialogfeld ressourcenbasierte zu konstruieren, rufen Sie entweder öffentlichen Form des Konstruktors.  
  
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
 *lpszTemplateName*  
 Enthält eine Null-terminierte Zeichenfolge mit dem Namen von einer Ressource im Dialogfeld an.  
  
 *nIDTemplate*  
 Enthält die ID einer Ressource im Dialogfeld an.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.  
  
### <a name="remarks"></a>Hinweise  
 Eine Form des Konstruktors ermöglicht den Zugriff auf die Ressource anhand des Namens der Vorlage. Der andere Konstruktor bietet Zugriff über Vorlagen-ID an, in der Regel mit einer **IDD_** Präfix (z. B. IDD_DIALOG1).  
  
 Um ein modales Dialogfeld aus einer Vorlage speicherresident erstellen zu können, zuerst den parameterlosen, protected-Konstruktor aufrufen, und rufen dann `InitModalIndirect`.  
  
 Nachdem Sie ein modales Dialogfeld mit einer der oben genannten Methoden erstellen, rufen `DoModal`.  
  
 Verwenden Sie zum Erstellen eines nicht modalen Dialogfelds geschützte Form der `CDialog` Konstruktor. Der Konstruktor ist geschützt, da Sie eine eigene Klasse im Dialogfeld zum Implementieren eines nicht modalen Dialogfelds abgeleitet werden müssen. Konstruktion eines nicht modalen Dialogfelds ist ein zweistufiger Prozess. Rufen Sie zunächst den Konstruktor; Rufen Sie dann die `Create` Memberfunktion versucht, ein ressourcenbasierte Dialogfeld erstellen, oder rufen Sie `CreateIndirect` um das Dialogfeld aus einer Vorlage in den Arbeitsspeicher zu erstellen.  
  
##  <a name="create"></a>  CDialog::Create  
 Rufen Sie `Create` ein nicht modales Dialogfeld mit einer Vorlage im Dialogfeld aus einer Ressource zu erstellen.  
  
```  
virtual BOOL Create(
    LPCTSTR lpszTemplateName,  
    CWnd* pParentWnd = NULL);

 
virtual BOOL Create(
    UINT nIDTemplate,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *lpszTemplateName*  
 Enthält eine Null-terminierte Zeichenfolge mit dem Namen von einer Ressource im Dialogfeld an.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.  
  
 *nIDTemplate*  
 Enthält die ID einer Ressource im Dialogfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn im Dialogfeld-Erstellung und Initialisierung erfolgreich war. beide Formen zurückgegeben wird. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Aufruf von einfügen `Create` in den Konstruktor oder rufen sie nach dem Konstruktor aufgerufen wird.  
  
 Zwei Arten von der `Create` Memberfunktion werden anhand des Namens der Vorlage oder Vorlagen-ID-Nummer (z. B. IDD_DIALOG1) für den Zugriff auf die Ressource im Dialogfeld bereitgestellt.  
  
 Übergeben Sie für eine der Formen einen Zeiger auf das übergeordnete Fenster-Objekt. Wenn *pParentWnd* NULL ist, wird das Dialogfeld erstellt werden, mit einem übergeordneten oder Besitzer-Fenster auf das Hauptanwendungsfenster festgelegt.  
  
 Die `Create` Memberfunktion gibt sofort, nachdem Sie das Dialogfeld erstellt.  
  
 Verwenden Sie WS_VISIBLE-Stil in der Vorlage im Dialogfeld aus, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow`. Weitere Dialogfeld-Stile und ihre Anwendung finden Sie in der [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Struktur im Windows SDK und [Window-Stile](../../mfc/reference/styles-used-by-mfc.md#window-styles) in die *MFC-Referenz*.  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt die `Create` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>  CDialog::CreateIndirect  
 Rufen Sie diese Memberfunktion, um ein nicht modales Dialogfeld aus einer Dialogfeldvorlage im Speicher zu erstellen.  
  
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
 *lpDialogTemplate*  
 Verweist auf Arbeitsspeicher, eine Dialogfeld-Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage ist in Form einer [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Struktur und das Steuerelement Informationen wie beschrieben in das Windows SDK.  
  
 *pParentWnd*  
 Verweist auf das Dialogfeldobjekt übergeordnete Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)). Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.  
  
 *lpDialogInit*  
 Verweist auf eine Ressource DLGINIT.  
  
 *hDialogTemplate*  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld an. Diese Vorlage ist in Form einer `DLGTEMPLATE` Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Dialogfeld erstellt und erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CreateIndirect` Memberfunktion gibt sofort, nachdem Sie das Dialogfeld erstellt.  
  
 Verwenden Sie WS_VISIBLE-Stil in der Vorlage im Dialogfeld aus, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow` verursachen angezeigt werden. Weitere Informationen dazu, wie Sie andere Dialogfeld-Formatvorlagen in der Vorlage angeben können, finden Sie unter den [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Struktur im Windows SDK.  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt die `CreateIndirect` Funktion.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten erfordern zusätzliche Informationen, die in einer Ressource DLGINIT bereitgestellt. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage um ein MFC-Dialogfeld mit einem ActiveX-Steuerelement zu erstellen." Knowledge Base-Artikeln finden Sie unter [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="domodal"></a>  Methode CDialog:: DoModal  
 Rufen Sie diese Memberfunktion zum Aufrufen des modalen Dialogfelds sowie zum Zurückgeben des Ergebnisses im Dialogfeld, wenn fertig.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **Int** -Wert, der der Wert gibt an die *%nergebnis* Parameter, der übergeben wurde die [CDialog::EndDialog](#enddialog) Member-Funktion, die verwendet wird, um das Dialogfeld zu schließen. Der zurückgegebene Wert ist 1, wenn die Funktion nicht erstellen konnte, die im Dialogfeld oder IDABORT Wenn ein anderer Fehler aufgetreten ist, in diesem Fall das Fenster "Ausgabe" Fehlerinformationen von enthält, [GetLastError](https://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verarbeitet die gesamte Interaktion mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. der Benutzer kann nicht, also mit anderen Windows interagieren, bis das Dialogfeld geschlossen wird.  
  
 Klickt der Benutzer eines der Druckknöpfe, in das Dialogfeld, z. B. OK oder Abbrechen, einer-Nachrichtenhandler-Memberfunktion, z. B. [OnOK](#onok) oder [OnCancel](#oncancel), aufgerufen, um zu versuchen, das Dialogfeld zu schließen. Der Standardwert `OnOK` Memberfunktion wird überprüfen und aktualisieren Sie die Daten im Dialogfeld und schließen Sie das Dialogfeld mit dem Ergebnis IDOK und der Standardwert `OnCancel` Member-Funktion wird das Dialogfeld mit dem Ergebnis IDCANCEL schließen, ohne zu überprüfen oder Aktualisieren der Dialogfeld-Daten. Sie können diese Meldungshandler-Funktionen zum Ändern des Verhaltens überschreiben.  
  
> [!NOTE]
> `PreTranslateMessage` für modales Dialogfeld im Feld die Nachrichtenverarbeitung wird jetzt aufgerufen werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>  CDialog::EndDialog  
 Rufen Sie diese Memberfunktion, um ein modales Dialogfeld zu beenden.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Parameter  
 *%nergebnis*  
 Enthält den Wert aus dem Dialogfeld an den Aufrufer der zurückzugebenden `DoModal`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt *%nergebnis* als Rückgabewert der `DoModal`. Verwenden Sie die `EndDialog` Funktion zum Abschließen der Verarbeitung, wenn ein modales Dialogfeld erstellt wird.  
  
 Rufen Sie `EndDialog` jederzeit selbst im [OnInitDialog](#oninitdialog), in diesem Fall schließen Sie das Dialogfeld, davor angezeigt wird oder vor der Eingabefokus festgelegt ist.  
  
 `EndDialog` Das Dialogfeld wird nicht sofort geschlossen werden. Stattdessen wird ein Flag, das leitet das Dialogfeld zu schließen, sobald der aktuellen Message-Handler zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>  CDialog::GetDefID  
 Rufen Sie die `GetDefID` Memberfunktion versucht, die das standardmäßige pushbutton-Steuerelement-ID für ein Dialogfeld zu erhalten.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Wert ( `DWORD`). Wenn die standardmäßige Pushbutton einen ID-Wert verfügt, wird das höherwertige Wort enthält DC_HASDEFID, und das niederwertige Wort enthält den ID-Wert. Wenn die standardmäßige Pushbutton nicht über ein ID-Wert verfügt, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist normalerweise die Schaltfläche "OK".  
  
##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl  
 Verschiebt den Fokus auf das angegebene Steuerelement im Dialogfeld an.  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndCtrl*  
 Gibt das Fenster (Steuerelement), um den Fokus erhalten.  
  
### <a name="remarks"></a>Hinweise  
 Um einen Zeiger auf das Steuerelement (untergeordnete Fenster) als übergeben *pWndCtrl*, rufen Sie die `CWnd::GetDlgItem` Memberfunktion, wodurch einen Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).  
  
##  <a name="initmodalindirect"></a>  DLGTEMPL  
 Rufen Sie diese Memberfunktion zum Initialisieren Sie ein modales Dialogfeld-Objekt, das mithilfe einer Dialogfeld-Vorlage, die Sie in den Arbeitsspeicher zu erstellen.  
  
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
 *lpDialogTemplate*  
 Verweist auf Arbeitsspeicher, eine Dialogfeld-Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage ist in Form einer [DLGTEMPLATE](/windows/desktop/api/winuser/ns-winuser-dlgtemplate) Struktur und das Steuerelement Informationen wie beschrieben in das Windows SDK.  
  
 *hDialogTemplate*  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld an. Diese Vorlage ist in Form einer `DLGTEMPLATE` Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Element oder Besitzer Window-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)) zu dem das Dialogfeldobjekt gehört. Wenn es NULL ist, wird das Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt.  
  
 *lpDialogInit*  
 Verweist auf eine Ressource DLGINIT.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Dialogfeldobjekt erstellt und erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Um ein modales Dialogfeld indirekt zu erstellen, zunächst belegen Sie einen Speicherblock auf dem globalen und füllen Sie es mit der Dialogfeldvorlage. Rufen Sie dann auf die leere `CDialog` Konstruktor zum Erstellen des Dialogfeld-Objekts. Rufen Sie als Nächstes `InitModalIndirect` Ihr Handle an die in-Memory-Dialogfeld-Vorlage zu speichern. Das Dialogfeld "Windows" erstellt und angezeigt wird später bei der [DoModal](#domodal) Memberfunktion aufgerufen wird.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten erfordern zusätzliche Informationen, die in einer Ressource DLGINIT bereitgestellt. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage um ein MFC-Dialogfeld mit einem ActiveX-Steuerelement zu erstellen." Knowledge Base-Artikeln finden Sie unter [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect  
 Rufen Sie die Dialogfeld-Einheiten eines Rechtecks in Einheiten von Bildschirm zu konvertieren.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpRect*  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält koordiniert, konvertiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dialogfeld-Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet, die durchschnittliche Breite und Höhe der Zeichen in die Schriftart für Dialogfeld-Text angegeben. Eine horizontale Einheit ist ein Viertel der im Dialogfeld Basis-Width-Komponente und eine vertikale Einheit ist ein Achtel der Dialogfeld-Basis Height-Komponente.  
  
 Die `GetDialogBaseUnits` Windows-Funktion gibt die Größeninformationen für die Systemschriftart, aber Sie können eine andere Schriftart für jedes Dialogfeld angeben, bei der Verwendung des DS_SETFONT-Stils in der Ressourcendefinition Datei. Die `MapDialogRect` Windows-Funktion verwendet die passende Schriftart für das Dialogfeld zu öffnen.  
  
 Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten in *LpRect* mit Bildschirm von Einheiten (in Pixel), damit das Rechteck verwendet werden kann, erstellen ein Dialogfeld oder ein Steuerelement innerhalb eines Felds zu positionieren.  
  
##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl  
 Verschiebt den Fokus auf das nächste Steuerelement im Dialogfeld an.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Fokus auf das letzte Steuerelement im Dialogfeld befindet, bewegt auf das erste Steuerelement.  
  
##  <a name="oncancel"></a>  CDialog::OnCancel  
 Das Framework ruft diese Methode auf, wenn der Benutzer klickt **Abbrechen** oder in ein modales oder nicht modales Dialogfeld, das die ESC-Taste drückt.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Ausführen von Aktionen (z. B. das Wiederherstellen von alten Daten) Wenn ein Benutzer das Dialogfeld schließt, indem Sie auf **Abbrechen** oder die ESC-Taste drücken. Standardmäßig schließt ein modales Dialogfeld durch Aufruf von [EndDialog](#enddialog) und dadurch [DoModal](#domodal) IDCANCEL zurückgegeben.  
  
 Wenn Sie implementieren die **Abbrechen** Schaltfläche in ein nicht modales Dialogfeld, müssen Sie überschreiben die `OnCancel` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Methode der Basisklasse, da sie aufruft, nicht `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch nicht zerstört es.  
  
> [!NOTE]
>  Sie können diese Methode können nicht überschreiben, bei der Verwendung einer `CFileDialog` Objekt in ein Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>  CDialog::  
 Diese Methode wird aufgerufen, als Reaktion auf die `WM_INITDIALOG` Nachricht.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob die Anwendung, den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde. Wenn `OnInitDialog` ungleich NULL zurückgegeben wird, wird Windows den Eingabefokus auf den Standardspeicherort an, das erste Steuerelement in das Dialogfeld. Die Anwendung kann 0 nur zurück, wenn sie explizit den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Windows sendet die `WM_INITDIALOG` Nachricht das Dialogfeld während der [erstellen](#create), [CreateIndirect](#createindirect), oder [DoModal](#domodal) -Aufrufe, die unmittelbar vor das Dialogfeld auf wird angezeigt.  
  
 Überschreiben Sie diese Methode, wenn Sie beim Initialisieren des Dialogfelds spezielle Verarbeitungsaufgaben durchführen möchten. In der außer Kraft gesetzte Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber ignorieren Sie den Rückgabewert. Geben Sie in der Regel zurück, `TRUE` aus der überschriebenen Methode.  
  
 Windows ruft die `OnInitDialog` Funktion mithilfe der globalen-Standarddialogfeld-Prozedur, die häufig für alle Dialogfelder für die Microsoft Foundation Class-Bibliothek. Diese Funktion über die meldungszuordnung wird nicht aufgerufen, und Sie benötigen daher keine Eintrags für eine Zuordnung für diese Methode.  
  
> [!NOTE]
> Sie können diese Methode können nicht überschreiben, bei der Verwendung einer `CFileDialog` Objekt in ein Programm, das unter Windows Vista oder höher kompiliert wird. Weitere Informationen zu Änderungen an `CFileDialog` unter Windows Vista und höher finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>  CDialog::OnOK  
 Wird aufgerufen, wenn der Benutzer klickt auf die **OK** (die Schaltfläche mit einer ID von IDOK).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Aktionen durchzuführen, wenn die **OK** Schaltfläche aktiviert ist. Wenn Sie das Dialogfeld automatisch eine datenvalidierung als auch Exchange enthält, die Standardimplementierung dieser Methode überprüft die Dialogfelddaten, und Sie werden die entsprechenden Variablen in Ihrer Anwendung aktualisiert.  
  
 Wenn Sie implementieren die **OK** Schaltfläche in ein nicht modales Dialogfeld, müssen Sie überschreiben die `OnOK` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Methode der Basisklasse, da sie aufruft, nicht [EndDialog](#enddialog) die ist das Dialogfeld nicht mehr sichtbar, jedoch nicht zerstört.  
  
> [!NOTE]
>  Sie können diese Methode können nicht überschreiben, bei der Verwendung einer `CFileDialog` Objekt in ein Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>  CDialog::OnSetFont  
 Gibt die Schriftart, die ein Dialogfeld-Steuerelement beim Zeichnen von Text verwendet.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pFont*  
 Gibt einen Zeiger auf die Schriftart, die als die Standardschriftart für alle Steuerelemente in diesem Dialogfeld verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld wird die angegebene Schriftart wird standardmäßig für alle Steuerelemente verwenden.  
  
 Der Dialog-Editor legt die Dialogfeld-Schriftart in der Regel als Teil der Dialogfeldvorlagen-Ressource im Dialogfeld fest.  
  
> [!NOTE]
> Sie können diese Methode können nicht überschreiben, bei der Verwendung einer `CFileDialog` Objekt in ein Programm, das unter Windows Vista oder höher kompiliert wird. Weitere Informationen zu Änderungen an `CFileDialog` unter Windows Vista und höher finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl  
 Legt den Fokus zum vorherigen Steuerelement im Dialogfeld fest.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn das erste Steuerelement in das Dialogfeld der Fokus hat, verschiebt er bis zum letzten Steuerelement in das Feld an.  
  
##  <a name="setdefid"></a>  CDialog::SetDefID  
 Ändert die standardmäßige pushbutton-Steuerelement für ein Dialogfeld an.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Gibt die ID des pushbutton-Steuerelements, die standardmäßig verwendet wird.  
  
##  <a name="sethelpid"></a>  CDialog::SetHelpID  
 Legt eine kontextbezogene Hilfe-ID für das Dialogfeld fest.  
  
```  
void SetHelpID(UINT nIDR);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDR*  
 Gibt an, die kontextbezogene Hilfe-ID.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DLGCBR32](../../visual-cpp-samples.md)   
 [MFC-Beispiel DLGTEMPL](../../visual-cpp-samples.md)   
 [CWnd-Klasse](../../mfc/reference/cwnd-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)

