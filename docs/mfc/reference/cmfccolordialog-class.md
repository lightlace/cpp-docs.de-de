---
title: CMFCColorDialog-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::CMFCColorDialog
- AFXCOLORDIALOG/CMFCColorDialog::GetColor
- AFXCOLORDIALOG/CMFCColorDialog::GetPalette
- AFXCOLORDIALOG/CMFCColorDialog::RebuildPalette
- AFXCOLORDIALOG/CMFCColorDialog::SetCurrentColor
- AFXCOLORDIALOG/CMFCColorDialog::SetNewColor
- AFXCOLORDIALOG/CMFCColorDialog::SetPageOne
- AFXCOLORDIALOG/CMFCColorDialog::SetPageTwo
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog [MFC], CMFCColorDialog
- CMFCColorDialog [MFC], GetColor
- CMFCColorDialog [MFC], GetPalette
- CMFCColorDialog [MFC], RebuildPalette
- CMFCColorDialog [MFC], SetCurrentColor
- CMFCColorDialog [MFC], SetNewColor
- CMFCColorDialog [MFC], SetPageOne
- CMFCColorDialog [MFC], SetPageTwo
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb3a2bce257717c695c1458b12f3e6d4f11b9d7a
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849736"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog-Klasse
Die `CMFCColorDialog` Klasse stellt ein Dialogfeld zur Farbauswahl dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Erstellt ein `CMFCColorDialog`-Objekt.|  
|`CMFCColorDialog::~CMFCColorDialog`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Gibt die aktuelle ausgewählte Farbe zurück.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Gibt die Farbe der Palette zurück.|  
|`CMFCColorDialog::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie um weitergeleitet werden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Leitet eine Palette aus der Systempalette an.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Legt die aktuelle ausgewählte Farbe fest.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Legt die Farbe am gleich einem angegebenen RGB-Wert fest.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Wählt einen RGB-Wert für die erste Eigenschaftenseite an.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Wählt einen RGB-Wert für die zweite Eigenschaftenseite.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_bIsMyPalette`|True, wenn das Dialogfeld zur Farbauswahl eine eigene Farben-Palette verwendet bzw. FALSE, wenn das Dialogfeld eine Palette verwendet, die im angegebenen die `CMFCColorDialog` Konstruktor.|  
|`m_bPickerMode`|True, während der Benutzer eine Farbe im Dialogfeld "Auswahl" auswählen. andernfalls "false".|  
|`m_btnColorSelect`|Die farbenschaltfläche, die der Benutzer ausgewählt hat.|  
|`m_CurrentColor`|Die zurzeit ausgewählte Farbe.|  
|`m_hcurPicker`|Der Cursor, der verwendet wird, um eine Farbe auszuwählen.|  
|`m_NewColor`|Die potenzielle ausgewählte Farbe, die dauerhaft ausgewählt oder auf die ursprüngliche Farbe wiederhergestellt werden kann.|  
|`m_pColourSheetOne`|Ein Zeiger auf die erste Seite das Eigenschaftenblatt der Color-Auswahl.|  
|`m_pColourSheetTwo`|Ein Zeiger auf die zweite Seite das Eigenschaftenblatt der Color-Auswahl.|  
|`m_pPalette`|Die aktuelle logische Palette.|  
|`m_pPropSheet`|Ein Zeiger auf das Eigenschaftenfenster für das Dialogfeld zur Farbauswahl.|  
|`m_wndColors`|Ein Objekt der Farbe Zeitauswahl-Steuerelement.|  
|`m_wndStaticPlaceHolder`|Ein statisches Steuerelement, das ist ein Platzhalter für das Eigenschaftenblatt der Color-Auswahl.|  
  
## <a name="remarks"></a>Hinweise  
 Das Dialogfeld zur Farbauswahl wird als ein Eigenschaftenblatt mit zwei Seiten angezeigt. Auf der ersten Seite Wählen Sie eine Standardfarbe aus der Systempalette an; Klicken Sie auf der zweiten Seite Wählen Sie eine benutzerdefinierte Farbe aus.  
  
 Kann eine `CMFCColorDialog` -Objekt auf dem Stapel, und rufen dann `DoModal`, übergeben die Ausgangsfarbe, als Parameter an die `CMFCColorDialog` Konstruktor. Das Dialogfeld zur Farbauswahl erstellt dann mehrere [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Objekte jedes Farben-Palette zu behandeln.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Dialogfeld "Farbe" konfigurieren "mithilfe verschiedener Methoden in der `CMFCColorDialog` Klasse. Das Beispiel zeigt, wie die aktuelle und die neuen Farben im Dialogfeld festgelegt, und wie Sie die Komponenten roten, grünen und blauen einer ausgewählten Farbe für die zwei Eigenschaftenseiten das Dialogfeld "Farbe" festlegen. In diesem Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#3](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolordialog.h  
  
##  <a name="cmfccolordialog"></a>  CMFCColorDialog::CMFCColorDialog  
 Erstellt ein `CMFCColorDialog`-Objekt.  
  
```  
CMFCColorDialog(
    COLORREF clrInit=0,  
    DWORD dwFlags=0,  
    CWnd* pParentWnd=NULL,  
    HPALETTE hPal=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *ClrInit*  
 Die Standardauswahl für die Farbe. Wenn kein Wert angegeben wird, ist die Standardeinstellung RGB(0,0,0) (Schwarz).  
  
 [in] *DwFlags*  
 (Reserviert).  
  
 [in] *pParentWnd*  
 Ein Zeiger auf das übergeordnete Element oder Besitzer des Dialogfelds-Fenster.  
  
 [in] *hPal*  
 Ein Handle für eine Farbpalette.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 Ruft die Farbe, die der Benutzer das Dialogfeld "Farbe" auswählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) -Wert, der den RGB-Informationen für das Dialogfeld "Farbe" ausgewählte Farbe an.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion aufzurufen, nachdem Sie die `DoModal` Methode.  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 Ruft die Farbpalette, die im aktuellen Dialogfeld "Farbe" verfügbar ist.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CPalette` -Objekt, das im angegebenen die `CMFCColorDialog` Konstruktor.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbpalette gibt an, die Farben, die der Benutzer auswählen kann.  
  
##  <a name="rebuildpalette"></a>  CMFCColorDialog::RebuildPalette  
 Leitet eine Palette aus der Systempalette an.  
  
```  
void RebuildPalette();
```  
  
##  <a name="setcurrentcolor"></a>  CMFCColorDialog::SetCurrentColor  
 Legt die aktuelle Farbe des Dialogfelds fest.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Rgb*  
 Ein RGB-Farbwert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 Legt die aktuelle Farbe der Farbe in der aktuellen Palette, die am ähnlichsten ist.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Rgb*  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , die eine RGB-Farbe angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 Gibt explizit an die Komponenten roten, grünen und blauen einer ausgewählten Farbe, auf die erste Seite ein Dialogfeld Farbe.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *R*  
 Gibt an, der roten Anteil der RGB-Wert.  
  
 [in] *G*  
 Gibt an, der grünen Anteil der RGB-Wert.  
  
 [in] *B*  
 Gibt die blaue Komponente den RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 Gibt explizit an die Komponenten roten, grünen und blauen einer ausgewählten Farbe, auf die zweite Seite ein Dialogfeld Farbe.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *R*  
 Gibt eine rote den RGB-Wert-Komponente  
  
 [in] *G*  
 Gibt eine grüne RGB-Wert-Komponente  
  
 [in] *B*  
 Gibt an, eine blaue Komponente des RGB-Wert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md)
