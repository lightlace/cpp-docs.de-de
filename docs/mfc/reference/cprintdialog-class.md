---
title: CPrintDialog Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CPrintDialog [MFC], CPrintDialog
- CPrintDialog [MFC], CreatePrinterDC
- CPrintDialog [MFC], DoModal
- CPrintDialog [MFC], GetCopies
- CPrintDialog [MFC], GetDefaults
- CPrintDialog [MFC], GetDeviceName
- CPrintDialog [MFC], GetDevMode
- CPrintDialog [MFC], GetDriverName
- CPrintDialog [MFC], GetFromPage
- CPrintDialog [MFC], GetPortName
- CPrintDialog [MFC], GetPrinterDC
- CPrintDialog [MFC], GetToPage
- CPrintDialog [MFC], PrintAll
- CPrintDialog [MFC], PrintCollate
- CPrintDialog [MFC], PrintRange
- CPrintDialog [MFC], PrintSelection
- CPrintDialog [MFC], m_pd
ms.assetid: 5bdb2424-adf8-433d-a97c-df11a83bc4e4
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 653cdc4580862288d98600603c1b45526ea38675
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cprintdialog-class"></a>CPrintDialog-Klasse
Kapselt die Dienste, die vom allgemeinen Windows-Dialogfeld für das Drucken bereitgestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPrintDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::CPrintDialog](#cprintdialog)|Erstellt ein `CPrintDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::CreatePrinterDC](#createprinterdc)|Erstellt einen druckergerätkontext ohne Anzeige des Dialogfelds drucken.|  
|[CPrintDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CPrintDialog::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|  
|[CPrintDialog::GetDefaults](#getdefaults)|Ruft Gerät Standardwerte ohne Anzeigen eines Dialogfelds ab.|  
|[CPrintDialog::GetDeviceName](#getdevicename)|Ruft den Namen des aktuell ausgewählten Druckergeräts ab.|  
|[CPrintDialog::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|  
|[CPrintDialog::GetDriverName](#getdrivername)|Ruft den Namen des aktuell ausgewählten Druckertreibers ab.|  
|[CPrintDialog::GetFromPage](#getfrompage)|Ruft die Anfangsseite des drucken Bereichs ab.|  
|[CPrintDialog::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Drucker Ports.|  
|[CPrintDialog::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker-Gerätekontext ab.|  
|[CPrintDialog::GetToPage](#gettopage)|Ruft die Endseite des drucken Bereichs ab.|  
|[CPrintDialog::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt.|  
|[CPrintDialog::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialog::PrintRange](#printrange)|Bestimmt, ob nur einen bestimmten Bereich von Seiten drucken.|  
|[CPrintDialog::PrintSelection](#printselection)|Bestimmt, ob nur die momentan ausgewählten Elemente zu drucken.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialog::m_pd](#m_pd)|Eine Struktur, die zum Anpassen einer `CPrintDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Allgemeine drucken Dialogfelder bieten eine einfache Möglichkeit zum Implementieren von Druck- und Einrichten von Dialogfeldern in Übereinstimmung mit den Windows-Standards.  
  
> [!NOTE]
>  Die `CPrintDialogEx` -Klasse kapselt die Dienste, die von der Windows 2000-druckeigenschaftenblatt bereitgestellt. Weitere Informationen finden Sie unter der [CPrintDialogEx](../../mfc/reference/cprintdialogex-class.md) (Übersicht).  
  
 `CPrintDialog`die Funktionalität wird ersetzt durch die [CPageSetupDialog](../../mfc/reference/cpagesetupdialog-class.md), dem dient ein häufig verwendetes Dialogfeld stellen für beide Setup und Seite drucken.  
  
 Sie können das Framework behandeln viele Aspekte des Druckvorgangs für Ihre Anwendung abhängig. In diesem Fall zeigt das Framework automatisch die Windows-Standarddialogfeld für das Drucken. Sie können auch das Framework-Handle, das für Ihre Anwendung drucken haben jedoch außer Kraft setzen das Standarddialogfeld Drucken mit Ihren eigenen klicken Sie im Dialogfeld "Drucken". Weitere Informationen zum Verwenden von Framework Druckaufgaben behandelt, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie Ihrer Anwendung zur Handhabung von ohne Beteiligung von das Framework drucken möchten, können Sie mithilfe der `CPrintDialog` -Klasse "wie besehen" mit dem Konstruktor bereitgestellt oder Sie können eine eigene Dialogfeldklasse von ableiten `CPrintDialog` und einen Konstruktor für Ihre speziellen Anforderungen zu schreiben. In beiden Fällen wird diese Dialogfelder verhält sich wie standard-MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.  
  
 Verwenden einer `CPrintDialog` Objekt, erstellen Sie zunächst das Objekt mit dem `CPrintDialog` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pd](#m_pd) Struktur der Werte von Steuerelementen für das Dialogfeld zu initialisieren. Die `m_pd` Struktur ist vom Typ [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.  
  
 Wenn Sie keine eigene Handles im angeben `m_pd` für die **hDevMode-Feld** und **hDevNames** Mitglieder, achten Sie darauf, dass Sie die Windows-Funktion aufrufen **GlobalFree** für diese Handles Wenn Sie das Dialogfeld fertig sind. Bei Verwendung der Implementierung des Frameworks Drucker Einrichten von bereitgestellten `CWinApp::OnFilePrintSetup`, Sie müssen nicht mit diesen Handles freizugeben. Die Handles werden vom verwaltet `CWinApp` und freigegeben werden `CWinApp`den Destruktor. Es ist nur erforderlich, diese Handles freizugeben, wenn mit `CPrintDialog` eigenständigen.  
  
 Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und die Benutzer Druckoptionen auszuwählen. `DoModal`Gibt zurück, ob der Benutzer die OK ausgewählt ( **IDOK**) oder "Abbrechen" ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, können Sie eine der `CPrintDialog`des Memberfunktionen zum Abrufen von Informationen vom Benutzer eingegeben.  
  
 Die `CPrintDialog::GetDefaults` Memberfunktion eignet sich für den aktuellen Druckerstandardeinstellungen abrufen, ohne ein Dialogfeld angezeigt. Diese Memberfunktion ist keine Benutzerinteraktion erforderlich.  
  
 Sie können die Windows **CommDlgExtendedError** -Funktion zu bestimmen, ob der Fehler während der Initialisierung des Dialogfelds und erfahren Sie mehr über den Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.  
  
 `CPrintDialog`basiert auf der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher ausgeliefert wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CPrintDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollte auf der Basisklasse übergeben werden. Anpassen von die Hookfunktion ist nicht erforderlich.  
  
 Um die gleiche Nachricht unterschiedlich, abhängig davon, ob das Dialogfeld Drucken oder Drucker einrichten ist zu verarbeiten, müssen Sie eine Klasse für jede im Dialogfeld ableiten. Sie müssen auch überschreiben, die Windows **AttachOnSetup** -Funktion, die die Erstellung eines neuen Dialogfelds behandelt, wenn der Drucker einrichten-Schaltfläche in einem Druckdialogfeld aktiviert ist.  
  
 Weitere Informationen zur Verwendung von `CPrintDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cprintdialog"></a>CPrintDialog::CPrintDialog  
 Erstellt eine Windows-Druckserver oder Drucker einrichten Dialogfeldobjekt.  
  
```  
CPrintDialog(
    BOOL bPrintSetupOnly,  
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS | PD_HIDEPRINTTOFILE | PD_NOSELECTION,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `bPrintSetupOnly`  
 Gibt an, ob die Windows-Druckserver-Standarddialogfeld oder Drucken einrichten (Dialogfeld) angezeigt wird. Legen Sie diesen Parameter auf **"true"** die Print-Installation von Windows-Standarddialogfeld angezeigt. Legen Sie es auf **"false"** zum Anzeigen des Dialogfelds Windows drucken. Wenn `bPrintSetupOnly` ist **"false"**, einen Drucker einrichten Optionsfeld wird weiterhin in das Dialogfeld Drucken angezeigt.  
  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, zum Anpassen der Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert. Z. B. die **PD_ALLPAGES** Flag legt den Standardbereich drucken für alle Seiten des Dokuments. Finden Sie unter der [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) Struktur in das Windows SDK für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld über- oder Besitzer Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion erstellt nur das Objekt. Verwenden der `DoModal` Member-Funktion, um das Dialogfeld anzuzeigen.  
  
 Beachten Sie, dass beim Aufrufen des Konstruktors mit `bPrintSetupOnly` festgelegt **"false"**, **PD_RETURNDC** Flag wird automatisch verwendet. Nach dem Aufruf `DoModal`, `GetDefaults`, oder `GetPrinterDC`, ein druckerdomänencontroller im zurückgegeben `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialog`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#174](../../mfc/codesnippet/cpp/cprintdialog-class_1.cpp)]  
  
##  <a name="createprinterdc"></a>CPrintDialog::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Diesen DC wird davon ausgegangen, dass der aktuelle Drucker-Gerätekontext, und alle anderen bereits abgerufen, Drucker, DCs müssen vom Benutzer gelöscht werden. Diese Funktion kann aufgerufen werden, und der resultierende DC verwendet, ohne jemals Anzeige des Dialogfelds drucken.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#106](../../mfc/codesnippet/cpp/cprintdialog-class_2.cpp)]  
  
##  <a name="domodal"></a>CPrintDialog::DoModal  
 Zeigt das Dialogfeld "Drucken" Allgemeine Windows an und ermöglicht es dem Benutzer auf verschiedenen Druckoptionen, z. B. die Anzahl der Kopien, Bereich, und gibt an, ob Kopien sortiert werden sollen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um festzustellen, ob ein Fehler aufgetreten.  
  
 **IDOK** und **IDCANCEL** sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder "Abbrechen" ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Optionen für Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pd` -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
 Beachten Sie, dass beim Aufrufen des Konstruktors mit `bPrintSetupOnly` festgelegt **"false"**, **PD_RETURNDC** Flag wird automatisch verwendet. Nach dem Aufruf `DoModal`, `GetDefaults`, oder `GetPrinterDC`, ein druckerdomänencontroller im zurückgegeben `m_pd.hDC`. Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialog`.  
  
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
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen der Anzahl von Kopien angefordert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdefaults"></a>CPrintDialog::GetDefaults  
 Ruft die Standardeinstellungen für Gerät als Standarddrucker ohne Anzeigen eines Dialogfelds ab.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Funktion erfolgreich ausgeführt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die abgerufenen Werte befinden sich der `m_pd` Struktur.  
  
 In einigen Fällen ein Aufruf dieser Funktion rufen die [Konstruktor](#cprintdialog) für `CPrintDialog` mit `bPrintSetupOnly` festgelegt **"false"**. In diesen Fällen einen druckerdomänencontroller und **hDevNames** und **hDevMode-Feld** (zwei Handles befindet sich in der `m_pd` -Datenmember) werden automatisch zugewiesen.  
  
 Wenn der Konstruktor für `CPrintDialog` aufgerufen wurde, wobei `bPrintSetupOnly` festgelegt **"false"**, diese Funktion wird nicht nur zurück **hDevNames** und **hDevMode-Feld** (befindet sich unter **m_pd.hDevNames** und **m_pd.hDevMode**) an den Aufrufer jedoch auch einen Drucker-Gerätekontext in zurück **m_pd.hDC**. Es liegt in der Verantwortung des Aufrufers, löschen die Drucker-Gerätekontext und rufen Sie die Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) Funktion auf die Handles Sie abschließend mit der `CPrintDialog` Objekt.  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment ruft den Standarddrucker Gerätekontext und meldet dem Benutzer die Auflösung des Druckers in Punkte pro Zoll. (Dieses Attribut für die Leistungsmerkmale des Druckers wird häufig als DPI bezeichnet.)  
  
 [!code-cpp[NVC_MFCDocView#107](../../mfc/codesnippet/cpp/cprintdialog-class_3.cpp)]  
  
##  <a name="getdevicename"></a>CPrintDialog::GetDeviceName  
 Ruft den Namen des aktuell ausgewählten Druckergeräts ab.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers oder nach dem Aufruf [GetDefaults](#getdefaults) die Standardeinstellungen für aktuelle Gerät als Standarddrucker abgerufen. Verwenden Sie einen Zeiger auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Beispiel  
 Dieses Codefragment zeigt des Benutzers Drucker Standardname und der Port, den sie zusammen mit dem Namen der Spooler verbunden ist, der Drucker verwendet. Der Code möglicherweise zeigt ein Meldungsfeld mit der Aufforderung "befindet sich HP LaserJet IIIP auf der Standarddrucker \\\server\share mit Winspool.", z. B.  
  
 [!code-cpp[NVC_MFCDocView#108](../../mfc/codesnippet/cpp/cprintdialog-class_4.cpp)]  
  
##  <a name="getdevmode"></a>CPrintDialog::GetDevMode  
 Ruft die `DEVMODE` Struktur.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Sie müssen den Arbeitsspeicher, bis diese Struktur mit dem Windows Entsperren [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die im Windows SDK beschrieben wird.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen von Informationen über das Druckgerät.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::PrintCollate](#printcollate).  
  
##  <a name="getdrivername"></a>CPrintDialog::GetDriverName  
 Ruft den Namen des aktuell ausgewählten Druckertreibers ab.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker. Verwenden Sie einen Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getfrompage"></a>CPrintDialog::GetFromPage  
 Ruft die Anfangsseite des drucken Bereichs ab.  
  
```  
int GetFromPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Seite Anfangszahl im Bereich der Seiten, die gedruckt werden.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` ab Seitenanzahl im Bereich von zu druckenden Seiten abgerufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="getportname"></a>CPrintDialog::GetPortName  
 Ruft den Namen des aktuell ausgewählten Drucker Ports.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker Ports.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) , den Namen des aktuell ausgewählten Drucker Ports abzurufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::GetDeviceName](#getdevicename).  
  
##  <a name="getprinterdc"></a>CPrintDialog::GetPrinterDC  
 Ruft ein Handle für den Drucker-Gerätekontext ab.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den Drucker-Gerätekontext bei Erfolg; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `bPrintSetupOnly` Parameter von der `CPrintDialog` Konstruktor wurde **"false"** (d. h., dass das Drucken-Dialogfeld angezeigt wird), klicken Sie dann `GetPrinterDC` gibt ein Handle für den Drucker-Gerätekontext zurück. Rufen Sie die Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) Funktion, um den Gerätekontext löschen, wenn Sie fertig sind verwenden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#109](../../mfc/codesnippet/cpp/cprintdialog-class_5.cpp)]  
  
##  <a name="gettopage"></a>CPrintDialog::GetToPage  
 Ruft die Endseite des drucken Bereichs ab.  
  
```  
int GetToPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die letzte Seitenzahl im Bereich der zu druckenden Seiten.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` die letzte Seitenzahl im Bereich von zu druckenden Seiten abgerufen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="m_pd"></a>CPrintDialog::m_pd  
 Eine Struktur, deren Mitglieder die Merkmale der dem Dialogfeldobjekt speichern.  
  
```  
PRINTDLG& m_pd;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPrintDialog` -Objekt können Sie `m_pd` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Memberfunktion. Weitere Informationen zu den `m_pd` -Struktur, finden Sie unter [PRINTDLG](http://msdn.microsoft.com/library/windows/desktop/ms646843) im Windows SDK.  
  
 Wenn Sie ändern die `m_pd` Datenmember direkt, Sie Standardverhalten überschreiben.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#111](../../mfc/codesnippet/cpp/cprintdialog-class_6.cpp)]  
  
##  <a name="printall"></a>CPrintDialog::PrintAll  
 Bestimmt, ob alle Seiten des Dokuments gedruckt.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn alle Seiten im Dokument gedruckt werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob alle Seiten im Dokument zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printcollate"></a>CPrintDialog::PrintCollate  
 Bestimmt, ob sortierte Kopien angefordert werden.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer im Dialogfeld das Kontrollkästchen Collate auswählt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren sollten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#110](../../mfc/codesnippet/cpp/cprintdialog-class_7.cpp)]  
  
##  <a name="printrange"></a>CPrintDialog::PrintRange  
 Bestimmt, ob nur einen bestimmten Bereich von Seiten drucken.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nur ein Bereich von Seiten im Dokument gedruckt werden; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob nur einen Bereich von Seiten im Dokument zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
##  <a name="printselection"></a>CPrintDialog::PrintSelection  
 Bestimmt, ob nur die momentan ausgewählten Elemente zu drucken.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn nur die ausgewählten Elemente werden zu druckende; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob nur die momentan ausgewählten Elemente zu drucken.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CPrintDialog::m_pd](#m_pd).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel DIBLOOK](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
