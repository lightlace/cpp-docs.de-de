---
title: CMFCColorDialog Klasse | Microsoft Docs
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
ms.openlocfilehash: 21114a3c04f96f2867f5440d47e856958060233e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33367915"
---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog-Klasse
Die `CMFCColorDialog` Klasse stellt ein Farbauswahl-Dialogfeld.  
  
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
|[CMFCColorDialog::GetColor](#getcolor)|Gibt den aktuellen ausgewählten Farbe zurück.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Gibt die Farben-Palette zurück.|  
|`CMFCColorDialog::PreTranslateMessage`|Übersetzt fenstermeldungen, bevor sie an verteilt wurden die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Leitet eine Palette aus der Systempalette an.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Legt die aktuelle ausgewählte Farbe fest.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Legt die Farbe fest, das am häufigsten gleichbedeutend mit einem angegebenen RGB-Wert.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Wählt einen RGB-Wert für die erste Eigenschaftenseite an.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Wählt einen RGB-Wert für die zweite Eigenschaftenseite an.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|name|Beschreibung|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE` Wenn das Dialogfeld zur Farbauswahl eigene Farben-Palette verwendet oder `FALSE` Wenn im Dialogfeld eine Palette, die im angegebenen verwendet der `CMFCColorDialog` Konstruktor.|  
|`m_bPickerMode`|`TRUE` während der Benutzer eine Farbe aus dem Auswahldialogfeld auswählt; andernfalls `FALSE`.|  
|`m_btnColorSelect`|Schaltfläche für die Farbe, die der Benutzer ausgewählt hat.|  
|`m_CurrentColor`|Die zurzeit ausgewählte Farbe.|  
|`m_hcurPicker`|Der Cursor, der verwendet wird, um eine Farbe auswählen.|  
|`m_NewColor`|Die potenziellen ausgewählte Farbe, die dauerhaft ausgewählt oder die ursprüngliche Farbe wiederhergestellt werden kann.|  
|`m_pColourSheetOne`|Ein Zeiger auf die erste Seite Farbe Auswahl Eigenschaftenblatt.|  
|`m_pColourSheetTwo`|Ein Zeiger auf die zweite Seite Farbe Auswahl Eigenschaftenblatt.|  
|`m_pPalette`|Die aktuelle logische Palette.|  
|`m_pPropSheet`|Ein Zeiger auf die Eigenschaftenseite für das Dialogfeld zur Farbauswahl.|  
|`m_wndColors`|Eine Farbe Datumsauswahl Control-Objekt.|  
|`m_wndStaticPlaceHolder`|Ein statisches Steuerelement, das ein Platzhalter für das Eigenschaftenblatt für Farbe Auswahl ist.|  
  
## <a name="remarks"></a>Hinweise  
 Das Dialogfeld zur Farbauswahl wird als ein Eigenschaftenblatt mit zwei Seiten angezeigt. Auf der ersten Seite Wählen Sie eine standardmäßige Farbe aus der Systempalette; auf der zweiten Seite Wählen Sie eine benutzerdefinierte Farbe aus.  
  
 Für das Konstruieren einer `CMFCColorDialog` Objekt auf dem Stapel, und rufen Sie dann `DoModal`, übergeben die Ausgangsfarbe als Parameter an die `CMFCColorDialog` Konstruktor. Das Dialogfeld zur Farbauswahl erstellt dann mehrere [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Objekte behandelt jede Farbpalette.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Dialogfeld Farbe konfigurieren mithilfe verschiedener Methoden in der `CMFCColorDialog` Klasse. Im Beispiel wird gezeigt, wie die aktuelle und die neue Farben im Dialogfeld festgelegt, und wie die Rot-, Grün- und blauen-Komponenten einer ausgewählten Farbe auf den zwei Eigenschaftenseiten für das Dialogfeld "Farbe" festgelegt. In diesem Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
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
 [in] `clrInit`  
 Die Standardauswahl für die Farbe. Wenn kein Wert angegeben wird, ist die Standardeinstellung RGB(0,0,0) (Schwarz).  
  
 [in] `dwFlags`  
 (Reserviert).  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das Dialogfeld über- oder Besitzer Fenster.  
  
 [in] `hPal`  
 Ein Handle für eine Farbpalette.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getcolor"></a>  CMFCColorDialog::GetColor  
 Ruft die Farbe, die der Benutzer über das Dialogfeld "Farbe" auswählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die RGB-Informationen für die Farbe ausgewählt, die im Dialogfeld "Farbe" enthält.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird nach dem Aufruf der `DoModal` Methode.  
  
##  <a name="getpalette"></a>  CMFCColorDialog::GetPalette  
 Ruft die Farbpalette, die im aktuellen Dialogfeld "Farbe" verfügbar ist.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CPalette` -Objekt, das im angegebenen der `CMFCColorDialog` Konstruktor.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbpalette gibt die Farben, die der Benutzer auswählen können.  
  
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
 [in] `rgb`  
 Ein RGB-Wert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setnewcolor"></a>  CMFCColorDialog::SetNewColor  
 Legt die aktuelle Farbe der Farbe in der aktuellen Palette, die am ähnlichsten ist.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rgb`  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , die eine RGB-Farbe angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpageone"></a>  CMFCColorDialog::SetPageOne  
 Explizit gibt die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf der ersten Eigenschaftenseite ein Dialogfeld "Farbe" ein.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `R`  
 Gibt die rote Komponente RGB-Wertes.  
  
 [in] `G`  
 Gibt die grünen Komponente RGB-Wertes.  
  
 [in] `B`  
 Gibt die blaue Komponente RGB-Wertes.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setpagetwo"></a>  CMFCColorDialog::SetPageTwo  
 Gibt explizit den Rot-, Grün- und blauen-Komponenten einer ausgewählten Farbe, auf der zweiten Eigenschaftenseite ein Dialogfeld "Farbe".  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `R`  
 Gibt eine rote Komponente RGB-Wertes  
  
 [in] `G`  
 Gibt eine grüne Komponente RGB-Wertes  
  
 [in] `B`  
 Gibt eine blaue Komponente RGB-Wertes  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md)
