---
title: Klasse CMFCRibbonColorButton | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::CMFCRibbonColorButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::AddColorsGroup
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableAutomaticButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::EnableOtherButton
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetAutomaticColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::GetHighlightedColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::RemoveAllColorGroups
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColor
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorBoxSize
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColorName
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetColumns
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetDocumentColors
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::SetPalette
- AFXRIBBONCOLORBUTTON/CMFCRibbonColorButton::UpdateColor
dev_langs:
- C++
helpviewer_keywords:
- CMFCRibbonColorButton class
ms.assetid: 6b4b4ee3-8cc0-41b4-a4eb-93e8847008e1
caps.latest.revision: 36
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
ms.openlocfilehash: 8cef76fd3518e1123cb9afd0c8cc2a39b2bff65c
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcribboncolorbutton-class"></a>CMFCRibbonColorButton-Klasse
Die `CMFCRibbonColorButton` -Klasse implementiert eine Farbenschaltfläche, die einer Menübandleiste hinzugefügt werden kann. Die Menüband-Farbenschaltfläche zeigt ein Dropdownmenü an, das eine oder mehrere Farbpaletten enthält.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCRibbonColorButton : public CMFCRibbonGallery  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonColorButton::CMFCRibbonColorButton](#cmfcribboncolorbutton)||  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCRibbonColorButton::AddColorsGroup](#addcolorsgroup)|Fügt dem normalen Farbbereich eine Gruppe Farben hinzu.|  
|[CMFCRibbonColorButton::EnableAutomaticButton](#enableautomaticbutton)|Gibt an, ob die Schaltfläche **Automatisch** aktiviert ist.|  
|[CMFCRibbonColorButton::EnableOtherButton](#enableotherbutton)|Aktiviert die Schaltfläche **Weitere** .|  
|[CMFCRibbonColorButton::GetAutomaticColor](#getautomaticcolor)||  
|[CMFCRibbonColorButton::GetColor](#getcolor)|Gibt die aktuell ausgewählte Farbe zurück.|  
|[CMFCRibbonColorButton::GetColorBoxSize](#getcolorboxsize)|Gibt die Größe der Farbelemente zurück, die in der Farbleiste angezeigt werden.|  
|[CMFCRibbonColorButton::GetColumns](#getcolumns)||  
|[CMFCRibbonColorButton::GetHighlightedColor](#gethighlightedcolor)|Gibt die Farbe des aktuell in der Popup-Farbpalette ausgewählten Elements zurück.|  
|[CMFCRibbonColorButton::RemoveAllColorGroups](#removeallcolorgroups)|Entfernt alle Farbgruppen aus dem normalen Farbbereich.|  
|[CMFCRibbonColorButton::SetColor](#setcolor)|Wählt eine Farbe aus dem normalen Farbbereich aus.|  
|[CMFCRibbonColorButton::SetColorBoxSize](#setcolorboxsize)|Legt die Größe aller Farbelemente fest, die in der Farbleiste angezeigt werden.|  
|[CMFCRibbonColorButton::SetColorName](#setcolorname)||  
|[CMFCRibbonColorButton::SetColumns](#setcolumns)||  
|[CMFCRibbonColorButton::SetDocumentColors](#setdocumentcolors)|Gibt eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments an.|  
|[CMFCRibbonColorButton::SetPalette](#setpalette)||  
|[CMFCRibbonColorButton::UpdateColor](#updatecolor)||  
  
## <a name="remarks"></a>Hinweise  
 Die Farbenschaltfläche im Menüband zeigt eine Farbleiste an, wenn ein Benutzer drauf drückt. Standardmäßig enthält diese Farbleiste eine Farbauswahlpalette, die als normaler Farbbereich bezeichnet wird. Optional kann die Farbleiste eine Schaltfläche **Automatisch** , die dem Benutzer die Auswahl einer Standardfarbe ermöglicht, und eine Schaltfläche **Weitere** anzeigen, die eine Popupfarbpalette anzeigt, die weitere Farben enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die Verwendung verschiedener Methoden in der `CMFCRibbonColorButton` -Klasse. Im Beispiel wird gezeigt, wie ein `CMFCRibbonColorButton` -Objekt konstruiert wird, das große Bild festgelegt wird, die Schaltfläche **Automatisch** aktiviert wird, die Schaltfläche **Weitere** aktiviert wird, die Spaltenanzahl festgelegt wird, die Größe aller Farbelemente festgelegt wird, die auf der Farbleiste angezeigt werden, dem normalen Farbbereich eine Gruppe Farben hinzugefügt wird, und eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments angegeben wird. Dieser Codeausschnitt ist Teil der [zeichnen Clientbeispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_DrawClient&3;](../../mfc/reference/codesnippet/cpp/cmfcribboncolorbutton-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonGallery](../../mfc/reference/cmfcribbongallery-class.md)  
  
 [CMFCRibbonColorButton](../../mfc/reference/cmfcribboncolorbutton-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxribboncolorbutton.h  
  
##  <a name="addcolorsgroup"></a>CMFCRibbonColorButton::AddColorsGroup  
 Fügt dem normalen Farbbereich eine Gruppe Farben hinzu.  
  
```  
void AddColorsGroup(
    LPCTSTR lpszName,  
    const CList<COLORREF,COLORREF>& lstColors,  
    BOOL bContiguousColumns=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Name der Gruppe.  
  
 [in] `lstColors`  
 Die Liste der Farben.  
  
 [in] `bContiguousColumns`  
 Steuert, wie die Farbe Elemente in der Gruppe angezeigt werden. Wenn `TRUE`, die Farbe Elemente ohne einen vertikalen Abstand gezeichnet werden. Wenn `FALSE`, die Farbe Elemente mit einer vertikalen Abstand gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Funktion, um die Farbe Popup wird werden mehrere Gruppen von Farben angezeigt. Sie können steuern, wie die Farben in Gruppe angezeigt werden.  
  
##  <a name="cmfcribboncolorbutton"></a>CMFCRibbonColorButton::CMFCRibbonColorButton  
 Erstellt ein `CMFCRibbonColorButton`-Objekt.  
  
```  
CMFCRibbonColorButton();

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    int nSmallImageIndex,  
    COLORREF color = RGB(0, 0, 0));

 
CMFCRibbonColorButton(
    UINT nID,  
    LPCTSTR lpszText,  
    BOOL bSimpleButtonLook,  
    int nSmallImageIndex,  
    int nLargeImageIndex,  
    COLORREF color = RGB(0, 0, 0));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nID`  
 Gibt die Befehls-ID des Befehls ausführen, wenn ein Benutzer auf die Schaltfläche klickt.  
  
 [in] `lpszText`  
 Gibt den Text auf der Schaltfläche angezeigt werden sollen.  
  
 [in] `nSmallImageIndex`  
 Der nullbasierte Index des kleinen Bilds auf der Schaltfläche angezeigt werden.  
  
 [in] `color`  
 Die Farbe der Schaltfläche (standardmäßig Schwarz).  
  
 [in] `bSimpleButtonLook`  
 Wenn `TRUE`, wird die Schaltfläche als einfaches Rechteck gezeichnet.  
  
 [in] `nLargeImageIndex`  
 Der nullbasierte Index des großen Bilds auf der Schaltfläche angezeigt werden.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="enableautomaticbutton"></a>CMFCRibbonColorButton::EnableAutomaticButton  
 Gibt an, ob die Schaltfläche **Automatisch** aktiviert ist.  
  
```  
void EnableAutomaticButton(
    LPCTSTR lpszLabel,  
    COLORREF colorAutomatic,  
    BOOL bEnable=TRUE,  
    LPCTSTR lpszToolTip=NULL,  
    BOOL bOnTop=TRUE,  
    BOOL bDrawBorder=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Die Bezeichnung für die **automatische** Schaltfläche.  
  
 [in] `colorAutomatic`  
 RGB-Wert, der angibt, die **automatische** Schaltfläche Standardfarbe.  
  
 [in] `bEnable`  
 `TRUE`Wenn die **automatische** Schaltfläche ist aktiviert. `FALSE` , wenn er deaktiviert ist.  
  
 [in] `lpszToolTip`  
 Die QuickInfo der **automatische** Schaltfläche.  
  
 [in] `bOnTop`  
 Gibt an, ob die **automatische** Schaltfläche befindet sich oben auf, bevor Sie Farbpalette.  
  
 [in] `bDrawBorder`  
 `TRUE`Wenn die Anwendung einen Rahmen um die Farbleiste auf die Schaltfläche für die Multifunktionsleiste Farbe zeichnet. Farbleiste zeigt die aktuell ausgewählte Farbe. `FALSE`Wenn die Anwendung keinen Rahmen zeichnet  
  
##  <a name="enableotherbutton"></a>CMFCRibbonColorButton::EnableOtherButton  
 Aktiviert die Schaltfläche **Weitere** .  
  
```  
void EnableOtherButton(
    LPCTSTR lpszLabel,  
    LPCTSTR lpszToolTip=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszLabel`  
 Die Beschriftung der Schaltfläche.  
  
 `lpszToolTip`  
 Der QuickInfo-Text für die **andere** Schaltfläche.  
  
### <a name="remarks"></a>Hinweise  
 Die **andere** Schaltfläche ist die Schaltfläche, die unterhalb der Gruppe von Farben angezeigt wird. Klickt der Benutzer die **andere** Schaltfläche ein Dialogfeld Farbe angezeigt.  
  
##  <a name="getautomaticcolor"></a>CMFCRibbonColorButton::GetAutomaticColor  
 Ruft die aktuelle automatische Schaltfläche Farbe ab.  
  
```  
COLORREF GetAutomaticColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein RGB-Farbwert, der die aktuelle automatische Schaltfläche Farbe darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Die automatische Schaltflächenfarbe festgelegt ist, durch die `colorAutomatic` übergebene Parameter die `CMFCRibbonColorButton::EnableAutomaticButton` Methode.  
  
##  <a name="getcolor"></a>CMFCRibbonColorButton::GetColor  
 Gibt die aktuell ausgewählte Farbe zurück.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Durch Klicken auf die Schaltfläche ausgewählte Farbe.  
  
##  <a name="getcolorboxsize"></a>CMFCRibbonColorButton::GetColorBoxSize  
 Gibt die Größe der Farbelemente zurück, die in der Farbleiste angezeigt werden.  
  
```  
CSize GetColorBoxSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Schaltflächen Farbe in der Dropdown-Farben-Palette.  
  
##  <a name="getcolumns"></a>CMFCRibbonColorButton::GetColumns  
 Ruft die Anzahl der Elemente in einer Zeile der Menüband-farbenschaltfläche-Katalog angezeigt.  
  
```  
int GetColumns() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Symbole in jeder Zeile zurück.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="gethighlightedcolor"></a>CMFCRibbonColorButton::GetHighlightedColor  
 Gibt die Farbe des derzeit ausgewählten Elements auf der Farbpalette die Farbe zurück.  
  
```  
COLORREF GetHighlightedColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Farbe des derzeit ausgewählten Elements auf der Farbpalette die Farbe.  
  
##  <a name="removeallcolorgroups"></a>CMFCRibbonColorButton::RemoveAllColorGroups  
 Entfernt alle Farbgruppen aus dem normalen Farbbereich.  
  
```  
void RemoveAllColorGroups();
```  
  
##  <a name="setcolor"></a>CMFCRibbonColorButton::SetColor  
 Wählt eine Farbe aus dem normalen Farbbereich aus.  
  
```  
void SetColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Eine Farbe festlegen.  
  
##  <a name="setcolorboxsize"></a>CMFCRibbonColorButton::SetColorBoxSize  
 Legt die Größe aller Farbelemente fest, die in der Farbleiste angezeigt werden.  
  
```  
void SetColorBoxSize(CSize sizeBox);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `sizeBox`  
 Die neue Größe der Schaltflächen Farbe in der Farbpalette.  
  
##  <a name="setcolorname"></a>CMFCRibbonColorButton::SetColorName  
 Legt einen neuen Namen für eine angegebene Farbe fest.  
  
```  
static void __stdcall SetColorName(
    COLORREF color,  
    const CString& strName);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Der RGB-Wert einer Farbe.  
  
 [in] `strName`  
 Der neue Name für die angegebene Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Da sie aufruft, `CMFCColorBar::SetColorName`, diese Methode ändert den Namen der angegebenen Farbe in allen `CMFCColorBar` Objekte in der Anwendung.  
  
##  <a name="setcolumns"></a>CMFCRibbonColorButton::SetColumns  
 Legt die Anzahl der Spalten in der Tabelle der Farben, die dem Benutzer bei Auswahl Farbe des Benutzers angezeigt wird.  
  
```  
void SetColumns(int nColumns);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nColumns`  
 Die Anzahl der Farbe Symbole in jeder Zeile angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="setdocumentcolors"></a>CMFCRibbonColorButton::SetDocumentColors  
 Gibt eine Liste mit RGB-Werten für die Anzeige im Farbbereich des Dokuments an.  
  
```  
void SetDocumentColors(
    LPCTSTR lpszLabel,  
    CList<COLORREF,COLORREF>& lstColors);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszLabel`  
 Der Text, mit die Farben angezeigt werden.  
  
 [in] `lstColors`  
 Ein Verweis auf eine Liste der RGB-Werte.  
  
##  <a name="setpalette"></a>CMFCRibbonColorButton::SetPalette  
 Gibt die standardmäßigen Farben in der Tabelle angezeigt, in dem die farbenschaltfläche angezeigt.  
  
```  
void SetPalette(CPalette* pPalette);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pPalette`  
 Ein Zeiger auf eine Farbpalette.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="updatecolor"></a>CMFCRibbonColorButton::UpdateColor  
 Wird vom Framework aufgerufen, wenn der Benutzer eine Farbe aus der Tabelle angezeigt wählt, wenn der Benutzer eine Farbe klickt.  
  
```  
void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein vom Benutzer ausgewählten Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCRibbonColorButton::UpdateColor` Methode ändert den aktuell ausgewählten die Farbe der Schaltfläche und benachrichtigt das übergeordnete Element durch Senden einer `WM_COMMAND` message mit einer `BN_CLICKED` standardbenachrichtigung. Verwenden der [CMFCRibbonColorButton::GetColor](#getcolor) Methode, um die ausgewählte Farbe abzurufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCRibbonGallery-Klasse](../../mfc/reference/cmfcribbongallery-class.md)

