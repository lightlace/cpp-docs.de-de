---
title: Klasse CPageSetupDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPageSetupDialog
dev_langs:
- C++
helpviewer_keywords:
- page setup
- Print Setup dialog box
- Page Setup dialog box
- OLE Page Setup dialog box
- CPageSetupDialog class
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
caps.latest.revision: 24
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
ms.openlocfilehash: 81d36b3a005a291aca4c77dc9771a4fe92c304ee
ms.lasthandoff: 02/24/2017

---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog-Klasse
Kapselt die Dienste, die durch das allgemeine Windows-OLE-Dialogfeld "Seiteneinrichtung" bereitgestellt werden, zusammen mit zusätzlicher Unterstützung für das Festlegen und Ändern von Druckrändern.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Erstellt ein `CPageSetupDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext für das Drucken.|  
|[CPageSetupDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer stellen eine Auswahl.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Gibt den Gerätenamen des Druckers.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Gibt die aktuelle `DEVMODE` des Druckers.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Gibt den vom Drucker verwendeten Treiber.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Gibt die aktuellen Randeinstellungen des Druckers.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Gibt das Papierformat des Druckers.|  
|[CPageSetupDialog::GetPortName](#getportname)|Gibt den Namen der Ausgabe-Ports.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Aufgerufen, um eine Bildschirmgrafik einer gedruckten Seite zu rendern.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Wird vom Framework aufgerufen, bevor eine Bildschirmgrafik einer gedruckten Seite.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Eine Struktur, die zur Anpassung einer `CPageSetupDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse soll die Stelle im Dialogfeld Seite einrichten.  
  
 Verwenden einer `CPageSetupDialog` Objekt erstellen Sie zunächst das Objekt mit dem `CPageSetupDialog` Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der `m_psd` -Datenmember auf die Werte der Steuerelemente des Dialogfelds zu initialisieren. Die [M_psd](#m_psd) Struktur ist vom Typ **PAGESETUPDLG**.  
  
 Rufen Sie nach dem initialisieren die Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. `DoModal`Gibt zurück, ob der Benutzer OK ausgewählt ( **IDOK**) oder Abbrechen ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, können Sie mehrere `CPageSetupDialog`Memberfunktionen oder den Zugriff der `m_psd` Datenmember zum Abrufen von Informationen vom Benutzer eingegebenen.  
  
> [!NOTE]
>  Nachdem das Dialogfeld allgemeine OLE-Seitenformat ausgeblendet wird, werden alle vom Benutzer vorgenommenen Änderungen nicht vom Framework gespeichert. Es ist Aufgabe der Anwendung auf alle Werte in diesem Dialogfeld an einem permanenten Speicherort, z. B. Mitglied der Anwendung Dokument oder Anwendungsklasse zu speichern.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="a-namecpagesetupdialoga--cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 Rufen Sie diese Funktion zum Erstellen einer `CPageSetupDialog` Objekt.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen im Dialogfeld Anpassen. Die Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:  
  
- **PSD_DEFAULTMINMARGINS** legt die minimale zulässige Breite für die Seitenränder des Druckers Mindestwerte identisch sein. Dieses Flag wird ignoriert, wenn die **PSD_MARGINS** und **PSD_MINMARGINS** Flags werden ebenfalls angegeben.  
  
- **PSD_INWININIINTLMEASURE** nicht implementiert.  
  
- **PSD_MINMARGINS** bewirkt, dass das System mit den Angaben in der **RtMinMargin** Element als die zulässige Mindestbreite für die Links, oben, rechten und unteren Rand. Das System verhindert, dass den Benutzer, die kleiner als die angegebene minimale Breite eingeben. Wenn **PSD_MINMARGINS** nicht angegeben wird, setzt das System die zulässige Mindestbreite gemäß den Drucker.  
  
- **PSD_MARGINS** den Randbereich für das Steuerelement aktiviert.  
  
- **PSD_INTHOUSANDTHSOFINCHES** führt dazu, dass die Einheiten des Dialogfelds in 1/1000 Zoll gemessen wird.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** führt dazu, dass die Einheiten des Dialogfelds in 1/100 Millimeter gemessen wird.  
  
- **PSD_DISABLEMARGINS** Rand Dialogfeldsteuerelemente deaktiviert.  
  
- **PSD_DISABLEPRINTER** deaktiviert die Schaltfläche Drucker.  
  
- **PSD_NOWARNING** verhindert, dass die Warnung angezeigt wird, wenn kein Standarddrucker ist.  
  
- **PSD_DISABLEORIENTATION** wird die Seite Ausrichtung Dialogfeld-Steuerelement deaktiviert.  
  
- **PSD_RETURNDEFAULT** bewirkt, dass `CPageSetupDialog` zurückzugebenden [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen, die für den System-Standarddrucker initialisiert werden, ohne dass ein Dialogfeld angezeigt. Es wird davon ausgegangen, dass beide **hDevNames** und **hDevMode-Feld** sind **NULL**ist, andernfalls die Funktion einen Fehler zurück. Wenn der Standarddrucker des Systems von einer alten Druckertreiber (früher als Windows-Version 3.0) unterstützt wird nur **hDevNames** zurückgegeben. **hDevMode** is **NULL**.  
  
- **PSD_DISABLEPAPER** wird das Papier Auswahl-Steuerelement deaktiviert.  
  
- **PSD_SHOWHELP** führt dazu, dass das Dialogfeld die Schaltfläche Hilfe anzuzeigen. Die **HwndOwner** Element sein **NULL** Wenn dieses Flag angegeben ist.  
  
- **PSD_ENABLEPAGESETUPHOOK** ermöglicht die Hookfunktion im angegebenen **LpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** bewirkt, dass das Betriebssystem So erstellen Sie das Dialogfeld Vorlage im Dialogfeld identifizierten **hInstance** und **LpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** gibt an, dass **hInstance** bezeichnet einen Datenblock, der eine vorab geladenen Dialogfeldvorlage enthält. Das System ignoriert **LpSetupTemplateName** Wenn dieses Flag angegeben ist.  
  
- **PSD_ENABLEPAGEPAINTHOOK** ermöglicht die Hookfunktion im angegebenen **LpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** Bereich zeichnen im Dialogfeld deaktiviert.  
  
 `pParentWnd`  
 Ein Zeiger auf des Dialogfelds über- oder Besitzer.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [DoModal](../../mfc/reference/cdialog-class.md#domodal) Funktion, um das Dialogfeld anzuzeigen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#94;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="a-namecreateprinterdca--cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext (DC).  
  
##  <a name="a-namedomodala--cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupDialog::DoModal  
 Rufen Sie diese Funktion zeigt das Dialogfeld allgemeine OLE-Seitenformat Windows und dem Benutzer ermöglichen, verschiedene Einrichtungsoptionen wie Druckränder, Größe und Ausrichtung der Papier und Zieldrucker auswählen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
 **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
### <a name="remarks"></a>Hinweise  
 Darüber hinaus kann der Benutzer die Drucker-Setup-Optionen, wie z. B. die Netzwerkadresse und spezielle Eigenschaften für den ausgewählten Drucker zugreifen.  
  
 Wenn Sie die verschiedenen Optionen der Seite Setup-Dialogfeld zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_psd` -Struktur, sollten Sie dies tun, vor dem Aufruf von `DoModal`, und nach dem Dialogobjekt erstellt wird. Nach dem Aufruf von `DoModal`, andere Memberfunktionen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld aufrufen.  
  
 Wenn Sie die aktuellen Einstellungen, die vom Benutzer eingegebenen weitergeben möchten, stellen Sie einen Aufruf von [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Diese Funktion verwendet die Informationen aus der `CPageSetupDialog` -Objekt und initialisiert und wählt einen neuen Drucker DC mit den richtigen Attributen.  
  
 [!code-cpp[NVC_MFCDocView&#95;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="a-namegetdevicenamea--cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 Rufen Sie diese Funktion nach `DoModal` zum Abrufen des Namens des ausgewählten Druckers.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Gerätename, die von der **CPageSetupDialog** Objekt.  
  
##  <a name="a-namegetdevmodea--cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zum Abrufen von Informationen über den Drucker-Gerätekontext, der die `CPageSetupDialog` Objekt.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Entsperren Sie den Arbeitsspeicher, die von dieser Struktur mit dem Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdrivernamea--cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetmarginsa--cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupDialog::GetMargins  
 Mit dieser Funktion wird nach einem Aufruf von `DoModal` die Ränder der Druckertreiber abgerufen.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *lpRectMargins*  
 Zeiger auf eine [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) Struktur oder [CRect](../../atl-mfc-shared/reference/crect-class.md) Objekt, das (in 1/1000 Zoll oder 1/100 mm) die Seitenränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie **NULL** für diesen Parameter, wenn Sie nicht in das Rechteck relevant sind.  
  
 *lpRectMinMargins*  
 Zeiger auf eine `RECT` Struktur oder `CRect` -Objekt, das (in 1/1000 Zoll oder 1/100 mm) die minimalen Seitenränder für den aktuell ausgewählten Drucker beschreibt. Übergeben Sie **NULL** für diesen Parameter, wenn Sie nicht in das Rechteck relevant sind.  
  
##  <a name="a-namegetpapersizea--cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 Rufen Sie diese Funktion zum Abrufen der Papiergröße für den Druck ausgewählt.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CSize](../../atl-mfc-shared/reference/csize-class.md) Objekt, das die Größe des Papiers (in 1/1000 Zoll oder 1/100 mm) für den Druck ausgewählt.  
  
##  <a name="a-namegetportnamea--cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupDialog::GetPortName  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zum Abrufen des Namens des derzeit ausgewählten Ports.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Ports.  
  
##  <a name="a-namempsda--cpagesetupdialogmpsd"></a><a name="m_psd"></a>CPageSetupDialog::m_psd  
 Eine Struktur vom Typ **PAGESETUPDLG**, zu speichern, deren Mitglieder die Merkmale des Dialog-Objekts.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPageSetupDialog` -Objekt können Sie `m_psd` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Member-Funktion.  
  
 Wenn Sie ändern die `m_psd` Datenmember direkt Standardverhalten überschreiben.  
  
 Weitere Informationen zu den [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) -Struktur, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Siehe das Beispiel für [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="a-nameondrawpagea--cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 Aufgerufen, um eine Bildschirmgrafik einer gedruckten Seite zu zeichnen.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Parameter  
 `pDC`  
 Ein Zeiger auf den Drucker-Gerätekontext.  
  
 `nMessage`  
 Gibt eine Meldung an, den Bereich der Seite, die gerade gezeichnet wird. Einer der folgenden Werte ist möglich:  
  
- **WM_PSD_FULLPAGERECT** Bereich ganze Seite.  
  
- **WM_PSD_MINMARGINRECT** aktuelle Mindestwerte.  
  
- **WM_PSD_MARGINRECT** aktuelle Ränder.  
  
- **WM_PSD_GREEKTEXTRECT** Inhalt der Seite.  
  
- **WM_PSD_ENVSTAMPRECT** Bereich für eine Darstellung der Verpackung Stempel reserviert.  
  
- **WM_PSD_YAFULLPAGERECT** Bereich für eine Absenderadresse Darstellung. In diesem Bereich werden an den Rändern des Seitenbereichs Beispiel erweitert.  
  
 `lpRect`  
 Zeiger auf eine [CRect](../../atl-mfc-shared/reference/crect-class.md) oder [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) Objekt, das die Koordinaten des Zeichenbereichs enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich null behandelt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Dieses Bild wird dann als Teil der OLE-Seitenformat Standarddialogfeld angezeigt. Die standardmäßige Implementierung zeichnet ein Bild von einer Textseite.  
  
 Überschreiben Sie diese Funktion, um das Zeichnen des Bilds oder das gesamte Bild eines bestimmten Bereichs angepasst. Sie erreichen dies, indem eine `switch` -Anweisung mit **Fall** Anweisungen, die den Wert der `nMessage`. Um das Rendering des Inhalts der Seite anzupassen, verwenden Sie z. B. den folgenden Code:  
  
 [!code-cpp[NVC_MFCDocView&#96;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Beachten Sie, dass Sie nicht alle vom behandeln müssen `nMessage`. Sie können auch eine Komponente des Bilds, das Bild oder die ganze Fläche mehrere Komponenten behandelt.  
  
##  <a name="a-namepredrawpagea--cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 Vom Framework aufgerufen, bevor das Bild der gedruckten Seite gezeichnet.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Parameter  
 *wPaper*  
 Gibt einen Wert, der das Papierformat angibt. Dieser Wert kann eine der der **DMPAPER_** Werte aufgeführt, in der Beschreibung der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Struktur.  
  
 `wFlags`  
 Gibt die Ausrichtung des Papiers oder des Umschlags, und gibt an, ob der Drucker einen Matrix- oder HPPCL (Hewlett-Packard Printer Control Language)-Gerät ist. Dieser Parameter kann einen der folgenden Werte aufweisen:  
  
-   0 x&001; Papier im Querformat (Punkt Matrix)  
  
-   0 x&003; Papier im Querformat (HPPCL)  
  
-   0x005 Papier im Hochformat (Punkt Matrix)  
  
-   0x007 Papier im Hochformat (HPPCL)  
  
-   0x00b Umschlag im Querformat (HPPCL)  
  
-   0x00d Umschlag im Hochformat (Punkt Matrix)  
  
-   0x019 Umschlag im Querformat (Punkt Matrix)  
  
-   0x01f Umschlag im Hochformat (Punkt Matrix)  
  
 `pPSD`  
 Zeiger auf eine **PAGESETUPDLG** Struktur. Weitere Informationen zu [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich null behandelt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Funktion, um das Zeichnen des Bilds angepasst. Wenn Sie diese Funktion zum Überschreiben und wieder **TRUE**, müssen Sie das gesamte Bild zeichnen. Wenn Sie diese Funktion zum Überschreiben und wieder **FALSE**, das gesamte Standardbild von Rahmen gezeichnet wird.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel WORDPAD](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




