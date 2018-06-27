---
title: CFontDialog Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CFontDialog
- AFXDLGS/CFontDialog
- AFXDLGS/CFontDialog::CFontDialog
- AFXDLGS/CFontDialog::DoModal
- AFXDLGS/CFontDialog::GetCharFormat
- AFXDLGS/CFontDialog::GetColor
- AFXDLGS/CFontDialog::GetCurrentFont
- AFXDLGS/CFontDialog::GetFaceName
- AFXDLGS/CFontDialog::GetSize
- AFXDLGS/CFontDialog::GetStyleName
- AFXDLGS/CFontDialog::GetWeight
- AFXDLGS/CFontDialog::IsBold
- AFXDLGS/CFontDialog::IsItalic
- AFXDLGS/CFontDialog::IsStrikeOut
- AFXDLGS/CFontDialog::IsUnderline
- AFXDLGS/CFontDialog::m_cf
dev_langs:
- C++
helpviewer_keywords:
- CFontDialog [MFC], CFontDialog
- CFontDialog [MFC], DoModal
- CFontDialog [MFC], GetCharFormat
- CFontDialog [MFC], GetColor
- CFontDialog [MFC], GetCurrentFont
- CFontDialog [MFC], GetFaceName
- CFontDialog [MFC], GetSize
- CFontDialog [MFC], GetStyleName
- CFontDialog [MFC], GetWeight
- CFontDialog [MFC], IsBold
- CFontDialog [MFC], IsItalic
- CFontDialog [MFC], IsStrikeOut
- CFontDialog [MFC], IsUnderline
- CFontDialog [MFC], m_cf
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ff998b8be93d1248775d49bcef7680f4c9777fd4
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953674"
---
# <a name="cfontdialog-class"></a>CFontDialog-Klasse
Können Sie ein Dialogfeld für die Auswahl von Schriftarten in die Anwendung integrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|Erstellt ein `CFontDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CFontDialog::GetCharFormat](#getcharformat)|Ruft ab, die Formatierung der ausgewählten Schriftart.|  
|[CFontDialog::GetColor](#getcolor)|Gibt die Farbe der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Weist die Merkmale der aktuell ausgewählten Schriftart eine `LOGFONT` Struktur.|  
|[CFontDialog::GetFaceName](#getfacename)|Gibt den Schriftartnamen der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetSize](#getsize)|Gibt den Schriftgrad der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetStyleName](#getstylename)|Gibt den Formatvorlagennamen der ausgewählten Schriftart.|  
|[CFontDialog::GetWeight](#getweight)|Gibt die Schriftbreite der ausgewählten Schriftart.|  
|[CFontDialog::IsBold](#isbold)|Bestimmt, ob die Schriftart fett formatiert ist.|  
|[CFontDialog::IsItalic](#isitalic)|Bestimmt, ob die Schriftart kursiv formatiert ist.|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|Bestimmt, ob die Schriftart durchgestrichen dargestellt wird.|  
|[CFontDialog::IsUnderline](#isunderline)|Bestimmt, ob die Schriftart unterstrichen ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|Eine Struktur, die zum Anpassen einer `CFontDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CFontDialog` Objekt wird ein Dialogfeld mit einer Liste von Schriftarten, die zurzeit im System installiert sind. Der Benutzer kann eine besondere Schriftart aus der Liste auswählen und diese Auswahl wird dann wieder an die Anwendung gemeldet.  
  
 So erstellen Sie eine `CFontDialog` Objekt, verwenden Sie den bereitgestellten Konstruktor oder leiten Sie eine neue Unterklasse und Ihre eigenen benutzerdefinierten Konstruktor verwenden.  
  
 Einmal eine `CFontDialog` -Objekts können Sie mithilfe der `m_cf` Struktur, um die Werte oder Zustände von Steuerelementen in das Dialogfeld zu initialisieren. Die [M_cf](#m_cf) Struktur ist vom Typ [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832). Weitere Informationen zu dieser Struktur finden Sie im Windows-SDK.  
  
 Rufen Sie nach dem initialisieren das Dialogfeldobjekt-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen, und ermöglicht dem Benutzer das auswählen eine Schriftart. `DoModal` Gibt zurück, ob der Benutzer die OK ausgewählt ( **IDOK**) oder "Abbrechen" ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, können Sie eine der `CFontDialog`des Memberfunktionen zum Abrufen von Informationen vom Benutzer eingegeben.  
  
 Sie können die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) -Funktion zu bestimmen, ob der Fehler während der Initialisierung des Dialogfelds und erfahren Sie mehr über den Fehler. Weitere Informationen zu dieser Funktion finden Sie im Windows-SDK.  
  
 `CFontDialog` basiert auf der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher ausgeliefert wird.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFontDialog`, geben Sie eine benutzerdefinierte Dialogfeldvorlage und hinzufügen eine meldungszuordnung, um die benachrichtigungsmeldungen aus den erweiterten Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten mit der Basisklasse übergeben werden.  
  
 Anpassen von die Hookfunktion ist nicht erforderlich.  
  
 Weitere Informationen zur Verwendung von `CFontDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cfontdialog"></a>  CFontDialog::CFontDialog  
 Erstellt ein `CFontDialog`-Objekt.  
  
```  
CFontDialog(
    LPLOGFONT lplfInitial = NULL,  
    DWORD dwFlags = CF_EFFECTS | CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);

CFontDialog(
    const CHARFORMAT& charformat,  
    DWORD dwFlags = CF_SCREENFONTS,  
    CDC* pdcPrinter = NULL,  
    CWnd* pParentWnd = NULL);  
```  
  
### <a name="parameters"></a>Parameter  
 *plfInitial*  
 Ein Zeiger auf eine [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Datenstruktur, die Sie einige der Schriftmerkmale festlegen kann.  
  
 *Zeichenformat*  
 Ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Datenstruktur, die Ihnen ermöglicht, legen Sie einige der Schriftmerkmale in einem Rich-edit-Steuerelement.  
  
 *dwFlags*  
 Bestimmt eine oder mehrere Schriftart-wählen-Flags. Ein oder mehrere Vorgabewerte können mit dem bitweisen OR-Operator kombiniert werden. Wenn Sie den `m_cf.Flag`s-Strukturmember ändern, stellen Sie sicher, dass Sie einen bitweisen OR-Operator bei Ihren Änderungen verwenden, um das Standardverhalten unverändert zu lassen. Finden Sie ausführliche Informationen zu diesen Flags, die Beschreibung des der [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) Struktur im Windows SDK.  
  
 *pdcPrinter*  
 Ein Zeiger auf einen Druckgerätekontext. Sofern bereitgestellt, verweist dieser Parameter auf einen Druckgerätekontext für den Drucker, auf dem die Schriftarten ausgewählt werden sollen.  
  
 *pParentWnd*  
 Ein Zeiger auf das übergeordnete Fenster oder das Besitzerfenster des Schriftartdialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Konstruktor automatisch die Member der `CHOOSEFONT`-Struktur ausfüllt. Sie sollten diese nur ändern, wenn Sie ein anderes Schriftartdialogfeld als das standardmäßige verwenden möchten.  
  
> [!NOTE]
>  Die erste Version dieser Funktion existiert nur, wenn es keine Unterstützung für das Rich-Edit-Steuerelement gibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#78](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>  CFontDialog::DoModal  
 Mit dieser Funktion wird zum Anzeigen der Windows allgemeine Schriftart (Dialogfeld), und ermöglicht dem Benutzer das auswählen eine Schriftart.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um festzustellen, ob ein Fehler aufgetreten.  
  
 **IDOK** und **IDCANCEL** sind Konstanten, die angeben, ob der Benutzer die Schaltfläche OK oder "Abbrechen" ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Schriftart Dialogfeld-Steuerelemente initialisieren, indem Sie Mitglieder festlegen möchten die [M_cf](#m_cf) -Struktur, ergreifen Sie dies vor dem Aufruf `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
### <a name="example"></a>Beispiel  
  Siehe Beispiele für [CFontDialog::CFontDialog](#cfontdialog) und [CFontDialog::GetColor](#getcolor).  
  
##  <a name="getcharformat"></a>  CFontDialog::GetCharFormat  
 Ruft ab, die Formatierung der ausgewählten Schriftart.  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *CF*  
 Ein [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die Informationen über die Formatierung der ausgewählten Schriftart enthält.  
  
##  <a name="getcolor"></a>  CFontDialog::GetColor  
 Mit dieser Funktion wird zum Abrufen der ausgewählten Farbe.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe der ausgewählten Schriftart.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#79](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="getcurrentfont"></a>  CFontDialog::GetCurrentFont  
 Mit dieser Funktion können Sie die Eigenschaften des aktuell ausgewählten Schriftart auf Mitglieder der Zuweisen einer [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>Parameter  
 *lplf*  
 Ein Zeiger auf eine `LOGFONT` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Andere `CFontDialog` Memberfunktionen werden bereitgestellt, um die einzelnen Eigenschaften der aktuellen Schriftart zugreifen.  
  
 Wenn diese Funktion, während eines Aufrufs aufgerufen wird [DoModal](#domodal), gibt die aktuelle Auswahl zu dem Zeitpunkt (was der Benutzer sieht oder wurde geändert, die im Dialogfeld "). Wenn diese Funktion, nach einem Aufruf von aufgerufen wird `DoModal` (nur, wenn `DoModal` gibt **IDOK**), wird zurückgegeben, was den Benutzer tatsächlich aktiviert.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#80](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="getfacename"></a>  CFontDialog::GetFaceName  
 Mit dieser Funktion wird zum Abrufen des Schriftartnamens der ausgewählten Schriftart.  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Des Schriftartnamens ausgewählten Schriftart der `CFontDialog` (Dialogfeld).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#81](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="getsize"></a>  CFontDialog::GetSize  
 Mit dieser Funktion wird zum Abrufen der Größe der ausgewählten Schriftart.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Schriftgrad, Uhrzeitdaten eines Punkts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#82](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="getstylename"></a>  CFontDialog::GetStyleName  
 Mit dieser Funktion wird zum Abrufen der Namen der Formatvorlage der ausgewählten Schriftart.  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Stil der Schriftart.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#83](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="getweight"></a>  CFontDialog::GetWeight  
 Mit dieser Funktion wird zum Abrufen der Breite der ausgewählten Schriftart.  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der ausgewählten Schriftart.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zu die Gewichtung einer Schriftart, finden Sie unter [CFont::](../../mfc/reference/cfont-class.md#createfont).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#84](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="isbold"></a>  CFontDialog::IsBold  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart fett formatiert ist.  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart fett Merkmal aktiviert wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#85](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="isitalic"></a>  CFontDialog::IsItalic  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart kursiv formatiert ist.  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart kursive Merkmal aktiviert wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#86](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="isstrikeout"></a>  CFontDialog::IsStrikeOut  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart mit durchgestrichen angezeigt wird.  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart durchgestrichen Merkmal aktiviert wurde; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#87](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="isunderline"></a>  CFontDialog::IsUnderline  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart unterstrichen ist.  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart Merkmal "Unterstreichen" aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#88](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="m_cf"></a>  CFontDialog::m_cf  
 Eine Struktur, deren Mitglieder die Merkmale der dem Dialogfeldobjekt speichern.  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CFontDialog` -Objekt können Sie `m_cf` so ändern Sie verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Memberfunktion. Weitere Informationen zu dieser Struktur finden Sie unter [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView#89](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)



