---
title: Klasse CPrintDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialog
- AFXDLGS/CPrintDialog
- AFXDLGS/CPrintDialog::CPrintDialog
- AFXDLGS/CPrintDialog::CreatePrinterDC
- AFXDLGS/CPrintDialog::DoModal
- AFXDLGS/CPrintDialog::GetCopies
- AFXDLGS/CPrintDialog::GetDefaults
- AFXDLGS/CPrintDialog::GetDeviceName
- AFXDLGS/CPrintDialog::GetDevMode
- AFXDLGS/CPrintDialog::GetDriverName
- AFXDLGS/CPrintDialog::GetFromPage
- AFXDLGS/CPrintDialog::GetPortName
- AFXDLGS/CPrintDialog::GetPrinterDC
- AFXDLGS/CPrintDialog::GetToPage
- AFXDLGS/CPrintDialog::PrintAll
- AFXDLGS/CPrintDialog::PrintCollate
- AFXDLGS/CPrintDialog::PrintRange
- AFXDLGS/CPrintDialog::PrintSelection
- AFXDLGS/CPrintDialog::m_pd
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- Print dialog box
- CPrintDialog class
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
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
ms.openlocfilehash: fe8b5a899169bf9dfd463278100384fde900a6a0
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialog-class"></a>CPrintDialog-Klasse
Kapselt die Dienste, die vom allgemeinen Windows-Dialogfeld für das Drucken bereitgestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|Erstellt ein `CPrintDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext ohne das Dialogfeld Drucken.|  
|[CPrintDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CPrintDialog::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|  
|[CPrintDialog::GetDefaults](#getdefaults)|Ruft die Standardeinstellungen des ohne Anzeige eines Dialogfelds ab.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|Ruft den Namen des ausgewählten Druckers.|  
|[CPrintDialog::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|  
|[CPrintDialog::GetDriverName](#getdrivername)|Ruft den Namen des aktuell ausgewählten Druckertreiber.|  
|[CPrintDialog::GetFromPage](#getfrompage)|Ruft die erste Seite des Druckbereichs ab.|  
|[CPrintDialog::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Ports.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Gerätekontext ab.|  
|[CPrintDialog::GetToPage](#gettopage)|Ruft die letzte Seite des Druckbereichs ab.|  
|[CPrintDialog::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt.|  
|[CPrintDialog::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialog::PrintRange](#printrange)|Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.|  
|[CPrintDialog::PrintSelection](#printselection)|Bestimmt, ob nur die ausgewählten Elemente zu drucken.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|Eine Struktur, die zur Anpassung einer `CPrintDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Allgemeine drucken Dialogfelder bieten eine einfache Möglichkeit zum Implementieren von Dialogfeldern Druckserver und Drucker einrichten in Übereinstimmung mit den Windows-Standards.  
  
> [!NOTE]
>  Die `CPrintDialogEx` -Klasse kapselt die Dienste, die von der Windows 2000-druckeigenschaftenblatt bereitgestellt. Weitere Informationen finden Sie unter der [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) (Übersicht).  
  
 `CPrintDialog`die Funktionalität wird ersetzt durch die [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), die ein Standarddialogfeld stellen für beide Setup und Seite drucken konzipiert ist.  
  
 Sie können das Framework zur Behandlung viele Aspekte des Druckvorgangs für Ihre Anwendung verwenden. In diesem Fall zeigt das Framework automatisch das Windows-Standarddialogfeld zum Drucken. Sie können auch das Framework-Handle, das für Ihre Anwendung drucken haben jedoch außer Kraft setzen das Standarddialogfeld Drucken mit Ihren eigenen Dialogfeld Drucken. Weitere Informationen zur Verwendung von Framework Druckaufgaben behandeln, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie die Anwendung drucken, ohne Beteiligung des Frameworks behandeln möchten, können Sie die `CPrintDialog` -Klasse "wie besehen" mit dem Konstruktor angegeben oder Sie können eigene Dialogfeldklasse von ableiten `CPrintDialog` und einen Konstruktor, um Ihre Bedürfnisse zu schreiben. In beiden Fällen diese Dialogfelder verhält sich wie standardmäßige MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.  
  
 Verwenden einer `CPrintDialog` Objekt erstellen Sie zunächst das Objekt mit dem `CPrintDialog` Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pd](#m_pd) Struktur, um die Werte der Steuerelemente des Dialogfelds zu initialisieren. Die `m_pd` Struktur ist vom Typ [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843). Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie keine eigene Handles im angeben `m_pd` für die **hDevMode-Feld** und **hDevNames** Elemente müssen Sie die Windows-Funktion aufrufen **GlobalFree** für diese Handles, wenn Sie das Dialogfeld fertig sind. Bei Verwendung der Implementierung des Frameworks Einrichten von bereitgestellten `CWinApp::OnFilePrintSetup`, Sie müssen nicht mit diesen Handles frei. Die Handles werden vom verwaltet `CWinApp` und freigegeben werden `CWinApp`Destruktor. Es ist nur erforderlich, diese Handles freizugeben, wenn mit `CPrintDialog` eigenständigen.  
  
 Rufen Sie nach dem initialisieren die Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. `DoModal`Gibt zurück, ob der Benutzer OK ausgewählt ( **IDOK**) oder Abbrechen ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, verwenden Sie eine der `CPrintDialog`Member-Funktionen zum Abrufen von Informationen vom Benutzer eingeben.  
  
 Der `CPrintDialog::GetDefaults` Member-Funktion eignet sich für die aktuellen Druckerstandardeinstellungen abrufen, ohne dass ein Dialogfeld angezeigt. Diese Memberfunktion erfordert keinen Benutzereingriff.  
  
 Verwenden Sie die Fenster **CommDlgExtendedError** -Funktion zu bestimmen, ob Fehler während der Initialisierung des Dialogfelds und Weitere Informationen zu dem Fehler. Weitere Informationen zu dieser Funktion finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CPrintDialog`Abhängig von der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher enthalten ist.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CPrintDialog`, geben Sie eine benutzerdefinierte Vorlage und fügen Sie eine Zuordnung Nachricht, um die Benachrichtigung über die erweiterte Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übergeben werden. Es ist nicht erforderlich, die Hookfunktion anpassen.  
  
 Um unterschiedlich, abhängig davon, ob das Dialogfeld Drucken oder Print-Installation ist die gleiche Nachricht zu verarbeiten, müssen Sie eine Klasse für jedes Dialogfeld ableiten. Sie müssen auch überschreiben, die Windows **AttachOnSetup** -Funktion, die die Erstellung eines neuen Dialogfelds behandelt, wenn die Schaltfläche Drucken Setup in ein Druckdialogfeld ausgewählt ist.  
  
 Weitere Informationen zur Verwendung von `CPrintDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cprintdialog"></a>CPrintDialog::CPrintDialog  
 Erstellt eine Windows-Druckserver oder Drucker einrichten Dialogfeld-Objekt.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrintSetupOnly`  
 Gibt an, ob das Standarddialogfeld Windows drucken oder Drucken einrichten (Dialogfeld) angezeigt wird. Legen Sie diesen Parameter **TRUE** standard Windows Print Setup-Dialogfeld angezeigt. Legen Sie es auf **FALSE** der Windows-Drucken-Dialogfeld angezeigt. Wenn `bPrintSetupOnly` ist **FALSE**, ein Optionsfeld einrichten wird weiterhin in das Dialogfeld Drucken angezeigt.  
  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert anpassen. Zum Beispiel die **PD_ALLPAGES** -Kennzeichen setzt den Druckbereich standardmäßig auf allen Seiten des Dokuments. Finden Sie unter der [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld übergeordnete Fenster oder das Besitzer.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion erstellt nur das Objekt. Verwenden der `DoModal` Member-Funktion, um das Dialogfeld anzuzeigen.  
  
 Beachten Sie, dass beim Aufrufen des Konstruktors mit `bPrintSetupOnly` festgelegt **FALSE**, **PD_RETURNDC** Flag wird automatisch verwendet. Nach dem Aufruf von `DoModal`, `GetDefaults`, oder `GetPrinterDC`, ein Drucker-Gerätekontext zurückgegeben werden `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialog`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#174;](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Domänencontroller wird als der aktuelle Drucker DC und andere zuvor abgerufen haben, Drucker, den Domänencontroller vom Benutzer gelöscht werden müssen. Diese Funktion kann aufgerufen werden, und der resultierende DC verwendet, ohne jemals das Dialogfeld Drucken.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#106;](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>CPrintDialog::DoModal  
 Zeigt das Dialogfeld "Drucken" Windows common an und ermöglicht dem Benutzer, wählen Sie verschiedene Druckoptionen wie z. B. die Anzahl der Kopien, Bereich, und gibt an, ob die Kopien sortiert werden sollen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
 **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Optionen im Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pd` -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Nach dem Aufruf von `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
 Beachten Sie, dass beim Aufrufen des Konstruktors mit `bPrintSetupOnly` festgelegt **FALSE**, **PD_RETURNDC** Flag wird automatisch verwendet. Nach dem Aufruf von `DoModal`, `GetDefaults`, oder `GetPrinterDC`, ein Drucker-Gerätekontext zurückgegeben werden `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialog`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::CreatePrinterDC](#createprinterdc).  
  
##  <a name="getcopies"></a>CPrintDialog::GetCopies  
 Ruft die Anzahl der Kopien, die angefordert.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Kopien, die angefordert.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zum Abrufen der Anzahl der Kopien, die angefordert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdefaults"></a>CPrintDialog::GetDefaults  
 Ruft die Standardeinstellungen des des Standarddruckers ohne Anzeige eines Dialogfelds ab.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die abgerufenen Werte befinden sich der `m_pd` Struktur.  
  
 In einigen Fällen wird ein Aufruf dieser Funktion rufen die [Konstruktor](#cprintdialog) für `CPrintDialog` mit `bPrintSetupOnly` festgelegt **FALSE**. In diesen Fällen einen Drucker-Gerätekontext und **hDevNames** und **hDevMode-Feld** (zwei Handles befindet sich der `m_pd` -Datenmember) werden automatisch zugewiesen.  
  
 Wenn der Konstruktor für `CPrintDialog` aufgerufen wurde, wobei `bPrintSetupOnly` festgelegt **FALSE**, diese Funktion nicht nur zurück **hDevNames** und **hDevMode-Feld** (befindet sich im **m_pd.hDevNames** und **m_pd.hDevMode**) an den Aufrufer jedoch auch in einen Drucker-Gerätekontext zurück **m_pd.hDC**. Es liegt in der Verantwortung des Aufrufers, löschen den Drucker DC und rufen Sie die Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) Funktion auf die Handles Sie abschließend mit der `CPrintDialog` Objekt.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment ruft den Standarddrucker Gerätekontext und meldet dem Benutzer die Auflösung des Druckers in Punkten pro Zoll. (Dieses Attribut der Funktionen des Druckers wird häufig als DPI bezeichnet.)  
  
 [!code-cpp[NVC_MFCDocView&#107;](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>CPrintDialog::GetDeviceName  
 Ruft den Namen des ausgewählten Druckers.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers oder nach dem Aufruf von [GetDefaults](#getdefaults) um die aktuellen Standardeinstellungen für Gerät den Standarddrucker abzurufen. Ein Zeiger auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment zeigt den Namen des Benutzers standardmäßig Drucker und den Port an, den sie zusammen mit dem Namen Spooler verbunden ist, der Drucker verwendet. Der Code möglicherweise zeigt ein Meldungsfeld an, die besagt, "Standarddrucker ist HP LaserJet IIIP \\\server\share mit Winspool.", z. B..  
  
 [!code-cpp[NVC_MFCDocView&#108;](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>CPrintDialog::GetDevMode  
 Ruft die `DEVMODE` Struktur.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Entsperren Sie den Arbeitsspeicher, die von dieser Struktur mit dem Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen von Informationen über das Druckgerät.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdrivername"></a>CPrintDialog::GetDriverName  
 Ruft den Namen des aktuell ausgewählten Druckertreiber.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker. Ein Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getfrompage"></a>CPrintDialog::GetFromPage  
 Ruft die erste Seite des Druckbereichs ab.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die ersten Seitenzahl im Bereich der zu druckenden Seiten.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` ab Seitenzahl im Bereich der zu druckenden Seiten abgerufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="getportname"></a>CPrintDialog::GetPortName  
 Ruft den Namen des aktuell ausgewählten Ports.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Ports.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des derzeit ausgewählten Ports.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getprinterdc"></a>CPrintDialog::GetPrinterDC  
 Ruft ein Handle für den Gerätekontext ab.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den Druckergerätekontext, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `bPrintSetupOnly` Parameter von der `CPrintDialog` Konstruktor wurde **FALSE** (d. h., dass das Dialogfeld Drucken angezeigt wird), dann `GetPrinterDC` gibt ein Handle für den Gerätekontext. Müssen Sie die Fenster aufrufen [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) Funktion, um den Gerätekontext zu löschen, wenn Sie fertig sind verwendet wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#109;](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>CPrintDialog::GetToPage  
 Ruft die letzte Seite des Druckbereichs ab.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die letzte Seitenzahl im Bereich der zu druckenden Seiten.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` die letzte Seitenzahl im Bereich der zu druckenden Seiten abgerufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="m_pd"></a>CPrintDialog::m_pd  
 Eine Struktur, deren Mitglieder die Merkmale des Dialog-Objekts gespeichert.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPrintDialog` -Objekt können Sie `m_pd` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Member-Funktion. Weitere Informationen zu den `m_pd` -Struktur, finden Sie unter [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie ändern die `m_pd` Datenmember direkt Standardverhalten überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#111;](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>CPrintDialog::PrintAll  
 Bestimmt, ob alle Seiten des Dokuments gedruckt.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn alle Seiten im Dokument werden gedruckt werden. andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob alle Seiten im Dokument zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printcollate"></a>CPrintDialog::PrintCollate  
 Bestimmt, ob sortierte Kopien angefordert werden.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer im Dialogfeld das Kontrollkästchen sortieren auswählt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren soll.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#110;](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>CPrintDialog::PrintRange  
 Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nur ein Bereich von Seiten im Dokument gedruckt werden sollen; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob nur einen Bereich von Seiten im Dokument zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printselection"></a>CPrintDialog::PrintSelection  
 Bestimmt, ob nur die ausgewählten Elemente zu drucken.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nur die ausgewählten Elemente werden gedruckt werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob nur die ausgewählten Elemente zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)

