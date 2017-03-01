---
title: CPrintDialogEx Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
dev_langs:
- C++
helpviewer_keywords:
- Print Setup dialog box
- CPrintDialogEx class
- Print dialog box
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 22
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
ms.openlocfilehash: 8dc8f01eef42b54af18ed07520d547768c931748
ms.lasthandoff: 02/24/2017

---
# <a name="cprintdialogex-class"></a>CPrintDialogEx-Klasse
Kapselt die Dienste, die vom Windows 2000-Druckeigenschaftenblatt bereitgestellt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Erstellt ein `CPrintDialogEx`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Erstellt einen Gerätekontext ohne das Dialogfeld Drucken.|  
|[CPrintDialogEx::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CPrintDialogEx::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Ruft die Standardeinstellungen des ohne Anzeige eines Dialogfelds ab.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Ruft den Namen des ausgewählten Druckers.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Ruft den Namen der vom System definierte Druckertreiber ab.|  
|[CPrintDialogEx::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Ports.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Gerätekontext ab.|  
|[CPrintDialogEx::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Bestimmt, ob die aktuelle Seite des Dokuments gedruckt.|  
|[CPrintDialogEx::PrintRange](#printrange)|Bestimmt, ob nur für einen angegebenen Bereich von Seiten zu drucken.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Bestimmt, ob nur die ausgewählten Elemente zu drucken.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Eine Struktur, die zur Anpassung einer `CPrintDialogEx` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können das Framework zur Behandlung viele Aspekte des Druckvorgangs für Ihre Anwendung verwenden. Weitere Informationen zur Verwendung von Framework Druckaufgaben behandeln, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie die Anwendung drucken, ohne Beteiligung des Frameworks behandeln möchten, können Sie die `CPrintDialogEx` -Klasse "wie besehen" mit dem Konstruktor angegeben oder Sie können eigene Dialogfeldklasse von ableiten `CPrintDialogEx` und einen Konstruktor, um Ihre Bedürfnisse zu schreiben. In beiden Fällen diese Dialogfelder verhält sich wie standardmäßige MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.  
  
 Verwenden einer `CPrintDialogEx` Objekt erstellen Sie zunächst das Objekt mit dem `CPrintDialogEx` Konstruktor. Nachdem das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pdex](#m_pdex) Struktur, um die Werte der Steuerelemente des Dialogfelds zu initialisieren. Die `m_pdex` Struktur ist vom Typ [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie keine eigene Handles im angeben `m_pdex` für die **hDevMode-Feld** und **hDevNames** Elemente müssen Sie die Windows-Funktion aufrufen **GlobalFree** für diese Handles, wenn Sie das Dialogfeld fertig sind.  
  
 Rufen Sie nach dem initialisieren die Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, Druckoptionen auszuwählen. Wenn `DoModal` zurückgibt, können Sie bestimmen, ob der Benutzer auf die Schaltfläche OK, anwenden oder "Abbrechen" ausgewählt.  
  
 Wenn der Benutzer auf OK geklickt hat, können Sie `CPrintDialogEx`Member-Funktionen zum Abrufen von Informationen vom Benutzer eingeben.  
  
 Der `CPrintDialogEx::GetDefaults` Member-Funktion eignet sich für die aktuellen Druckerstandardeinstellungen abrufen, ohne dass ein Dialogfeld angezeigt. Diese Methode erfordert keinen Benutzereingriff.  
  
 Verwenden Sie die Fenster **CommDlgExtendedError** -Funktion zu bestimmen, ob Fehler während der Initialisierung des Dialogfelds und Weitere Informationen zu dem Fehler. Weitere Informationen zu dieser Funktion finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Weitere Informationen zur Verwendung von `CPrintDialogEx`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="a-namecprintdialogexa--cprintdialogexcprintdialogex"></a><a name="cprintdialogex"></a>CPrintDialogEx::CPrintDialogEx  
 Erstellt eine Windows 2000-druckeigenschaftenblatt.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, um die Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert anpassen. Zum Beispiel die **PD_ALLPAGES** -Kennzeichen setzt den Druckbereich standardmäßig auf allen Seiten des Dokuments. Finden Sie unter der [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld übergeordnete Fenster oder das Besitzer.  
  
### <a name="remarks"></a>Hinweise  
 Diese Member-Funktion erstellt nur das Objekt. Verwenden der `DoModal` Member-Funktion, um das Dialogfeld anzuzeigen.  
  
##  <a name="a-namecreateprinterdca--cprintdialogexcreateprinterdc"></a><a name="createprinterdc"></a>CPrintDialogEx::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Domänencontroller befindet sich auch in der **hDC** Mitglied [M_pdex](#m_pdex).  
  
 Dieser Domänencontroller wird als der aktuelle Drucker DC und andere zuvor abgerufene Drucker DCs müssen gelöscht werden. Diese Funktion kann aufgerufen werden, und der resultierende DC verwendet, ohne jemals das Dialogfeld Drucken.  
  
##  <a name="a-namedomodala--cprintdialogexdomodal"></a><a name="domodal"></a>CPrintDialogEx::DoModal  
 Mit dieser Funktion können Sie das Eigenschaftenfenster von Windows 2000 für allgemeine Drucken anzuzeigen und dem Benutzer ermöglichen, wählen Sie verschiedene Druckoptionen wie z. B. die Anzahl der Kopien, Bereich, und gibt an, ob die Kopien sortiert werden sollen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die INT_PTR Rückgabewerts ist tatsächlich ein HRESULT. Finden Sie im Abschnitt Return Values [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Optionen im Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pdex` -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Nach dem Aufruf von `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
 Wenn die **PD_RETURNDC** Flag wird verwendet, beim Aufrufen von `DoModal`, ein Drucker-Gerätekontext zurückgegeben werden die **hDC** Mitglied [M_pdex](#m_pdex). Dieser Domänencontroller muss mit einem Aufruf von freigegeben werden [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialogEx`.  
  
##  <a name="a-namegetcopiesa--cprintdialogexgetcopies"></a><a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zum Abrufen der Anzahl der Kopien, die angefordert.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Kopien, die angefordert.  
  
##  <a name="a-namegetdefaultsa--cprintdialogexgetdefaults"></a><a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Rufen Sie diese Funktion, um die Standardeinstellungen des des Standarddruckers abzurufen, ohne dass ein Dialogfeld angezeigt.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn erfolgreich, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
 `GetDefaults`das Eigenschaftenblatt Drucken wird nicht angezeigt werden. Stattdessen wird die **hDevNames** und **hDevMode-Feld** Mitglieder [M_pdex](#m_pdex) , Handles für die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen, die für den System-Standarddrucker initialisiert werden. Beide **hDevNames** und **hDevMode-Feld** muss NULL sein, oder `GetDefaults` fehlschlägt.  
  
 Wenn die **PD_RETURNDC** Flag festgelegt ist, diese Funktion nicht nur zurück **hDevNames** und **hDevMode-Feld** (befindet sich im **m_pdex.hDevNames** und **m_pdex.hDevMode**) an den Aufrufer zurück und auch einen Drucker-DC in **m_pdex.hDC**. Es liegt in der Verantwortung des Aufrufers, löschen den Drucker DC und rufen Sie die Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) Funktion auf die Handles Sie abschließend mit der `CPrintDialogEx` Objekt.  
  
##  <a name="a-namegetdevicenamea--cprintdialogexgetdevicename"></a><a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers oder nach dem Aufruf von [GetDefaults](#getdefaults) zum Abrufen des Namens des Standarddruckers.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeiger auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetdevmodea--cprintdialogexgetdevmode"></a><a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen von Informationen über das Druckgerät.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Entsperren Sie den Arbeitsspeicher, die von dieser Struktur mit dem Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die in beschrieben wird die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdrivernamea--cprintdialogexgetdrivername"></a><a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Ein Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetportnamea--cprintdialogexgetportname"></a><a name="getportname"></a>CPrintDialogEx::GetPortName  
 Mit dieser Funktion wird nach dem Aufruf von [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des derzeit ausgewählten Ports.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Ports.  
  
##  <a name="a-namegetprinterdca--cprintdialogexgetprinterdc"></a><a name="getprinterdc"></a>CPrintDialogEx::GetPrinterDC  
 Gibt ein Handle für den Drucker-Gerätekontext zurück.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie die Fenster aufrufen [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) Funktion, um den Gerätekontext zu löschen, wenn Sie fertig sind verwendet wird.  
  
##  <a name="a-namempdexa--cprintdialogexmpdex"></a><a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Eine PRINTDLGEX-Struktur, deren Mitglieder die Merkmale des Dialog-Objekts gespeichert.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPrintDialogEx` -Objekt können Sie `m_pdex` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Member-Funktion. Weitere Informationen zu den `m_pdex` -Struktur, finden Sie unter [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Wenn Sie ändern die `m_pdex` Datenmember direkt Standardverhalten überschreiben.  
  
##  <a name="a-nameprintalla--cprintdialogexprintall"></a><a name="printall"></a>CPrintDialogEx::PrintAll  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob alle Seiten im Dokument zu drucken.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn alle Seiten im Dokument gedruckt, andernfalls **FALSE**.  
  
##  <a name="a-nameprintcollatea--cprintdialogexprintcollate"></a><a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren soll.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** klickt der Benutzer dieses Kontrollkästchen im Dialogfeld; andernfalls **FALSE**.  
  
##  <a name="a-nameprintcurrentpagea--cprintdialogexprintcurrentpage"></a><a name="printcurrentpage"></a>CPrintDialogEx::PrintCurrentPage  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob die aktuelle Seite im Dokument zu drucken.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** Wenn **aktuelle Seite drucken** im Dialogfeld ausgewählt ist andernfalls **FALSE**.  
  
##  <a name="a-nameprintrangea--cprintdialogexprintrange"></a><a name="printrange"></a>CPrintDialogEx::PrintRange  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob nur einen Bereich von Seiten im Dokument zu drucken.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** sind nur ein Bereich von Seiten im Dokument gedruckt, andernfalls **FALSE**.  
  
### <a name="remarks"></a>Hinweise  
 Der angegebenen Seitenbereiche können bestimmt werden, von [M_pdex](#m_pdex) (finden Sie unter **nPageRanges**, **nMaxPageRanges**, und **LpPageRanges** in der [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) -Struktur der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]).  
  
##  <a name="a-nameprintselectiona--cprintdialogexprintselection"></a><a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Mit dieser Funktion wird nach dem Aufruf von `DoModal` zu bestimmen, ob nur die ausgewählten Elemente zu drucken.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **True,** sind nur die ausgewählten Elemente gedruckte andernfalls **FALSE**.  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)

