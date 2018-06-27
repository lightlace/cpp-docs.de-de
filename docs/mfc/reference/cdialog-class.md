---
title: CDialog-Klasse | Microsoft Docs
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
ms.openlocfilehash: 8ae7748c249cb9c7752b55d07bf10278c9c7f4ce
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955013"
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
|[CDialog::Create](#create)|Initialisiert die `CDialog` Objekt. Erstellt ein nicht modales Dialogfeld, und fügt es der `CDialog` Objekt.|  
|[CDialog::CreateIndirect](#createindirect)|Erstellt ein nicht modales Dialogfeld aus einer Vorlage im Dialogfeld im Arbeitsspeicher (nicht ressourcenbasierte).|  
|[Methode CDialog:: DoModal](#domodal)|Ruft ein modales Dialogfeld, und gibt Sie zurück, wenn fertig.|  
|[CDialog::EndDialog](#enddialog)|Schließt ein modales Dialogfeld an.|  
|[CDialog::GetDefID](#getdefid)|Ruft die ID der standardmäßige pushbutton-Steuerelement für ein Dialogfeld ab.|  
|[CDialog::GotoDlgCtrl](#gotodlgctrl)|Verschiebt den Fokus zu einem angegebenen Dialogfeld-Steuerelement im Dialogfeld an.|  
|[DLGTEMPL](#initmodalindirect)|Erstellt ein modales Dialogfeld aus einer Vorlage im Dialogfeld im Arbeitsspeicher (nicht ressourcenbasierte). Die Parameter werden gespeichert, bis die Funktion `DoModal` aufgerufen wird.|  
|[CDialog::MapDialogRect](#mapdialogrect)|Konvertiert die Einheiten im Dialogfeld eines Rechtecks Bildschirm Einheiten.|  
|[CDialog::NextDlgCtrl](#nextdlgctrl)|Verschiebt den Fokus auf das nächste Dialogfeld-Steuerelement im Dialogfeld an.|  
|[CDialog::](#oninitdialog)|Überschreiben Sie, um das Dialogfeld Initialisierung zu erweitern.|  
|[CDialog::OnSetFont](#onsetfont)|Überschreiben Sie, um die Schriftart angeben, die ein Dialogfeld-Steuerelement verwenden, wenn es sich um Text zeichnet.|  
|[CDialog::PrevDlgCtrl](#prevdlgctrl)|Verschiebt den Fokus auf das vorherige Dialogfeld-Steuerelement im Dialogfeld an.|  
|[CDialog::SetDefID](#setdefid)|Das standardmäßige pushbutton-Steuerelement für ein Dialogfeld in einem angegebenen Pushbutton geändert.|  
|[CDialog::SetHelpID](#sethelpid)|Legt eine kontextbezogene Hilfe-ID für das Dialogfeld.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDialog::OnCancel](#oncancel)|Außer Kraft setzen Sie, um die Schaltfläche "Abbrechen" oder ESC Aktion auszuführen. Die Standardeinstellung schließt das Dialogfeld und `DoModal` gibt **IDCANCEL**.|  
|[CDialog::OnOK](#onok)|Überschreiben Sie, um die Schaltfläche "OK"-Aktion in einem modalen Dialogfeld Ausführen. Die Standardeinstellung schließt das Dialogfeld und `DoModal` gibt **IDOK**.|  
  
## <a name="remarks"></a>Hinweise  
 Dialogfelder werden zwei Typen: modale und nicht modale. Ein modales Dialogfeld muss vom Benutzer geschlossen werden, bevor die Anwendung fortgesetzt wird. Ein nicht modales Dialogfeld ermöglicht den Benutzer das Dialogfeld anzuzeigen und heraus zu einem anderen Vorgang abbrechen oder entfernen das Dialogfeld.  
  
 Ein `CDialog` Objekt ist eine Kombination einer Dialogfeldvorlage und einem `CDialog`-abgeleitete Klasse. Dialog-Editor zum Erstellen der Dialogfeldvorlage und speichern es in einer Ressource, und verwenden Sie dann das Hinzufügen von Klassen-Assistent zum Erstellen einer Klasse abgeleitet wurde. `CDialog`.  
  
 Ein Dialogfeld, z. B. ein anderes Fenster empfängt Nachrichten von Windows. In einem Dialogfeld interessieren Sie insbesondere bei der Verarbeitung von benachrichtigungsmeldungen aus den Dialogfeld-Steuerelemente, da dies ist die Interaktion des Benutzers mit dem Dialogfeld. Verwenden Sie auswählen, welche Nachrichten Sie trotzdem Handle und die entsprechenden Meldungszuordnungseinträge und Meldungshandler Memberfunktionen der Klasse hinzugefügt wird, werden das Eigenschaftenfenster. Sie müssen nur die Handler-Memberfunktionen anwendungsspezifischen Code schreiben.  
  
 Falls gewünscht, können Sie immer Meldungszuordnungseinträge und Memberfunktionen manuell schreiben.  
  
 In alle bis auf die unbedeutendsten (Dialogfeld) fügen Sie Membervariablen zur Dialogfeldklasse abgeleiteten zum Speichern von Daten in das Dialogfeld-Steuerelemente vom Benutzer eingegebenen oder zum Anzeigen von Daten für den Benutzer an. Die Variable hinzufügen-Assistenten können Sie Member Variablen erstellen und diese mit Steuerelementen zuordnen. Gleichzeitig wählen Sie eine Variable vom Typ und den zulässigen Wertebereich für jede Variable ein. Der Code-Assistenten hinzugefügt abgeleiteten Dialogfeldklasse die Membervariablen.  
  
 Eine Zuordnung wird generiert, um den Austausch von Daten zwischen der Membervariablen und das Dialogfeld-Steuerelementen automatisch behandelt. Die datenzuordnung bietet Funktionen, die die Steuerelemente im Dialogfeld mit den richtigen Werten zu initialisieren, rufen Sie die Daten, und überprüfen Sie die Daten.  
  
 Um ein modales Dialogfeld erstellen möchten, erstellen Sie ein Objekt auf dem Stapel mit dem Konstruktor für die abgeleiteten Dialogfeldklasse, und rufen Sie anschließend `DoModal` im Dialogfenster und seiner Steuerelemente zu erstellen. Wenn Sie ein nicht modales Dialogfeld erstellen möchten, rufen Sie `Create` im Konstruktor der Dialogfeldklasse.  
  
 Sie können auch eine Vorlage im Arbeitsspeicher erstellen, mit einer [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Daten strukturieren, wie im Windows SDK beschrieben. Wenn Sie erstellt haben, eine `CDialog` -Objekt, rufen Sie [CreateIndirect](#createindirect) ein ohne Modus zu erstellen (Dialogfeld), oder rufen [InitModalIndirect](#initmodalindirect) und [DoModal](#domodal) ein modales erstellen Das Dialogfeld.  
  
 Die datenzuordnung Dialogdatenaustausch und-Validierung wird geschrieben, in einer Überschreibung von `CWnd::DoDataExchange` , Ihre neue Dialogfeldklasse hinzugefügt wird. Finden Sie unter der [DoDataExchange](../../mfc/reference/cwnd-class.md#dodataexchange) Memberfunktion in `CWnd` für Weitere Informationen über die Dialogdatenaustausch und-Validierung Funktionalität.  
  
 Der Programmierer und der Aufruf Framework `DoDataExchange` indirekt durch einen Aufruf von [CWnd::UpdateData](../../mfc/reference/cwnd-class.md#updatedata).  
  
 Das Framework ruft `UpdateData` Wenn klickt der Benutzer die Schaltfläche "OK", um ein modales Dialogfeld zu schließen. (Die Daten werden nicht abgerufen, wenn die Schaltfläche "Abbrechen" geklickt wird.) Die standardmäßige Implementierung des [OnInitDialog](#oninitdialog) ruft auch `UpdateData` die Anfangswerte der Steuerelemente festgelegt. Überschreiben Sie i. d. r. `OnInitDialog` um Steuerelemente zu initialisieren. `OnInitDialog` wird aufgerufen, nachdem der Dialogfeld-Steuerelemente werden erstellt, und unmittelbar bevor das Dialogfeld angezeigt wird.  
  
 Sie können Aufrufen `CWnd::UpdateData` zu einem beliebigen Zeitpunkt während der Ausführung einen gebunden oder ungebunden (Dialogfeld).  
  
 Wenn Sie ein Dialogfeld von hand entwickeln, Sie die erforderlichen Membervariablen zur Klasse abgeleiteten Dialogfeld selbst, und hinzufügen Memberfunktionen zur festlegen oder Abrufen dieser Werte.  
  
 Ein modales Dialogfeld wird automatisch geschlossen, wenn die Schaltfläche OK oder "Abbrechen" gedrückt wird oder wenn Ihr Code aufruft, die `EndDialog` Memberfunktion.  
  
 Wenn Sie ein nicht modales Dialogfeld implementieren, immer außer Kraft setzen die `OnCancel` Memberfunktion und rufen `DestroyWindow` aus darin. Rufen Sie nicht die Basisklasse `CDialog::OnCancel`, da er ruft `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch werden nicht gelöscht. Sie sollten auch überschreiben `PostNcDestroy` für nicht modale Dialogfelder zum Löschen von **dies**, da nicht modale Dialogfelder in der Regel zugeordnet sind, mit **neue**. Modale Dialogfelder werden in der Regel auf den Frame erstellt und müssen nicht `PostNcDestroy` Cleanup.  
  
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
 Enthält eine Null-terminierte Zeichenfolge, die eine Dialogfeldvorlagen-Ressource im Dialogfeld heißt.  
  
 *nIDTemplate*  
 Enthält die ID einer Dialogfeldvorlagen-Ressource im Dialogfeld an.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
### <a name="remarks"></a>Hinweise  
 Eine Form des Konstruktors bietet Zugriff auf die Dialogressource anhand des Namens der Vorlage. Der anderen Konstruktor ermöglicht den Zugriff von Vorlagen-ID-Nummer in der Regel mit einer **IDD_** Präfix (z. B. "IDD_DIALOG1").  
  
 Um ein modales Dialogfeld aus einer Vorlage im Arbeitsspeicher zu konstruieren, zuerst den parameterlosen, geschützten Konstruktor aufrufen, und rufen dann `InitModalIndirect`.  
  
 Nachdem Sie ein modales Dialogfeld mit einer der oben aufgeführten Methoden erstellen, rufen Sie `DoModal`.  
  
 Um ein nicht modales Dialogfeld erstellen, verwenden die geschützte Form der `CDialog` Konstruktor. Der Konstruktor ist geschützt, da Sie eine eigene Klasse im Dialogfeld, um ein nicht modales Dialogfeld implementieren abgeleitet werden müssen. Konstruktion eines nicht modalen Dialogfelds ist ein zweistufiger Prozess. Rufen Sie zunächst den Konstruktor; Rufen Sie anschließend die `Create` Memberfunktion versucht, ein ressourcenbasierte Dialogfeld erstellen, oder rufen Sie `CreateIndirect` um das Dialogfeld aus einer Vorlage im Arbeitsspeicher zu erstellen.  
  
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
 Enthält eine Null-terminierte Zeichenfolge, die eine Dialogfeldvorlagen-Ressource im Dialogfeld heißt.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
 *nIDTemplate*  
 Enthält die ID einer Dialogfeldvorlagen-Ressource im Dialogfeld an.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei beiden Formen zurückgegeben ungleich NULL, wenn das Dialogfeld Erstellung und Initialisierung erfolgreich waren. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können den Aufruf von put `Create` in den Konstruktor oder rufen sie nach dem Konstruktor wird aufgerufen.  
  
 Zwei Formen von der `Create` Memberfunktion werden von Vorlagenamen oder der ID-Nummer für die Vorlage (z. B. "IDD_DIALOG1") für den Zugriff auf das Dialogfeld Dialogfeldvorlagen-Ressource bereitgestellt.  
  
 Übergeben Sie für eine der Formen einen Zeiger auf das Fenster des übergeordneten Objekts. Wenn *pParentWnd* ist **NULL**, mit seinem übergeordneten oder Besitzer-Fenster auf das Hauptanwendungsfenster festgelegt im Dialogfeld erstellt werden.  
  
 Die `Create` Memberfunktion sofort zurück, nachdem sie das Dialogfeld erstellt.  
  
 Verwenden der **WS_VISIBLE** in der Vorlage im Dialogfeld Format zuzuweisen, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow`. Weitere Dialogfeld-Stile und ihre Anwendung finden Sie in der [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Struktur im Windows SDK und [Fensterstile](../../mfc/reference/styles-used-by-mfc.md#window-styles) in der *MFC-Referenz*.  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt, indem die `Create` Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#62](../../mfc/codesnippet/cpp/cdialog-class_1.cpp)]  
  
##  <a name="createindirect"></a>  CDialog::CreateIndirect  
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
 *lpDialogTemplate*  
 Verweist auf Arbeitsspeicher, das Dialogfeld Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage wird in Form einer [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Struktur und Informationen, wie im Windows SDK beschrieben.  
  
 *pParentWnd*  
 Verweist auf das Dialogfeldobjekt übergeordnete Fensterobjekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)). Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
 *lpDialogInit*  
 Verweist auf eine **DLGINIT** Ressource.  
  
 *hDialogTemplate*  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld an. Diese Vorlage wird in Form einer **DLGTEMPLATE** Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeld erstellt und wurde erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `CreateIndirect` Memberfunktion sofort zurück, nachdem sie das Dialogfeld erstellt.  
  
 Verwenden der **WS_VISIBLE** in der Vorlage im Dialogfeld Format zuzuweisen, wenn das Dialogfeld angezeigt werden soll, wenn das übergeordnete Fenster erstellt wird. Andernfalls müssen Sie aufrufen `ShowWindow` darin angezeigt werden. Weitere Informationen, wie Sie andere Dialogfeld-Stile in der Vorlage angeben können, finden Sie unter der [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Struktur im Windows SDK.  
  
 Verwenden der `CWnd::DestroyWindow` Funktion zerstört ein Dialogfeld erstellt, indem die `CreateIndirect` Funktion.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten, erfordern zusätzliche Informationen in einem **DLGINIT** Ressource. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage um ein MFC-Dialogfeld mit einem ActiveX-Steuerelement zu erstellen." Knowledge Base-Artikeln finden Sie unter [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="domodal"></a>  Methode CDialog:: DoModal  
 Rufen Sie diese Memberfunktion zum Aufrufen des modalen Dialogfelds und die Dialogfeld-Ergebnis zurück.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **Int** Wert, der der Wert gibt an die *%nergebnis* zu übergebene Parameter der [CDialog::EndDialog](#enddialog) Memberfunktion, die verwendet wird, um das Dialogfeld zu schließen. Der Rückgabewert ist -1, wenn die Funktion nicht das Dialogfeld erstellt werden konnte oder **IDABORT** Wenn ein anderer Fehler aufgetreten ist, in diesem Fall das Fenster "Ausgabe" enthält Fehlerinformationen von [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion verarbeitet alle Interaktionen mit dem Benutzer, während das Dialogfeld aktiv ist. Dies ist, was die modales Dialogfeld. d. h. kann nicht der Benutzer mit anderen Fenstern interagieren, bis das Dialogfeld geschlossen wird.  
  
 Wenn der Benutzer eine der Schaltflächen im Dialogfeld, z. B. OK oder "Abbrechen", einer Nachrichtenhandler Memberfunktion, z. B. klickt [OnOK](#onok) oder [OnCancel](#oncancel), wird aufgerufen, um das Dialogfeld zu schließen. Die Standardeinstellung `OnOK` Memberfunktion wird überprüfen und aktualisieren Sie die Daten im Dialogfeld und schließen Sie das Dialogfeld mit dem Ergebnis **IDOK**, und der standardmäßige `OnCancel` Memberfunktion schließt das Dialogfeld mit dem Ergebnis  **IDCANCEL** ohne überprüfen oder Aktualisieren der Daten im Dialogfeld. Sie können diese Meldungshandler Funktionen zum Ändern des Verhaltens überschreiben.  
  
> [!NOTE]
> `PreTranslateMessage` wird jetzt für modalen Dialog Box-Nachrichtenverarbeitung aufgerufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#63](../../mfc/codesnippet/cpp/cdialog-class_2.cpp)]  
  
##  <a name="enddialog"></a>  CDialog::EndDialog  
 Rufen Sie diese Memberfunktion, um ein modales Dialogfeld zu beenden.  
  
```  
void EndDialog(int nResult);
```  
  
### <a name="parameters"></a>Parameter  
 *%nergebnis*  
 Enthält den Wert aus dem Dialogfeld an den Aufrufer des zurückzugebenden `DoModal`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion gibt *%nergebnis* als Rückgabewert von `DoModal`. Verwenden Sie die `EndDialog` Funktion zum Abschließen der Verarbeitung, wenn ein modales Dialogfeld erstellt wird.  
  
 Sie können Aufrufen `EndDialog` jederzeit selbst im [OnInitDialog](#oninitdialog), in diesem Fall sollten Sie schließen, bevor sie das Dialogfeld angezeigt wird oder bevor der Eingabefokus festgelegt wird.  
  
 `EndDialog` Das Dialogfeld wird nicht sofort geschlossen werden. Stattdessen wird ein Flag, das leitet das Dialogfeld zu schließen, sobald der aktuelle Message-Handler zurückgegeben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#64](../../mfc/codesnippet/cpp/cdialog-class_3.cpp)]  
  
 [!code-cpp[NVC_MFCControlLadenDialog#65](../../mfc/codesnippet/cpp/cdialog-class_4.cpp)]  
  
##  <a name="getdefid"></a>  CDialog::GetDefID  
 Rufen Sie die `GetDefID` Memberfunktion versucht, die das standardmäßige pushbutton-Steuerelement-ID für ein Dialogfeld zu erhalten.  
  
```  
DWORD GetDefID() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine 32-Bit-Wert ( `DWORD`). Wenn die standardmäßige Pushbutton einen ID-Wert aufweist, enthält das höherwertige Wort **DC_HASDEFID** und das niederwertige Wort enthält den ID-Wert. Wenn die standardmäßige Pushbutton nicht über ein ID-Wert verfügt, ist der Rückgabewert 0.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist normalerweise eine Schaltfläche "OK".  
  
##  <a name="gotodlgctrl"></a>  CDialog::GotoDlgCtrl  
 Verschiebt den Fokus auf das angegebene Steuerelement im Dialogfeld an.  
  
```  
void GotoDlgCtrl(CWnd* pWndCtrl);
```  
  
### <a name="parameters"></a>Parameter  
 *pWndCtrl*  
 Identifiziert das Fenster (Steuerelement), den Fokus erhält.  
  
### <a name="remarks"></a>Hinweise  
 Um einen Zeiger auf das Steuerelement zu übergeben (untergeordneten Fensters) *pWndCtrl*, rufen die `CWnd::GetDlgItem` Memberfunktion, die zurückgibt, einen Zeiger auf eine [CWnd](../../mfc/reference/cwnd-class.md) Objekt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [GetDlgItem](../../mfc/reference/cwnd-class.md#getdlgitem).  
  
##  <a name="initmodalindirect"></a>  DLGTEMPL  
 Rufen Sie diese Memberfunktion zum Initialisieren Sie ein modales Dialogfeld-Objekt, das mit einer Dialogfeld-Vorlage, die Sie im Arbeitsspeicher erstellen.  
  
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
 Verweist auf Arbeitsspeicher, das Dialogfeld Vorlage verwendet enthält, um das Dialogfeld zu erstellen. Diese Vorlage wird in Form einer [DLGTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms645394) Struktur und Informationen, wie im Windows SDK beschrieben.  
  
 *hDialogTemplate*  
 Enthält ein Handle für den globalen Arbeitsspeicher, die mit einer Vorlage im Dialogfeld an. Diese Vorlage wird in Form einer **DLGTEMPLATE** Struktur und die Daten für jedes Steuerelement im Dialogfeld.  
  
 *pParentWnd*  
 Verweist auf das übergeordnete oder Besitzer Fenster-Objekt (des Typs [CWnd](../../mfc/reference/cwnd-class.md)), der das Dialogfeldobjekt angehört. Ist er **NULL**, dem Dialogfeldobjekt übergeordnete Fenster auf das Hauptanwendungsfenster festgelegt ist.  
  
 *lpDialogInit*  
 Verweist auf eine **DLGINIT** Ressource.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Dialogfeldobjekt erstellt und wurde erfolgreich initialisiert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Um ein modales Dialogfeld indirekt zu erstellen, zunächst belegen einen Speicherblock auf dem globalen und mit der Dialogfeldvorlage gefüllt. Rufen Sie dann auf die leere `CDialog` Konstruktor, um das Dialogfeld-Objekt zu erstellen. Rufen Sie als Nächstes `InitModalIndirect` zum Speichern des Handles für die Vorlage in-Memory-Dialogfeld. Das Dialogfeld "Windows" wird erstellt und angezeigt höher, bei der [DoModal](#domodal) Memberfunktion aufgerufen wird.  
  
 Dialogfelder, die ActiveX-Steuerelemente enthalten, erfordern zusätzliche Informationen in einem **DLGINIT** Ressource. Weitere Informationen finden Sie im Knowledge Base-Artikel Q231591, "So wird's gemacht: verwenden eine Dialogvorlage um ein MFC-Dialogfeld mit einem ActiveX-Steuerelement zu erstellen." Knowledge Base-Artikeln finden Sie unter [ http://support.microsoft.com ](http://support.microsoft.com/).  
  
##  <a name="mapdialogrect"></a>  CDialog::MapDialogRect  
 Rufen Sie die Einheiten im Dialogfeld eines Rechtecks Bildschirm Einheiten zu konvertieren.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpRect*  
 Verweist auf eine [RECT](../../mfc/reference/rect-structure1.md) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) -Objekt, das das Dialogfeld enthält koordiniert, der konvertiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld Einheiten sind im Hinblick auf die aktuellen Dialogfeld-Basiseinheit abgeleitet wurde. die durchschnittliche Breite und Höhe der Zeichen in der Schriftart für Text im Dialogfeld angegeben. Eine horizontale Einheit ist ein Viertel der im Dialogfeld Basis-Breite Einheit, und eine vertikale Einheit ist ein Achtel des Geräts im Dialogfeld Basis Höhe.  
  
 Die **GetDialogBaseUnits** Windows-Funktion gibt Informationen zur Datenbankgröße für die Systemschriftart, aber Sie können eine andere Schriftart jedem Dialogfeld angeben, bei der Verwendung der **DS_SETFONT** Stil die Ressource-Definitionsdatei. Die `MapDialogRect` Windows-Funktion verwendet die passende Schriftart für das Dialogfeld zu öffnen.  
  
 Die `MapDialogRect` Memberfunktion ersetzt die Dialogfeld-Einheiten in *LpRect* mit Bildschirm Einheiten (in Pixel), damit das Rechteck zum Erstellen eines Dialogfelds oder positionieren ein Steuerelement innerhalb eines Felds verwendet werden kann.  
  
##  <a name="nextdlgctrl"></a>  CDialog::NextDlgCtrl  
 Verschiebt den Fokus zum nächsten Steuerelement im Dialogfeld an.  
  
```  
void NextDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Fokus auf das letzte Steuerelement im Dialogfeld befindet, wird in das erste Steuerelement verschoben.  
  
##  <a name="oncancel"></a>  CDialog::OnCancel  
 Das Framework ruft diese Methode auf, wenn der Benutzer klickt **"Abbrechen"** oder in einem Dialogfeld gebunden oder ungebunden die ESC-Taste drückt.  
  
```  
virtual void OnCancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode zum Ausführen von Aktionen (z. B. das Wiederherstellen von alten Daten) Wenn ein Benutzer das Dialogfeld schließt, indem Sie auf **"Abbrechen"** oder drücken die ESC-Taste. Die Standardeinstellung schließt ein modales Dialogfeld durch Aufruf von ["EndDialog"](#enddialog) und dadurch [DoModal](#domodal) IDCANCEL zurückgegeben.  
  
 Wenn Sie implementieren die **"Abbrechen"** Schaltfläche in ein nicht modales Dialogfeld, überschreiben Sie die `OnCancel` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Basisklasse-Methode nicht, da er aufruft `EndDialog`, dem wird das Dialogfeld ausgeblendet, jedoch nicht zu zerstören.  
  
> [!NOTE]
>  Diese Methode kann nicht überschrieben werden, bei der Verwendung einer `CFileDialog` Objekt in einem Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#66](../../mfc/codesnippet/cpp/cdialog-class_5.cpp)]  
  
##  <a name="oninitdialog"></a>  CDialog::  
 Diese Methode wird aufgerufen, als Antwort auf die `WM_INITDIALOG` Nachricht.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt an, ob die Anwendung den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde. Wenn `OnInitDialog` ungleich NULL zurückgegeben wird, wird Windows den Eingabefokus auf den Standardspeicherort, der das erste Steuerelement im Dialogfeld. Die Anwendung kann 0 zurückgeben, nur dann, wenn er explizit den Eingabefokus auf eines der Steuerelemente im Dialogfeld festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Sendet Windows die `WM_INITDIALOG` Nachricht auf das Dialogfeld während der [erstellen](#create), [CreateIndirect](#createindirect), oder [DoModal](#domodal) -Aufrufe, die auftreten, unmittelbar bevor das Dialogfeld wird angezeigt.  
  
 Überschreiben Sie diese Methode, wenn Sie besondere Bearbeitung beim Initialisieren des Dialogfelds ausführen möchten. In der überschriebenen Version, rufen Sie zuerst die Basisklasse `OnInitDialog` aber ignorieren Sie den Rückgabewert. In der Regel wird nun wieder `TRUE` aus Ihrer außer Kraft gesetzte Methode.  
  
 Windows-Aufrufe der `OnInitDialog` Funktion mithilfe der globalen-Standarddialogfeld-Prozedur, die häufig für alle Dialogfelder für die Microsoft Foundation Class-Bibliothek. Diese Funktion über die meldungszuordnung wird nicht aufgerufen, und Sie benötigen daher keinen Meldungszuordnungseintrag für diese Methode.  
  
> [!NOTE]
> Diese Methode kann nicht überschrieben werden, bei der Verwendung einer `CFileDialog` Objekt in einem Programm, das unter Windows Vista oder höher kompiliert wird. Weitere Informationen zu Änderungen an `CFileDialog` unter Windows Vista und höheren Versionen finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#67](../../mfc/codesnippet/cpp/cdialog-class_6.cpp)]  
  
##  <a name="onok"></a>  CDialog::OnOK  
 Wird aufgerufen, wenn der Benutzer klickt auf die **OK** Schaltfläche (die Schaltfläche mit einer ID IDOK).  
  
```  
virtual void OnOK();
```  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, um Aktionen durchzuführen, wenn die **OK** Schaltfläche aktiviert ist. Wenn das Dialogfeld Automatische datenvalidierung und Exchange enthält, wird die standardmäßige Implementierung dieser Methode überprüft der Dialogfelddaten, und der entsprechenden Variablen in der Anwendung aktualisiert.  
  
 Wenn Sie implementieren die **OK** Schaltfläche in ein nicht modales Dialogfeld, überschreiben Sie die `OnOK` Methode, und rufen [DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow) darin. Rufen Sie die Basisklasse-Methode nicht, da er aufruft ["EndDialog"](#enddialog) die unsichtbar des Dialogfelds "", jedoch nicht zerstört.  
  
> [!NOTE]
>  Diese Methode kann nicht überschrieben werden, bei der Verwendung einer `CFileDialog` Objekt in einem Programm, das unter Windows XP kompiliert wird. Weitere Informationen zu `CFileDialog`, finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCControlLadenDialog#68](../../mfc/codesnippet/cpp/cdialog-class_7.cpp)]  
  
##  <a name="onsetfont"></a>  CDialog::OnSetFont  
 Gibt die Schriftart, die ein Dialogfeld-Steuerelement beim Zeichnen von Text verwendet wird.  
  
```  
Virtual void OnSetFont(CFont* pFont);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pFont*  
 Gibt einen Zeiger auf die Schriftart, die für alle Steuerelemente in diesem Dialogfeld als Standardschriftart verwendet werden.  
  
### <a name="remarks"></a>Hinweise  
 Das Dialogfeld wird die angegebene Schriftart als Standard für alle Steuerelemente verwenden.  
  
 Dialog-Editor wird die im Dialogfeld-Schriftart in der Regel als Teil der Dialogfeldvorlagen-Ressource im Dialogfeld.  
  
> [!NOTE]
> Diese Methode kann nicht überschrieben werden, bei der Verwendung einer `CFileDialog` Objekt in einem Programm, das unter Windows Vista oder höher kompiliert wird. Weitere Informationen zu Änderungen an `CFileDialog` unter Windows Vista und höheren Versionen finden Sie unter [CFileDialog-Klasse](../../mfc/reference/cfiledialog-class.md).  
  
##  <a name="prevdlgctrl"></a>  CDialog::PrevDlgCtrl  
 Legt den Fokus zum vorherigen Steuerelement im Dialogfeld fest.  
  
```  
void PrevDlgCtrl() const;  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn der Fokus auf das erste Steuerelement im Dialogfeld befindet, wird bis zum letzten Steuerelement im Feld verschoben.  
  
##  <a name="setdefid"></a>  CDialog::SetDefID  
 Ändert das standardmäßige pushbutton-Steuerelement für ein Dialogfeld an.  
  
```  
void SetDefID(UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 *nID*  
 Gibt die ID des pushbutton-Steuerelements, die standardmäßig verwendet wird.  
  
##  <a name="sethelpid"></a>  CDialog::SetHelpID  
 Legt eine kontextbezogene Hilfe-ID für das Dialogfeld.  
  
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

