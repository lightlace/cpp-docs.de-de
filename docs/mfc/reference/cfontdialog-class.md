---
title: CFontDialog Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CFontDialog class
- dialog boxes, fonts
- fonts
- fonts, selecting
ms.assetid: 6228d500-ed0f-4156-81e5-ab0d57d1dcf4
caps.latest.revision: 25
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6f277ba8fba72106918e03397f57726bd5beb0ff
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cfontdialog-class"></a>CFontDialog-Klasse
Können Sie ein Dialogfeld für die Auswahl von Schriftarten in Ihre Anwendung integrieren.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CFontDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::CFontDialog](#cfontdialog)|Erstellt ein `CFontDialog`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::DoModal](#domodal)|Zeigt das Dialogfeld an und ermöglicht dem Benutzer eine Auswahl treffen.|  
|[CFontDialog::GetCharFormat](#getcharformat)|Ruft ab, die Formatierung der ausgewählten Schriftart.|  
|[CFontDialog::GetColor](#getcolor)|Gibt die Farbe der ausgewählten Schriftart.|  
|[CFontDialog::GetCurrentFont](#getcurrentfont)|Die Merkmale des derzeit ausgewählten Schriftart zum weist eine `LOGFONT` Struktur.|  
|[CFontDialog::GetFaceName](#getfacename)|Gibt den Schriftartnamen der ausgewählten Schriftart zurück.|  
|[CFontDialog::GetSize](#getsize)|Gibt den Schriftgrad der ausgewählten Schriftart.|  
|[CFontDialog::GetStyleName](#getstylename)|Gibt den Formatvorlagennamen der ausgewählten Schriftart.|  
|[CFontDialog::GetWeight](#getweight)|Gibt die Breite der ausgewählten Schriftart.|  
|[CFontDialog::IsBold](#isbold)|Bestimmt, ob die Schriftart fett formatiert ist.|  
|[CFontDialog::IsItalic](#isitalic)|Bestimmt, ob die Schriftart kursiv ist.|  
|[CFontDialog::IsStrikeOut](#isstrikeout)|Bestimmt, ob die Schriftart durchgestrichen dargestellt wird.|  
|[CFontDialog::IsUnderline](#isunderline)|Bestimmt, ob die Schrift unterstrichen ist.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CFontDialog::m_cf](#m_cf)|Eine Struktur, die zur Anpassung einer `CFontDialog` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `CFontDialog` -Objekt ist ein Dialogfeld mit einer Liste von Schriftarten, die zurzeit im System installiert sind. Der Benutzer kann eine bestimmte Schriftart aus der Liste auswählen und diese Auswahl wird dann wieder an die Anwendung gemeldet.  
  
 Erstellt ein `CFontDialog` Objekt verwenden Sie den bereitgestellten Konstruktor oder leiten Sie eine neue Unterklasse und Ihre eigenen benutzerdefinierten Konstruktor.  
  
 Einmal eine `CFontDialog` -Objekts, können Sie die `m_cf` Struktur, um die Werte oder Zustände von Steuerelementen im Dialogfeld zu initialisieren. Die [M_cf](#m_cf) Struktur ist vom Typ [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832). Weitere Informationen zu dieser Struktur finden Sie im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Rufen Sie nach dem initialisieren das Dialogfeldobjekt-Steuerelemente, die `DoModal` Memberfunktion, um das Dialogfeld anzuzeigen und dem Benutzer ermöglichen, eine Schriftart auswählen. `DoModal`Gibt zurück, ob der Benutzer OK ausgewählt ( **IDOK**) oder Abbrechen ( **IDCANCEL**) Schaltfläche.  
  
 Wenn `DoModal` gibt **IDOK**, verwenden Sie eine der `CFontDialog`Member-Funktionen zum Abrufen von Informationen vom Benutzer eingeben.  
  
 Verwenden Sie die Fenster [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) -Funktion zu bestimmen, ob Fehler während der Initialisierung des Dialogfelds und Weitere Informationen zu dem Fehler. Weitere Informationen zu dieser Funktion finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `CFontDialog`Abhängig von der COMMDLG. DLL-Datei, die mit Windows-Versionen 3.1 und höher enthalten ist.  
  
 Um das Dialogfeld anzupassen, leiten Sie eine Klasse von `CFontDialog`, geben Sie eine benutzerdefinierte Vorlage und hinzufügen eine meldungszuordnung, um die Benachrichtigung über die erweiterte Steuerelemente zu verarbeiten. Alle nicht verarbeiteten Nachrichten sollten an die Basisklasse übergeben werden.  
  
 Es ist nicht erforderlich, die Hookfunktion anpassen.  
  
 Weitere Informationen zur Verwendung von `CFontDialog`, finden Sie unter [allgemeine Dialogfeldklassen](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFontDialog`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdlgs.h  
  
##  <a name="cfontdialog"></a>CFontDialog::CFontDialog  
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
 l`plfInitial`  
 Ein Zeiger auf eine ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037) -Datenstruktur, die Sie einige der Schriftmerkmale festlegen kann.  
  
 `charFormat`  
 Ein Zeiger auf eine [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) -Datenstruktur, können Sie einige der Schriftmerkmale in einem Rich festlegen, edit-Steuerelement.  
  
 `dwFlags`  
 Bestimmt eine oder mehrere Schriftart-wählen-Flags. Ein oder mehrere Vorgabewerte können mit dem bitweisen OR-Operator kombiniert werden. Wenn Sie den `m_cf.Flag`s-Strukturmember ändern, stellen Sie sicher, dass Sie einen bitweisen OR-Operator bei Ihren Änderungen verwenden, um das Standardverhalten unverändert zu lassen. Informationen zu diesen Flags, finden Sie unter der Beschreibung der [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) -Struktur im der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 pdcPrinter  
 Ein Zeiger auf einen Druckgerätekontext. Sofern bereitgestellt, verweist dieser Parameter auf einen Druckgerätekontext für den Drucker, auf dem die Schriftarten ausgewählt werden sollen.  
  
 `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster oder das Besitzerfenster des Schriftartdialogfelds.  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass der Konstruktor automatisch die Member der `CHOOSEFONT`-Struktur ausfüllt. Sie sollten diese nur ändern, wenn Sie ein anderes Schriftartdialogfeld als das standardmäßige verwenden möchten.  
  
> [!NOTE]
>  Die erste Version dieser Funktion existiert nur, wenn es keine Unterstützung für das Rich-Edit-Steuerelement gibt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#78;](../../mfc/codesnippet/cpp/cfontdialog-class_1.cpp)]  
  
##  <a name="domodal"></a>CFontDialog::DoModal  
 Rufen Sie diese Funktion zeigt das Dialogfeld allgemeine Schriftart Windows und der Benutzer eine Schriftart aus.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Rückgabewert  
 **IDOK** oder **IDCANCEL**. Wenn **IDCANCEL** wird zurückgegeben, rufen Sie die Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) Funktion, um zu bestimmen, ob ein Fehler aufgetreten ist.  
  
 **IDOK** und **IDCANCEL** Konstanten, die angeben, ob der Benutzer auf die Schaltfläche OK oder Abbrechen ausgewählt werden.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie die verschiedenen Schriftart Dialogfeld-Steuerelemente zu initialisieren, indem Sie Mitglieder festlegen möchten die [M_cf](#m_cf) -Struktur, Sie sollten dies tun, vor dem Aufruf von `DoModal`, aber erst, nachdem das Dialogfeldobjekt erstellt wird.  
  
 Wenn `DoModal` gibt **IDOK**, Sie können andere Memberfunktionen aufrufen zum Abrufen von Einstellungen oder Eingabe von Informationen vom Benutzer in das Dialogfeld.  
  
### <a name="example"></a>Beispiel  
  Beispiele finden Sie [CFontDialog::CFontDialog](#cfontdialog) und [CFontDialog::GetColor](#getcolor).  
  
##  <a name="getcharformat"></a>CFontDialog::GetCharFormat  
 Ruft ab, die Formatierung der ausgewählten Schriftart.  
  
```  
void GetCharFormat(CHARFORMAT& cf) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `cf`  
 Ein [CHARFORMAT](http://msdn.microsoft.com/library/windows/desktop/bb787881) Struktur, die Informationen über die Formatierung der ausgewählten Schriftart enthält.  
  
##  <a name="getcolor"></a>CFontDialog::GetColor  
 Rufen Sie diese Funktion, um die ausgewählte Schriftfarbe abzurufen.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe der ausgewählten Schriftart.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#79;](../../mfc/codesnippet/cpp/cfontdialog-class_2.cpp)]  
  
##  <a name="getcurrentfont"></a>CFontDialog::GetCurrentFont  
 Mit dieser Funktion können Sie die Mitglieder der Merkmale der derzeit ausgewählten Schriftart Zuweisen einer [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) Struktur.  
  
```  
void GetCurrentFont(LPLOGFONT lplf);
```  
  
### <a name="parameters"></a>Parameter  
 *lplf*  
 Ein Zeiger auf eine `LOGFONT` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Andere `CFontDialog` Member-Funktionen werden bereitgestellt, um Zugriff auf einzelne Eigenschaften der aktuellen Schriftart.  
  
 Wenn diese Funktion, während eines Aufrufs aufgerufen wird [DoModal](#domodal), wird die aktuelle Auswahl zu dem Zeitpunkt (was der Benutzer sieht oder wurde im Dialogfeld geändert). Wenn diese Funktion, nach einem Aufruf von aufgerufen wird `DoModal` (nur, wenn `DoModal` gibt **IDOK**), was den Benutzer tatsächlich aktiviert wird.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#80;](../../mfc/codesnippet/cpp/cfontdialog-class_3.cpp)]  
  
##  <a name="getfacename"></a>CFontDialog::GetFaceName  
 Rufen Sie diese Funktion zum Abrufen des Schriftartnamens der ausgewählten Schriftart.  
  
```  
CString GetFaceName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Den Schriftartnamen des ausgewählten Schriftart die `CFontDialog` im Dialogfeld.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#81;](../../mfc/codesnippet/cpp/cfontdialog-class_4.cpp)]  
  
##  <a name="getsize"></a>CFontDialog::GetSize  
 Rufen Sie diese Funktion zum Abrufen der Größe der ausgewählten Schriftart.  
  
```  
int GetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Schriftgrad, Uhrzeitdaten eines Punkts.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#82;](../../mfc/codesnippet/cpp/cfontdialog-class_5.cpp)]  
  
##  <a name="getstylename"></a>CFontDialog::GetStyleName  
 Rufen Sie diese Funktion zum Abrufen der Name der ausgewählten Schriftart.  
  
```  
CString GetStyleName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Name der Schriftart.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&83;](../../mfc/codesnippet/cpp/cfontdialog-class_6.cpp)]  
  
##  <a name="getweight"></a>CFontDialog::GetWeight  
 Rufen Sie diese Funktion zum Abrufen der Breite der ausgewählten Schriftart.  
  
```  
int GetWeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Gewichtung der ausgewählten Schriftart.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen auf das Gewicht einer Schriftart finden Sie unter [CFont::](../../mfc/reference/cfont-class.md#createfont).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#84;](../../mfc/codesnippet/cpp/cfontdialog-class_7.cpp)]  
  
##  <a name="isbold"></a>CFontDialog::IsBold  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart fett formatiert ist.  
  
```  
BOOL IsBold() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart fett Merkmal aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#85;](../../mfc/codesnippet/cpp/cfontdialog-class_8.cpp)]  
  
##  <a name="isitalic"></a>CFontDialog::IsItalic  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart kursiv formatiert ist.  
  
```  
BOOL IsItalic() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart kursive Merkmal aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#86;](../../mfc/codesnippet/cpp/cfontdialog-class_9.cpp)]  
  
##  <a name="isstrikeout"></a>CFontDialog::IsStrikeOut  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart durchgestrichen dargestellt wird.  
  
```  
BOOL IsStrikeOut() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart durchgestrichen Merkmal aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#87;](../../mfc/codesnippet/cpp/cfontdialog-class_10.cpp)]  
  
##  <a name="isunderline"></a>CFontDialog::IsUnderline  
 Rufen Sie diese Funktion, um zu bestimmen, ob die ausgewählte Schriftart unterstrichen ist.  
  
```  
BOOL IsUnderline() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die ausgewählte Schriftart die Unterstreichung-Eigenschaft aktiviert ist; andernfalls 0.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#88;](../../mfc/codesnippet/cpp/cfontdialog-class_11.cpp)]  
  
##  <a name="m_cf"></a>CFontDialog::m_cf  
 Eine Struktur, deren Mitglieder die Merkmale des Dialog-Objekts gespeichert.  
  
```  
CHOOSEFONT m_cf;  
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen einer `CFontDialog` -Objekt können Sie `m_cf` so ändern Sie verschiedene Aspekte des Dialogfelds vor dem Aufruf der `DoModal` Member-Funktion. Weitere Informationen zu dieser Struktur finden Sie unter [CHOOSEFONT](http://msdn.microsoft.com/library/windows/desktop/ms646832) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDocView&#89;](../../mfc/codesnippet/cpp/cfontdialog-class_12.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel HIERSVR](../../visual-cpp-samples.md)   
 [CCommonDialog-Klasse](../../mfc/reference/ccommondialog-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)




