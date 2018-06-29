---
title: CPageSetupDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CPageSetupDialog
- AFXDLGS/CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CPageSetupDialog
- AFXDLGS/CPageSetupDialog::CreatePrinterDC
- AFXDLGS/CPageSetupDialog::DoModal
- AFXDLGS/CPageSetupDialog::GetDeviceName
- AFXDLGS/CPageSetupDialog::GetDevMode
- AFXDLGS/CPageSetupDialog::GetDriverName
- AFXDLGS/CPageSetupDialog::GetMargins
- AFXDLGS/CPageSetupDialog::GetPaperSize
- AFXDLGS/CPageSetupDialog::GetPortName
- AFXDLGS/CPageSetupDialog::OnDrawPage
- AFXDLGS/CPageSetupDialog::PreDrawPage
- AFXDLGS/CPageSetupDialog::m_psd
dev_langs:
- C++
helpviewer_keywords:
- CPageSetupDialog [MFC], CPageSetupDialog
- CPageSetupDialog [MFC], CreatePrinterDC
- CPageSetupDialog [MFC], DoModal
- CPageSetupDialog [MFC], GetDeviceName
- CPageSetupDialog [MFC], GetDevMode
- CPageSetupDialog [MFC], GetDriverName
- CPageSetupDialog [MFC], GetMargins
- CPageSetupDialog [MFC], GetPaperSize
- CPageSetupDialog [MFC], GetPortName
- CPageSetupDialog [MFC], OnDrawPage
- CPageSetupDialog [MFC], PreDrawPage
- CPageSetupDialog [MFC], m_psd
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd96f0240f8dd97fdda54fd2d00231db14ae3d47
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079182"
---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog-Klasse
Kapselt die Dienste, die durch das allgemeine Windows-OLE-Dialogfeld "Seiteneinrichtung" bereitgestellt werden, zusammen mit zusätzlicher Unterstützung für das Festlegen und Ändern von Druckrändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Erstellt ein `CPageSetupDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext für das Drucken.|  
|[CPageSetupDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht eine Gruppenauswahl, auf die Benutzer stellen.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Gibt den Gerätenamen des Druckers zurück.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Gibt das aktuelle `DEVMODE` des Druckers.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Gibt den Drucker verwendeten Treibers zurück.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Gibt die aktuellen Randeinstellungen des Druckers zurück.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Gibt das Papierformat des Druckers zurück.|  
|[CPageSetupDialog::GetPortName](#getportname)|Gibt den Namen der Ausgabe-Port zurück.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Wird aufgerufen, durch das Framework eine Bildschirmaufnahme einer gedruckten Seite gerendert.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Vom Framework aufgerufen, bevor Sie eine Bildschirmaufnahme einer gedruckten Seite rendern.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Eine Struktur, die zum Anpassen einer `CPageSetupDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse dient zur des Dialogfelds drucken Setup stattfinden.  
  
 Verwenden einer `CPageSetupDialog` Objekt, erstellen Sie zunächst das Objekt mit dem `CPageSetupDialog` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der `m_psd` Datenmember der Werte von Steuerelementen für das Dialogfeld zu initialisieren. Die [M_psd](#m_psd) Struktur ist vom Typ **PAGESETUPDLG**.  
  
 Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und die Benutzer Druckoptionen auszuwählen. `DoModal` Gibt zurück, ob der Benutzer die OK ausgewählt ( **IDOK**) oder "Abbrechen" ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, können Sie einige der `CPageSetupDialog`des Memberfunktionen oder den Zugriff der `m_psd` Datenmember Eingabe von Informationen vom Benutzer abgerufen.  
  
> [!NOTE]
>  Nachdem das Standarddialogfeld OLE-Seiteneinrichtung geschlossen wird, werden vom Benutzer vorgenommene Änderungen nicht durch das Framework gespeichert werden. Es ist Aufgabe der Anwendung für alle Werte in diesem Dialogfeld an einem dauerhaften Speicherort, z. B. Mitglied der Anwendung Dokument oder Anwendungsklasse zu speichern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cpagesetupdialog"></a>  CPageSetupDialog::CPageSetupDialog  
 Mit dieser Funktion wird zum Erstellen einer `CPageSetupDialog` Objekt.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *dwFlags*  
 Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen im Dialogfeld Anpassen. Die Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:  
  
- **PSD_DEFAULTMINMARGINS** legt die minimale zulässige Stärke für die Seitenränder an den Drucker Mindestwerte identisch sein. Dieses Flag wird ignoriert, wenn die **PSD_MARGINS** und **PSD_MINMARGINS** Flags sind ebenfalls angegeben.  
  
- **PSD_INWININIINTLMEASURE** nicht implementiert.  
  
- **PSD_MINMARGINS** bewirkt, dass das System verwendet die im angegebenen Werte die **RtMinMargin** Member als die minimale zulässige Stärke für die Links, oben, rechts und unteren Rand. Das System verhindert, dass den Benutzer, die kleiner als die angegebene minimale Breite eingeben. Wenn **PSD_MINMARGINS** nicht angegeben wird, setzt das System die minimale zulässige Breite den zulässigen vom Drucker.  
  
- **PSD_MARGINS** den Randbereich für das Steuerelement aktiviert.  
  
- **PSD_INTHOUSANDTHSOFINCHES** bewirkt, dass die Einheiten im Dialogfeld in 1/1000 Zoll gemessen werden.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** bewirkt, dass die Einheiten im Dialogfeld in 1/100 Millimetern gemessen werden.  
  
- **PSD_DISABLEMARGINS** deaktiviert den Rand Dialogfeld-Steuerelemente.  
  
- **PSD_DISABLEPRINTER** deaktiviert die Schaltfläche "Drucker".  
  
- **PSD_NOWARNING** verhindert, dass die Warnung wird angezeigt, wenn kein Standarddrucker ist.  
  
- **PSD_DISABLEORIENTATION** wird die Seite Ausrichtung Dialogfeld-Steuerelement deaktiviert.  
  
- **PSD_RETURNDEFAULT** bewirkt, dass `CPageSetupDialog` zurückzugebenden [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen, die für den System-Standarddrucker initialisiert werden, ohne dass ein Dialogfeld angezeigt. Es wird angenommen, dass beide **hDevNames** und **hDevMode-Feld** sind **NULL**ist, andernfalls die Funktion gibt einen Fehler zurück. Wenn das System als Standarddrucker durch einen alten Druckertreiber (früher als Windows-Version 3.0), unterstützt wird nur **hDevNames** zurückgegeben. **hDevMode-Feld** ist **NULL**.  
  
- **PSD_DISABLEPAPER** Papier-Auswahlsteuerelement deaktiviert.  
  
- **PSD_SHOWHELP** bewirkt, dass im Dialogfeld die Schaltfläche "Hilfe" anzuzeigen. Die **HwndOwner** Element darf nicht sein **NULL** Wenn dieses Flag angegeben ist.  
  
- **PSD_ENABLEPAGESETUPHOOK** ermöglicht die Hookfunktion im angegebenen **LpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** weist das Betriebssystem, um das Dialogfeld zu erstellen, mithilfe der Dialogfelds "Vorlage" identifizierte **hInstance** und **LpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** gibt an, dass **hInstance** identifiziert einen Datenblock, der eine vorab geladene Dialogfeldvorlage enthält. Das System ignoriert **LpSetupTemplateName** Wenn dieses Flag angegeben ist.  
  
- **PSD_ENABLEPAGEPAINTHOOK** ermöglicht die Hookfunktion im angegebenen **LpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** deaktiviert den Draw-Bereich des Dialogfelds.  
  
 *pParentWnd*  
 Ein Zeiger auf den übergeordneten oder den Besitzer des Dialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [DoModal](../../mfc/reference/cdialog-class.md#domodal) Funktion, um das Dialogfeld anzuzeigen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#94](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>  CPageSetupDialog::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext (DC).  
  
##  <a name="domodal"></a>  CPageSetupDialog::DoModal  
 Mit dieser Funktion wird für die Anzeige von OLE-Seiteneinrichtung-Standarddialogfeld Windows und die Benutzer verschiedene drucken Setupoptionen wie Druckränder, Größe und Ausrichtung der Papier und Zieldrucker auszuwählen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um festzustellen, ob ein Fehler aufgetreten.  
  
 **IDOK** und **IDCANCEL** sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder "Abbrechen" ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Darüber hinaus kann der Benutzer die Drucker-Setup-Optionen, z. B. die Netzwerkadresse und Eigenschaften, die spezifisch für den ausgewählten Drucker zugreifen.  
  
 Wenn Sie die verschiedenen Optionen der Seite Setup-Dialogfeld zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_psd` -Struktur, sollten Sie dies tun, vor dem Aufruf `DoModal`, und nach das Dialogfeldobjekt erstellt wird. Nach dem Aufruf `DoModal`, rufen Sie andere Memberfunktionen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
 Wenn Sie die aktuellen Einstellungen, die vom Benutzer eingegebenen weitergeben möchten, stellen Sie einen Aufruf von [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Diese Funktion nimmt die Informationen aus der `CPageSetupDialog` -Objekt und initialisiert und wählt einen neuen Drucker DC mit den entsprechenden Attributen.  
  
 [!code-cpp[NVC_MFCDocView#95](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="getdevicename"></a>  CPageSetupDialog::GetDeviceName  
 Mit dieser Funktion werden nach `DoModal` den Namen des aktuell ausgewählten Druckers abzurufenden.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des Laufwerks verwendet werden, indem die `CPageSetupDialog` Objekt.  
  
##  <a name="getdevmode"></a>  CPageSetupDialog::GetDevMode  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen von Informationen zu den Druckergerätekontext von der `CPageSetupDialog` Objekt.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Sie müssen den Arbeitsspeicher, bis diese Struktur mit dem Windows Entsperren [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die im Windows SDK beschrieben wird.  
  
##  <a name="getdrivername"></a>  CPageSetupDialog::GetDriverName  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie einen Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getmargins"></a>  CPageSetupDialog::GetMargins  
 Mit dieser Funktion wird nach einem Aufruf von `DoModal` die Ränder des Druckertreibers Gerät abrufen.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectMargins*  
 Zeiger auf eine [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das (in 1/1000 Zoll oder 1/100 mm) die Druckränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie **NULL** für diesen Parameter, wenn Sie nicht in dieses Rechteck interessiert sind.  
  
 *lpRectMinMargins*  
 Zeiger auf eine `RECT` Struktur oder `CRect` Objekt, das (in 1/1000 Zoll oder 1/100 mm) die minimalen Druckränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie **NULL** für diesen Parameter, wenn Sie nicht in dieses Rechteck interessiert sind.  
  
##  <a name="getpapersize"></a>  CPageSetupDialog::GetPaperSize  
 Mit dieser Funktion wird zum Abrufen der Größe der in diesem Dokument für den Druck ausgewählt.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Größe des Papiers (in 1/1000 Zoll oder 1/100 mm) für den Druck ausgewählt.  
  
##  <a name="getportname"></a>  CPageSetupDialog::GetPortName  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` , den Namen des aktuell ausgewählten Drucker Ports abzurufen.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker Ports.  
  
##  <a name="m_psd"></a>  CPageSetupDialog::m_psd  
 Eine Struktur des Typs **PAGESETUPDLG**, zu speichern, deren Mitglieder die Merkmale des Dialog-Objekts.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPageSetupDialog` -Objekt können Sie `m_psd` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Memberfunktion.  
  
 Wenn Sie ändern die `m_psd` Datenmember direkt, Sie Standardverhalten überschreiben.  
  
 Weitere Informationen zu den [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) -Struktur, finden Sie im Windows SDK.  
  
 Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="ondrawpage"></a>  CPageSetupDialog::OnDrawPage  
 Wird aufgerufen, durch das Framework eine Bildschirmaufnahme einer gedruckten Seite gezeichnet werden soll.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 *pDC*  
 Ein Zeiger auf den Druckergerätekontext.  
  
 *nMeldung*  
 Gibt eine Meldung an, den Bereich der Seite, die gerade gezeichnet wird. Einer der folgenden Werte ist möglich:  
  
- **WM_PSD_FULLPAGERECT** den gesamten Bereich.  
  
- **WM_PSD_MINMARGINRECT** aktuelle Mindestwerte.  
  
- **WM_PSD_MARGINRECT** aktuelle Ränder.  
  
- **WM_PSD_GREEKTEXTRECT** Inhalt der Seite.  
  
- **WM_PSD_ENVSTAMPRECT** Bereich für eine Darstellung Briefmarke reserviert.  
  
- **WM_PSD_YAFULLPAGERECT** Bereich für eine Rückgabeadresse-Darstellung. Dieser Bereich erstreckt sich an den Rändern der Seite im Bereich Beispiel.  
  
 *lpRect*  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) oder [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) Objekt, das die Koordinaten des Zeichenbereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn behandelt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Bild wird dann als Teil der OLE-Seiteneinrichtung Standarddialogfeld angezeigt. Die standardmäßige Implementierung zeichnet ein Bild von einer Seite des Texts.  
  
 Überschreiben Sie diese Funktion, um das Zeichnen von einem bestimmten Bereich des Bilds oder das gesamte Bild anzupassen. Sie erreichen dies, indem eine **wechseln** -Anweisung mit **Fall** Anweisungen, die Überprüfung des Werts der *nMeldung*. Um das Rendern des Inhalts der Seite, Bild anzupassen, verwenden Sie z. B. den folgende Beispielcode:  
  
 [!code-cpp[NVC_MFCDocView#96](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Beachten Sie, dass Sie nicht benötigen, behandeln jede Groß-/Kleinschreibung *nMeldung*. Sie können auswählen, um eine Komponente des Bilds, mehrere Komponenten des Bilds oder den gesamten Bereich zu behandeln.  
  
##  <a name="predrawpage"></a>  CPageSetupDialog::PreDrawPage  
 Vom Framework aufgerufen, bevor das Bild der gedruckten Seite zeichnen.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Parameter  
 *wPaper*  
 Gibt einen Wert, der das Papierformat angibt. Dieser Wert kann eine von der **DMPAPER_** Werte aufgeführt, in der Beschreibung des der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur.  
  
 *wFlags*  
 Gibt die Ausrichtung des Papiers oder des Umschlags, und gibt an, ob der Drucker einen Matrix- oder HPPCL (Hewlett-Packard Printer Control Language)-Gerät ist. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
-   0 x 001 Papier im Querformat (Punkt Matrix)  
  
-   0 x 003 Papier im Querformat (HPPCL)  
  
-   0x005 Papier im Hochformat (Punkt Matrix)  
  
-   0x007 Papier im Hochformat (HPPCL)  
  
-   0x00b Umschlag im Querformat (HPPCL)  
  
-   0x00d Umschlag im Hochformat (Punkt Matrix)  
  
-   0x019 Umschlag im Querformat (Punkt Matrix)  
  
-   0x01f Umschlag im Hochformat (Punkt Matrix)  
  
 *pPSD*  
 Zeiger auf eine **PAGESETUPDLG** Struktur. Weitere Informationen zu [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), finden Sie im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn behandelt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um die Zeichnens des Bildes anpassen. Wenn Sie diese Funktion zu überschreiben und zurückkehren **"true"**, müssen Sie das gesamte Bild gezeichnet. Wenn Sie diese Funktion zu überschreiben und zurückkehren **"false"**, durch das Framework das gesamte Standardbild gezeichnet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



