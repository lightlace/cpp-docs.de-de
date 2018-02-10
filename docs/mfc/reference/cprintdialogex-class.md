---
title: CPrintDialogEx Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrintDialogEx
- AFXDLGS/CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CPrintDialogEx
- AFXDLGS/CPrintDialogEx::CreatePrinterDC
- AFXDLGS/CPrintDialogEx::DoModal
- AFXDLGS/CPrintDialogEx::GetCopies
- AFXDLGS/CPrintDialogEx::GetDefaults
- AFXDLGS/CPrintDialogEx::GetDeviceName
- AFXDLGS/CPrintDialogEx::GetDevMode
- AFXDLGS/CPrintDialogEx::GetDriverName
- AFXDLGS/CPrintDialogEx::GetPortName
- AFXDLGS/CPrintDialogEx::GetPrinterDC
- AFXDLGS/CPrintDialogEx::PrintAll
- AFXDLGS/CPrintDialogEx::PrintCollate
- AFXDLGS/CPrintDialogEx::PrintCurrentPage
- AFXDLGS/CPrintDialogEx::PrintRange
- AFXDLGS/CPrintDialogEx::PrintSelection
- AFXDLGS/CPrintDialogEx::m_pdex
dev_langs:
- C++
helpviewer_keywords:
- CPrintDialogEx [MFC], CPrintDialogEx
- CPrintDialogEx [MFC], CreatePrinterDC
- CPrintDialogEx [MFC], DoModal
- CPrintDialogEx [MFC], GetCopies
- CPrintDialogEx [MFC], GetDefaults
- CPrintDialogEx [MFC], GetDeviceName
- CPrintDialogEx [MFC], GetDevMode
- CPrintDialogEx [MFC], GetDriverName
- CPrintDialogEx [MFC], GetPortName
- CPrintDialogEx [MFC], GetPrinterDC
- CPrintDialogEx [MFC], PrintAll
- CPrintDialogEx [MFC], PrintCollate
- CPrintDialogEx [MFC], PrintCurrentPage
- CPrintDialogEx [MFC], PrintRange
- CPrintDialogEx [MFC], PrintSelection
- CPrintDialogEx [MFC], m_pdex
ms.assetid: 1d506703-ee1c-44cc-b4ce-4e778fec26b8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3aefa1a0e879cbacbf3a971bff2887f72d13f303
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="cprintdialogex-class"></a>CPrintDialogEx-Klasse
Kapselt die Dienste, die von der Windows-druckeigenschaftenblatt bereitgestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CPrintDialogEx : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::CPrintDialogEx](#cprintdialogex)|Erstellt ein `CPrintDialogEx`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::CreatePrinterDC](#createprinterdc)|Erstellt einen druckergerätkontext ohne Anzeige des Dialogfelds drucken.|  
|[CPrintDialogEx::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CPrintDialogEx::GetCopies](#getcopies)|Ruft die Anzahl der Kopien, die angefordert.|  
|[CPrintDialogEx::GetDefaults](#getdefaults)|Ruft Gerät Standardwerte ohne Anzeigen eines Dialogfelds ab.|  
|[CPrintDialogEx::GetDeviceName](#getdevicename)|Ruft den Namen des aktuell ausgewählten Druckergeräts ab.|  
|[CPrintDialogEx::GetDevMode](#getdevmode)|Ruft die `DEVMODE` Struktur.|  
|[CPrintDialogEx::GetDriverName](#getdrivername)|Ruft den Namen des Gerätetreibers systemdefinierte Drucker ab.|  
|[CPrintDialogEx::GetPortName](#getportname)|Ruft den Namen des aktuell ausgewählten Drucker Ports.|  
|[CPrintDialogEx::GetPrinterDC](#getprinterdc)|Ruft ein Handle für den Drucker-Gerätekontext ab.|  
|[CPrintDialogEx::PrintAll](#printall)|Bestimmt, ob alle Seiten des Dokuments gedruckt.|  
|[CPrintDialogEx::PrintCollate](#printcollate)|Bestimmt, ob sortierte Kopien angefordert werden.|  
|[CPrintDialogEx::PrintCurrentPage](#printcurrentpage)|Bestimmt, ob die aktuelle Seite des Dokuments gedruckt.|  
|[CPrintDialogEx::PrintRange](#printrange)|Bestimmt, ob nur einen bestimmten Bereich von Seiten drucken.|  
|[CPrintDialogEx::PrintSelection](#printselection)|Bestimmt, ob nur die momentan ausgewählten Elemente zu drucken.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CPrintDialogEx::m_pdex](#m_pdex)|Eine Struktur, die zum Anpassen einer `CPrintDialogEx` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Sie können das Framework behandeln viele Aspekte des Druckvorgangs für Ihre Anwendung abhängig. Weitere Informationen zum Verwenden von Framework Druckaufgaben behandelt, finden Sie im Artikel [Drucken](../../mfc/printing.md).  
  
 Wenn Sie Ihrer Anwendung zur Handhabung von ohne Beteiligung von das Framework drucken möchten, können Sie mithilfe der `CPrintDialogEx` -Klasse "wie besehen" mit dem Konstruktor bereitgestellt oder Sie können eine eigene Dialogfeldklasse von ableiten `CPrintDialogEx` und einen Konstruktor für Ihre speziellen Anforderungen zu schreiben. In beiden Fällen wird diese Dialogfelder verhält sich wie standard-MFC-Dialogfelder, da sie von der Klasse abgeleitet sind `CCommonDialog`.  
  
 Verwenden einer `CPrintDialogEx` Objekt, erstellen Sie zunächst das Objekt mit dem `CPrintDialogEx` Konstruktor. Nachdem Sie das Dialogfeld erstellt wurde, können Sie festlegen oder ändern Sie alle Werte in der [M_pdex](#m_pdex) Struktur der Werte von Steuerelementen für das Dialogfeld zu initialisieren. Die `m_pdex` Struktur ist vom Typ [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.  
  
 Wenn Sie keine eigene Handles im angeben `m_pdex` für die **hDevMode-Feld** und **hDevNames** Mitglieder, achten Sie darauf, dass Sie die Windows-Funktion aufrufen **GlobalFree** für diese Handles Wenn Sie das Dialogfeld fertig sind.  
  
 Rufen Sie nach dem Initialisieren der Dialogfeld-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und die Benutzer Druckoptionen auszuwählen. Wenn `DoModal` zurückgegeben wird, können Sie bestimmen, ob der Benutzer die Schaltfläche OK, anwenden oder "Abbrechen" ausgewählt.  
  
 Wenn der Benutzer auf OK geklickt hat, können Sie `CPrintDialogEx`des Memberfunktionen zum Abrufen von Informationen vom Benutzer eingegeben.  
  
 Die `CPrintDialogEx::GetDefaults` Memberfunktion eignet sich für den aktuellen Druckerstandardeinstellungen abrufen, ohne ein Dialogfeld angezeigt. Diese Methode erfordert kein Eingreifen des Benutzers.  
  
 Sie können die Windows **CommDlgExtendedError** -Funktion zu bestimmen, ob der Fehler während der Initialisierung des Dialogfelds und erfahren Sie mehr über den Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.  
  
 Weitere Informationen zur Verwendung von `CPrintDialogEx`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `IObjectWithSite`  
  
 `IPrintDialogCallback`  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPrintDialogEx`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cprintdialogex"></a>  CPrintDialogEx::CPrintDialogEx  
 Erstellt eine Windows-druckeigenschaftenblatt an.  
  
```  
CPrintDialogEx(
    DWORD dwFlags = PD_ALLPAGES | PD_USEDEVMODECOPIES | PD_NOPAGENUMS       | PD_HIDEPRINTTOFILE | PD_NOSELECTION | PD_NOCURRENTPAGE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `dwFlags`  
 Ein oder mehrere Flags, die Sie verwenden können, zum Anpassen der Einstellungen im Dialogfeld mit dem bitweisen OR-Operator kombiniert. Z. B. die **PD_ALLPAGES** Flag legt den Standardbereich drucken für alle Seiten des Dokuments. Finden Sie unter der [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Struktur in das Windows SDK für Weitere Informationen zu diesen Flags.  
  
 `pParentWnd`  
 Ein Zeiger auf das Dialogfeld über- oder Besitzer Fenster.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion erstellt nur das Objekt. Verwenden der `DoModal` Member-Funktion, um das Dialogfeld anzuzeigen.  
  
##  <a name="createprinterdc"></a>  CPrintDialogEx::CreatePrinterDC  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Handle für den neu erstellten Drucker-Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Der zurückgegebene Domänencontroller befindet sich auch in der **hDC** Mitglied [M_pdex](#m_pdex).  
  
 Diesen DC wird davon ausgegangen, dass der aktuelle Drucker-Gerätekontext und anderen zuvor abgerufene Drucker DCs müssen gelöscht werden. Diese Funktion kann aufgerufen werden, und der resultierende DC verwendet, ohne jemals Anzeige des Dialogfelds drucken.  
  
##  <a name="domodal"></a>  CPrintDialogEx::DoModal  
 Mit dieser Funktion können Sie die Windows-druckeigenschaftenblatt angezeigt und ermöglicht dem Benutzer verschiedene Druckoptionen, z. B. die Anzahl der Kopien, Seitenbereich, wählen und gibt an, ob Kopien sortiert werden sollen.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die INT_PTR zurück, dass der Wert tatsächlich ein HRESULT ist. Finden Sie im Abschnitt Rückgabewerte [PrintDlgEx](http://msdn.microsoft.com/library/windows/desktop/ms646942) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Optionen für Dialogfeld "Drucken" zu initialisieren, indem Sie Mitglieder festlegen möchten die `m_pdex` -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Nach dem Aufruf `DoModal`, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
 Wenn die **PD_RETURNDC** -Flag verwendet wird, beim Aufrufen `DoModal`, ein druckerdomänencontroller wird zurückgegeben, der **hDC** Mitglied [M_pdex](#m_pdex). Dieser Domänencontroller muss freigegeben werden, mit einem Aufruf von [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) durch den Aufrufer der `CPrintDialogEx`.  
  
##  <a name="getcopies"></a>CPrintDialogEx::GetCopies  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zum Abrufen der Anzahl von Kopien angefordert.  
  
```  
int GetCopies() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Kopien, die angefordert.  
  
##  <a name="getdefaults"></a>CPrintDialogEx::GetDefaults  
 Rufen Sie diese Funktion, um die Standardeinstellungen für Gerät als Standarddrucker abzurufen, ohne dass ein Dialogfeld angezeigt.  
  
```  
BOOL GetDefaults();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** bei Erfolg, andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Erstellt einen Drucker-Gerätekontext (DC) aus der [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES](../../mfc/reference/devnames-structure.md) Strukturen.  
  
 `GetDefaults`die druckeigenschaftenblatt wird nicht angezeigt werden. Stattdessen wird die **hDevNames** und **hDevMode-Feld** Mitglied [M_pdex](#m_pdex) , Handles für die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) und [DEVNAMES ](../../mfc/reference/devnames-structure.md) Strukturen, die für den System-Standarddrucker initialisiert werden. Beide **hDevNames** und **hDevMode-Feld** dürfen NULL sein, oder `GetDefaults` ein Fehler auftritt.  
  
 Wenn die **PD_RETURNDC** Flag festgelegt ist, diese Funktion wird nicht nur zurück **hDevNames** und **hDevMode-Feld** (befindet sich im **m_pdex.hDevNames** und **m_pdex.hDevMode**) an den Aufrufer jedoch auch einen Drucker-Gerätekontext in zurück **m_pdex.hDC**. Es liegt in der Verantwortung des Aufrufers, löschen die Drucker-Gerätekontext und rufen Sie die Windows [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579) Funktion auf die Handles Sie abschließend mit der `CPrintDialogEx` Objekt.  
  
##  <a name="getdevicename"></a>CPrintDialogEx::GetDeviceName  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) zum Abrufen des Namens des ausgewählten Druckers oder nach dem Aufruf [GetDefaults](#getdefaults) , den Namen des Standarddruckers abzurufen.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie einen Zeiger auf die `CString` zurückgegebenes Objekt `GetDeviceName` als Wert des `lpszDeviceName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getdevmode"></a>CPrintDialogEx::GetDevMode  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen von Informationen über das Druckgerät.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) Datenstruktur, die Informationen über die Initialisierung für Grafikgeräte und ein Druckertreiber-Umgebung enthält. Sie müssen den Arbeitsspeicher, bis diese Struktur mit dem Windows Entsperren [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) -Funktion, die im Windows SDK beschrieben wird.  
  
##  <a name="getdrivername"></a>CPrintDialogEx::GetDriverName  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) zum Abrufen des Namens des Gerätetreibers systemdefinierte Drucker.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` den systemdefinierte Treibernamen angeben.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie einen Zeiger auf die `CString` zurückgegebenes Objekt `GetDriverName` als Wert des `lpszDriverName` in einem Aufruf von [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="getportname"></a>CPrintDialogEx::GetPortName  
 Mit dieser Funktion wird nach dem Aufruf [DoModal](#domodal) oder [GetDefaults](#getdefaults) , den Namen des aktuell ausgewählten Drucker Ports abzurufen.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name des aktuell ausgewählten Drucker Ports.  
  
##  <a name="getprinterdc"></a>  CPrintDialogEx::GetPrinterDC  
 Gibt ein Handle für den Drucker-Gerätekontext zurück.  
  
```  
HDC GetPrinterDC() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für den Druckergerätekontext.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die Windows [DeleteDC](http://msdn.microsoft.com/library/windows/desktop/dd183533) Funktion, um den Gerätekontext löschen, wenn Sie fertig sind verwenden.  
  
##  <a name="m_pdex"></a>CPrintDialogEx::m_pdex  
 Eine PRINTDLGEX-Struktur, deren Mitglieder die Merkmale der dem Dialogfeldobjekt speichern.  
  
```  
PRINTDLGEX m_pdex;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CPrintDialogEx` -Objekt können Sie `m_pdex` festzulegende verschiedene Aspekte des Dialogfelds vor dem Aufruf der [DoModal](#domodal) Memberfunktion. Weitere Informationen zu den `m_pdex` -Struktur, finden Sie unter [PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) im Windows SDK.  
  
 Wenn Sie ändern die `m_pdex` Datenmember direkt, Sie Standardverhalten überschreiben.  
  
##  <a name="printall"></a>  CPrintDialogEx::PrintAll  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob alle Seiten im Dokument zu drucken.  
  
```  
BOOL PrintAll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn alle Seiten im Dokument werden gedruckt; andernfalls **"false"**.  
  
##  <a name="printcollate"></a>CPrintDialogEx::PrintCollate  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` zu bestimmen, ob der Drucker alle gedruckte Exemplare des Dokuments zu sortieren sollten.  
  
```  
BOOL PrintCollate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** klickt der Benutzer das Kontrollkästchen "Collate" im Dialogfeld; andernfalls **"false"**.  
  
##  <a name="printcurrentpage"></a>  CPrintDialogEx::PrintCurrentPage  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob die aktuelle Seite im Dokument zu drucken.  
  
```  
BOOL PrintCurrentPage() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** Wenn **aktuelle Seite drucken** in das Dialogfeld "Drucken" ausgewählt ist andernfalls **"false"**.  
  
##  <a name="printrange"></a>CPrintDialogEx::PrintRange  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob nur einen Bereich von Seiten im Dokument zu drucken.  
  
```  
BOOL PrintRange() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** sind nur ein Bereich von Seiten im Dokument werden gedruckt; andernfalls **"false"**.  
  
### <a name="remarks"></a>Hinweise  
 Der angegebene Seitenbereiche können bestimmt werden, von [M_pdex](#m_pdex) (finden Sie unter **nPageRanges**, **nMaxPageRanges**, und **LpPageRanges** in der [ PRINTDLGEX](http://msdn.microsoft.com/library/windows/desktop/ms646844) Struktur im Windows SDK).  
  
##  <a name="printselection"></a>CPrintDialogEx::PrintSelection  
 Mit dieser Funktion wird nach dem Aufruf `DoModal` bestimmt, ob nur die momentan ausgewählten Elemente zu drucken.  
  
```  
BOOL PrintSelection() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 **"True"** sind nur die ausgewählten Elemente werden gedruckt; andernfalls **"false"**.  
  
## <a name="see-also"></a>Siehe auch  
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CPrintInfo-Struktur](../../mfc/reference/cprintinfo-structure.md)
