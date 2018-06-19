---
title: CMFCColorPickerCtrl-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::CMFCColorPickerCtrl
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::GetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SelectCellHexagon
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHLS
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetHue
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminance
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetLuminanceBarWidth
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetOriginalColor
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetPalette
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetSaturation
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::SetType
- AFXCOLORPICKERCTRL/CMFCColorPickerCtrl::DrawCursor
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorPickerCtrl [MFC], CMFCColorPickerCtrl
- CMFCColorPickerCtrl [MFC], GetColor
- CMFCColorPickerCtrl [MFC], GetHLS
- CMFCColorPickerCtrl [MFC], GetHue
- CMFCColorPickerCtrl [MFC], GetLuminance
- CMFCColorPickerCtrl [MFC], GetSaturation
- CMFCColorPickerCtrl [MFC], SelectCellHexagon
- CMFCColorPickerCtrl [MFC], SetColor
- CMFCColorPickerCtrl [MFC], SetHLS
- CMFCColorPickerCtrl [MFC], SetHue
- CMFCColorPickerCtrl [MFC], SetLuminance
- CMFCColorPickerCtrl [MFC], SetLuminanceBarWidth
- CMFCColorPickerCtrl [MFC], SetOriginalColor
- CMFCColorPickerCtrl [MFC], SetPalette
- CMFCColorPickerCtrl [MFC], SetSaturation
- CMFCColorPickerCtrl [MFC], SetType
- CMFCColorPickerCtrl [MFC], DrawCursor
ms.assetid: b9bbd03c-beb0-4b55-9765-9985fd05e5dc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ad7e67cc32621fc30108767493c3a7bffd481b68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374814"
---
# <a name="cmfccolorpickerctrl-class"></a>CMFCColorPickerCtrl-Klasse
Die `CMFCColorPickerCtrl` -Klasse bietet eine Funktionalität für ein Steuerelement, das verwendet wird, um Farben auszuwählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorPickerCtrl : public CButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::CMFCColorPickerCtrl](#cmfccolorpickerctrl)|Erstellt ein `CMFCColorPickerCtrl`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::GetColor](#getcolor)|Ruft die Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHLS](#gethls)|Ruft die Werte für Farbton, Intensität und Sättigung der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetHue](#gethue)|Ruft den Farbtonkomponente der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetLuminance](#getluminance)|Ruft die Komponente Intensität der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::GetSaturation](#getsaturation)|Ruft die Komponente zu einer Überlastung der Farbe, die der Benutzer auswählt.|  
|[CMFCColorPickerCtrl::SelectCellHexagon](#selectcellhexagon)|Legt die aktuelle Farbe auf die durch den angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definierte Farbe fest.|  
|[CMFCColorPickerCtrl::SetColor](#setcolor)|Legt die aktuelle Farbe auf den angegebenen Wert der RGB-Farbe.|  
|[CMFCColorPickerCtrl::SetHLS](#sethls)|Legt die aktuelle Farbe auf den angegebenen HLS-Farbwert fest.|  
|[CMFCColorPickerCtrl::SetHue](#sethue)|Ändert den Farbtonkomponente von der zurzeit ausgewählte Farbe an.|  
|[CMFCColorPickerCtrl::SetLuminance](#setluminance)|Ändert die Intensität-Komponente von der zurzeit ausgewählte Farbe an.|  
|[CMFCColorPickerCtrl::SetLuminanceBarWidth](#setluminancebarwidth)|Legt die Breite des Balkens Intensität in den Farben-Auswahlsteuerelement fest.|  
|[CMFCColorPickerCtrl::SetOriginalColor](#setoriginalcolor)|Legt die erste ausgewählte Farbe an.|  
|[CMFCColorPickerCtrl::SetPalette](#setpalette)|Legt die aktuelle Farbpalette.|  
|[CMFCColorPickerCtrl::SetSaturation](#setsaturation)|Ändert die Komponente zu einer Überlastung der aktuell ausgewählte Farbe an.|  
|[CMFCColorPickerCtrl::SetType](#settype)|Legt den Typ des anzuzeigenden Farben-Auswahlsteuerelement an.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorPickerCtrl::DrawCursor](#drawcursor)|Vom Framework aufgerufen, bevor ein Cursor, der der ausgewählten Farbe angezeigt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Standardfarben aus einer Farbpalette Sechseckige ausgewählt sind, und benutzerdefinierte Farben werden von einem Balkendiagramm Intensität ausgewählt Farben mit Rot/Grün/Blau Notation oder Farbton/Satuaration/Intensität-Notation angegeben werden.  
  
 Die folgende Abbildung zeigt verschiedene `CMFCColorPickerCtrl` Objekte.  
  
 ![CMFCColorPickerCtrl-Dialogfeld](../../mfc/reference/media/colorpicker.png "Farbwähler")  
  
 Die `CMFCColorPickerCtrl` unterstützt zwei Paare von Formatvorlagen. Die Stile HEX und HEX_GREYSCALE eignen sich für standard Farbauswahl. Die Auswahl und INTENSITÄT Formate eignen sich für benutzerdefinierte Farbauswahl.  
  
 Führen Sie die folgenden Schritte zum Integrieren der `CMFCColorPickerCtrl` Steuerelement in einem Dialogfeld:  
  
1.  Bei Verwendung der **ClassWizard**, legen Sie ein neue Schaltflächen-Steuerelement in der Dialogfeldvorlage (da die `CMFCColorPickerCtrl` Klasse geerbt wird, von der `CButton` Klasse).  
  
2.  Fügen Sie eine Membervariable, die das neue Schaltflächen-Steuerelement in Ihre Dialogfeldklasse zugeordnet ist. Ändern Sie den Variablentyp aus `CButton` auf `CMFCColorPickerCtrl`.  
  
3.  Fügen Sie der `WM_INITDIALOG` Message-Handler für die Dialogfeldklasse. Im Handler festlegen, Typ, in der Palette und ausgewählten Ausgangsfarbe, der die `CMFCColorPickerCtrl` Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Konfigurieren einer `CMFCColorPickerCtrl` -Objekt mithilfe verschiedener Methoden in der `CMFCColorPickerCtrl` Klasse. Im Beispiel wird veranschaulicht, wie den Typ des Kontoauswahl-Steuerelement festgelegt, und zum Festlegen von seine Farbe, Farbton Intensität und Sättigung. Das Beispiel ist Teil der [neues Steuerelement-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#4](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#5](../../mfc/reference/codesnippet/cpp/cmfccolorpickerctrl-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCColorPickerCtrl](../../mfc/reference/cmfccolorpickerctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolorpickerctrl.h  
  
##  <a name="cmfccolorpickerctrl"></a>  CMFCColorPickerCtrl::CMFCColorPickerCtrl  
 Erstellt ein `CMFCColorPickerCtrl`-Objekt.  
  
```  
CMFCColorPickerCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="drawcursor"></a>  CMFCColorPickerCtrl::DrawCursor  
 Vom Framework aufgerufen, bevor ein Cursor, der der ausgewählten Farbe angezeigt wird.  
  
```  
virtual void DrawCursor(
    CDC* pDC,  
    const CRect& rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Gibt einen rechteckigen Bereich, um die ausgewählte Farbe an.  
  
### <a name="remarks"></a>Hinweise  
 Überschreiben Sie diese Methode, wenn Sie die Form des Cursors zu ändern, die auf die ausgewählte Farbe verweist müssen.  
  
##  <a name="getcolor"></a>  CMFCColorPickerCtrl::GetColor  
 Ruft die Farbe, die der Benutzer auswählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der RGB-Wert der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethls"></a>  CMFCColorPickerCtrl::GetHLS  
 Ruft die Werte für Farbton, Intensität und Sättigung der Farbe, die der Benutzer auswählt.  
  
```  
void GetHLS(
    double* hue,  
    double* luminance,  
    double* saturation);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `hue`  
 Ein Zeiger auf eine Variable vom Typ double, das Informationen Farbton empfängt.  
  
 [out] `luminance`  
 Ein Zeiger auf eine Variable vom Typ double, die Intensität-Informationen erhält.  
  
 [out] `saturation`  
 Ein Zeiger auf eine Variable vom Typ double, das Informationen zu einer Überlastung des empfängt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethue"></a>  CMFCColorPickerCtrl::GetHue  
 Ruft den Farbtonkomponente der Farbe, die der Benutzer auswählt.  
  
```  
double GetHue() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Farbtonkomponente der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getluminance"></a>  CMFCColorPickerCtrl::GetLuminance  
 Ruft die Komponente Intensität der Farbe, die der Benutzer auswählt.  
  
```  
double GetLuminance() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Komponente der Intensität der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="getsaturation"></a>  CMFCColorPickerCtrl::GetSaturation  
 Ruft ab, der Sättigungswert der ausgewählten Farbe, die der Benutzer auswählt.  
  
```  
double GetSaturation() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Komponente zu einer Überlastung der ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="selectcellhexagon"></a>  CMFCColorPickerCtrl::SelectCellHexagon  
 Legt die aktuelle Farbe auf die durch den angegebenen Komponenten der RGB-Farbe oder die angegebene Zelle Sechseck definierte Farbe fest.  
  
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
 Die Komponente grün.  
  
 [in] `B`  
 Die blaue Farbe-Komponente.  
  
 [in] `x`  
 Die X-Koordinate des Cursors an, die auf eine Zelle Sechseck verweist.  
  
 [in] `y`  
 Die y-Koordinate des Cursors an, die auf eine Zelle Sechseck verweist.  
  
### <a name="return-value"></a>Rückgabewert  
 Die zweite Überladung dieser Methode gibt immer zurück `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die erste Überladung dieser Methode legt die Farbe, die die Farben-Auswahlsteuerelement entspricht der aktuellen Farbe des roten, grünen und blauen Farbkomponenten angegeben.  
  
 Die zweite Überladung dieser Methode legt die aktuelle Farbe auf die Farbe von der Zelle Sechseck, auf das von der angegebenen Cursorposition fest.  
  
##  <a name="setcolor"></a>  CMFCColorPickerCtrl::SetColor  
 Legt die aktuelle Farbe auf den angegebenen Wert der RGB-Farbe.  
  
```  
void SetColor(COLORREF Color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Color`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sethls"></a>  CMFCColorPickerCtrl::SetHLS  
 Legt die aktuelle Farbe auf den angegebenen HLS-Farbwert fest.  
  
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
 Ein Wert zu einer Überlastung.  
  
 [in] `bInvalidate`  
 `TRUE` Erzwingen Sie das Fenster, um sofort auf die neu ausgewählte Farbe zu aktualisieren; andernfalls `FALSE`. Die Standardeinstellung ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="sethue"></a>  CMFCColorPickerCtrl::SetHue  
 Ändert den Farbton der zurzeit ausgewählte Farbe an.  
  
```  
void SetHue(double Hue);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Hue`  
 Ein Farbtonwert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setluminance"></a>  CMFCColorPickerCtrl::SetLuminance  
 Ändert die Intensität der zurzeit ausgewählte Farbe an.  
  
```  
void SetLuminance(double Luminance);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Luminance`  
 Ein Intensitätswert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setluminancebarwidth"></a>  CMFCColorPickerCtrl::SetLuminanceBarWidth  
 Legt die Breite des Balkens Intensität in den Farben-Auswahlsteuerelement fest.  
  
```  
void SetLuminanceBarWidth(int w);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `w`  
 Die Breite des Balkens Intensität gemessen in Pixel.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um die Größe von der Intensität-Leiste auf der **benutzerdefinierte** Farben-Auswahlsteuerelement auf der Registerkarte. Die `w` Parameter gibt die neue Breite des Balkens Intensität an. Der Wert der Zeilenbreite wird ignoriert, wenn sie drei Viertel der Breite des Clientbereichs überschreitet.  
  
##  <a name="setoriginalcolor"></a>  CMFCColorPickerCtrl::SetOriginalColor  
 Legt die erste ausgewählte Farbe an.  
  
```  
void SetOriginalColor(COLORREF ref);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `ref`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode, wenn die Farben-Auswahlsteuerelement initialisiert wird.  
  
##  <a name="setpalette"></a>  CMFCColorPickerCtrl::SetPalette  
 Legt die aktuelle Farbpalette.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPalette`  
 Ein Zeiger auf eine Farbpalette.  
  
### <a name="remarks"></a>Hinweise  
 Farben-Palette definiert das Array der Farben, das angezeigt werden in den Farben-Auswahlsteuerelement an.  
  
##  <a name="setsaturation"></a>  CMFCColorPickerCtrl::SetSaturation  
 Ändert die Sättigung der zurzeit ausgewählte Farbe an.  
  
```  
void SetSaturation(double Saturation);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `Saturation`  
 Ein Wert zu einer Überlastung.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="settype"></a>  CMFCColorPickerCtrl::SetType  
 Legt den Typ des anzuzeigenden Farben-Auswahlsteuerelement an.  
  
```  
void SetType(COLORTYPE colorType);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `colorType`  
 Eine Farbe Picker-Steuerelementtyp.  
  
 Die-Kerntypen werden durch die `CMFCColorPickerCtrl::COLORTYPE` Enumeration. Die möglichen Typen sind `LUMINANCE`, `PICKER`, `HEX` und `HEX_GREYSCALE`. Der Standardtyp ist `PICKER`.  
  
### <a name="remarks"></a>Hinweise  
 Um eine Farbe Zeitauswahl-Steuerelement-Typ anzugeben, rufen Sie diese Methode vor der Erstellung des Steuerelements in Windows.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorDialog-Klasse](../../mfc/reference/cmfccolordialog-class.md)
