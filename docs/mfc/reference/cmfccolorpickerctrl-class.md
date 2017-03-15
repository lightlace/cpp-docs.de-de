---
title: CMFCColorPickerCtrl-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorPickerCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPickerCtrl class
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
caps.latest.revision: 33
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
ms.openlocfilehash: 0a819d04535ba965e2c1a10f3761c442c9840538
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl-Klasse
Die `CMFCColorPickerCtrl` Klasse bietet Funktionen für ein Steuerelement, das verwendet wird, um Farben auszuwählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Erstellt ein `CMFCColorPickerCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Ruft die Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Ruft die Werte für Farbton, Helligkeit und die Sättigung der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Ruft den Farbtonkomponente der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Ruft die Komponente Intensität der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Ruft die Sättigungskomponente der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Legt die aktuelle Farbe die Farbe, die durch den angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definiert.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Legt die aktuelle Farbe auf den angegebenen RGB-Farbwert fest.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Legt die aktuelle Farbe auf den angegebenen Wert der HLS-Farbe fest.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Ändert den Farbtonkomponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Ändert die Intensität Komponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Legt die Breite des Balkens Intensität im Auswahlsteuerelement Farbe fest.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Die erste ausgewählte Farbe festgelegt.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Legt die aktuelle Farbpalette.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Ändert die Sättigungskomponente der ausgewählten Farbe.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Legt den Typ der Farben-Auswahlsteuerelement angezeigt.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Vom Framework aufgerufen, bevor ein Cursor, der auf der ausgewählten Farbe angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Standardfarben aus einer Farbpalette Sechseckige ausgewählt sind, und benutzerdefinierte Farben werden von einem Balkendiagramm Intensität ausgewählten Farben mit Rot/Grün/Blau Notation oder Farbton/Satuaration/Intensität-Notation angegeben werden.  
  
 Die folgende Abbildung zeigt mehrere `CMFCColorPickerCtrl` Objekte.  
  
 ![CMFCColorPickerCtrl-Dialogfeld](../../mfc/reference/media/colorpicker.png "Farbwähler")  
  
 Die `CMFCColorPickerCtrl` unterstützt zwei Paare von Formatvorlagen. Die Stile HEX und HEX_GREYSCALE eignen sich für die Standardfarbe Auswahl. Die Auswahl und INTENSITÄT Formatvorlagen sind für benutzerdefinierte Farbauswahl geeignet.  
  
 Führen Sie die folgenden Schritte zum Einbinden der `CMFCColorPickerCtrl` Steuerelement in ein Dialogfeld:  
  
1.  Bei Verwendung der **ClassWizard**, legen Sie ein neuen Schaltflächen-Steuerelement in der Dialogfeldvorlage (da die `CMFCColorPickerCtrl` Klasse geerbt wird, von der `CButton` Klasse).  
  
2.  Fügen Sie eine Membervariable, die die neuen Schaltflächen-Steuerelement in die Dialogfeldklasse zugeordnet ist. Ändern Sie den Variablentyp aus `CButton` auf `CMFCColorPickerCtrl`.  
  
3.  Legen Sie die `WM_INITDIALOG` Meldungshandler für die Dialogfeldklasse. Legen Sie im Handler den, Palette sowie ausgewählte Anfangsfarbe für den `CMFCColorPickerCtrl` Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie so konfigurieren Sie eine `CMFCColorPickerCtrl` Objekt mit verschiedenen Methoden in der `CMFCColorPickerCtrl` Klasse. Das Beispiel veranschaulicht, wie den Typ des Steuerelements für die Zeitauswahl festgelegt, und wie die Farbe, Farbton, Helligkeit und Sättigung festgelegt. Das Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&4;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&5;](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorpickerctrl.h  
  
##  <a name="a-namecmfccolorpickerctrla--cmfccolorpickerctrlcmfccolorpickerctrl"></a><a name="cmfccolorpickerctrl"></a>CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Erstellt ein `CMFCColorPickerCtrl`-Objekt.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namedrawcursora--cmfccolorpickerctrldrawcursor"></a><a name="drawcursor"></a>CMFCColorPickerCtrl::DrawCursor  
 Vom Framework aufgerufen, bevor ein Cursor, der auf der ausgewählten Farbe angezeigt wird.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Gibt ein Rechteck um die ausgewählte Farbe an.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie die Form des Cursors zu ändern, die auf die ausgewählte Farbe zeigt müssen.  
  
##  <a name="a-namegetcolora--cmfccolorpickerctrlgetcolor"></a><a name="getcolor"></a>CMFCColorPickerCtrl::GetColor  
 Ruft die Farbe, die der Benutzer auswählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der RGB-Wert der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegethlsa--cmfccolorpickerctrlgethls"></a><a name="gethls"></a>CMFCColorPickerCtrl::GetHLS  
 Ruft die Werte für Farbton, Helligkeit und die Sättigung der Farbe, die der Benutzer auswählt.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `hue`  
 Ein Zeiger auf eine Variable vom Typ double, der Farbton Informationen empfängt.  
  
 [out] `luminance`  
 Ein Zeiger auf eine Variable vom Typ double, der Intensität Informationen empfängt.  
  
 [out] `saturation`  
 Ein Zeiger auf eine Variable vom Typ double, der Informationen zu einer Überlastung des empfängt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegethuea--cmfccolorpickerctrlgethue"></a><a name="gethue"></a>CMFCColorPickerCtrl::GetHue  
 Ruft den Farbtonkomponente der Farbe, die der Benutzer auswählt.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Farbtonkomponente der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetluminancea--cmfccolorpickerctrlgetluminance"></a><a name="getluminance"></a>CMFCColorPickerCtrl::GetLuminance  
 Ruft die Komponente Intensität der Farbe, die der Benutzer auswählt.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Komponente der Intensität der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetsaturationa--cmfccolorpickerctrlgetsaturation"></a><a name="getsaturation"></a>CMFCColorPickerCtrl::GetSaturation  
 Ruft den Sättigungswert der Farbe, die der Benutzer auswählt.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Sättigungskomponente der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameselectcellhexagona--cmfccolorpickerctrlselectcellhexagon"></a><a name="selectcellhexagon"></a>CMFCColorPickerCtrl::SelectCellHexagon  
 Legt die aktuelle Farbe die Farbe, die durch den angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definiert.  
  
```  
void SelectCellHexagon(
    BYTE R,  
    BYTE G,  
    BYTE B);

 
BOOL SelectCellHexagon(
    int x,  
    int y);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `R`  
 Die Farbe Rot-Komponente.  
  
 [in] `G`  
 Die grün-Komponente.  
  
 [in] `B`  
 Die Blau-Komponente.  
  
 [in] `x`  
 Die X-Koordinate des Cursors, die auf eine Zelle Sechseck verweist.  
  
 [in] `y`  
 Die y-Koordinate des Cursors, die auf eine Zelle Sechseck verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite Überladung dieser Methode gibt immer zurück `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung dieser Methode wird die aktuelle Farbe die Farbe, die das Steuerelement zur Auswahl von Farbe entspricht, der roten, grünen und blauen Farbkomponenten angegeben.  
  
 Die zweite Überladung dieser Methode wird die aktuelle Farbe die Farbe von der Zelle Sechseck, auf den durch die Position des angegebenen Cursors.  
  
##  <a name="a-namesetcolora--cmfccolorpickerctrlsetcolor"></a><a name="setcolor"></a>CMFCColorPickerCtrl::SetColor  
 Legt die aktuelle Farbe auf den angegebenen RGB-Farbwert fest.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Color`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesethlsa--cmfccolorpickerctrlsethls"></a><a name="sethls"></a>CMFCColorPickerCtrl::SetHLS  
 Legt die aktuelle Farbe auf den angegebenen Wert der HLS-Farbe fest.  
  
```  
void SetHLS(
    double hue,  
    double luminance,  
    double saturation,  
    BOOL bInvalidate=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hue`  
 Ein Farbtonwert.  
  
 [in] `luminance`  
 Ein Intensitätswert.  
  
 [in] `saturation`  
 Ein Sättigungswert.  
  
 [in] `bInvalidate`  
 `TRUE`Das Fenster sofort die neue Farbe aktualisieren zu erzwingen; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesethuea--cmfccolorpickerctrlsethue"></a><a name="sethue"></a>CMFCColorPickerCtrl::SetHue  
 Ändert den Farbton der ausgewählten Farbe.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Hue`  
 Ein Farbtonwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetluminancea--cmfccolorpickerctrlsetluminance"></a><a name="setluminance"></a>CMFCColorPickerCtrl::SetLuminance  
 Ändert die Intensität der ausgewählten Farbe.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Luminance`  
 Ein Intensitätswert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetluminancebarwidtha--cmfccolorpickerctrlsetluminancebarwidth"></a><a name="setluminancebarwidth"></a>CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Legt die Breite des Balkens Intensität im Auswahlsteuerelement Farbe fest.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `w`  
 Die Breite des Balkens Intensität in Pixel gemessen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Ändern der Größe der Intensität-Leiste auf die **benutzerdefinierte** auf der Registerkarte Farben-Auswahlsteuerelement. Die `w` Parameter gibt die neue Breite des Balkens Intensität. Der Width-Wert wird ignoriert, wenn sie drei Viertel der die Breite des Clientbereichs überschreitet.  
  
##  <a name="a-namesetoriginalcolora--cmfccolorpickerctrlsetoriginalcolor"></a><a name="setoriginalcolor"></a>CMFCColorPickerCtrl::SetOriginalColor  
 Die erste ausgewählte Farbe festgelegt.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ref`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Aufgerufen Sie diese Methode wird, wenn die Farben-Auswahlsteuerelement initialisiert wird.  
  
##  <a name="a-namesetpalettea--cmfccolorpickerctrlsetpalette"></a><a name="setpalette"></a>CMFCColorPickerCtrl::SetPalette  
 Legt die aktuelle Farbpalette.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPalette`  
 Ein Zeiger auf eine Farbpalette.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbpalette definiert das Array der Farben, das angezeigt werden in den Farben-Auswahlsteuerelement an.  
  
##  <a name="a-namesetsaturationa--cmfccolorpickerctrlsetsaturation"></a><a name="setsaturation"></a>CMFCColorPickerCtrl::SetSaturation  
 Ändert die Sättigung der ausgewählten Farbe.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Saturation`  
 Ein Sättigungswert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesettypea--cmfccolorpickerctrlsettype"></a><a name="settype"></a>CMFCColorPickerCtrl::SetType  
 Legt den Typ der Farben-Auswahlsteuerelement angezeigt.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorType`  
 Ein Color Picker-Steuerelementtyp.  
  
 Die Typen definieren, indem die `CMFCColorPickerCtrl::COLORTYPE` Enumeration. Mögliche Typen sind `LUMINANCE`, `PICKER`, `HEX` und `HEX_GREYSCALE`. Der Standardtyp ist `PICKER`.  
  
### <a name="remarks"></a>Hinweise  
 Um eine Farbe Picker-Steuerelement festzulegen, rufen Sie diese Methode auf, bevor das Windows-Steuerelement erstellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)

