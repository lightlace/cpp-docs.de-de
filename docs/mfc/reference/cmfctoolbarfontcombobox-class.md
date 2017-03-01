---
title: Klasse CMFCToolBarFontComboBox | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox class
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
caps.latest.revision: 29
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
ms.openlocfilehash: 50b22e19cab4f434ec53383c8a170344e89cbab0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox-Klasse
Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement, die dem Benutzer ermöglicht enthält, eine Schriftart aus einer Liste von Systemschriftarten auswählen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Erstellt ein `CMFCToolBarFontComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Wählt einer Schriftart im Kombinationsfeld Schriftart entsprechend entweder den Namen der Schriftart festgelegten Präfix und Zeichen der Schriftart.|  
  
### <a name="data-members"></a>Datenmember  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 Die Höhe der Zeichen in der Schriftart-Kombinationsfeld.  
  
## <a name="remarks"></a>Hinweise  
 Um eine Schriftart Kombinationsfelds-Schaltfläche zu einer Symbolleiste hinzuzufügen, gehen Sie folgendermaßen vor:  
  
1.  Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
2.  Konstruieren Sie ein `CMFCToolBarFontComboBox`-Objekt.  
  
3.  In den Message-Handler, verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die ursprüngliche Schaltfläche mit der neuen kombinationsfeldschaltfläche durch [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
4.  Synchronisieren Sie die Schriftart, die im Kombinationsfeld mit der Schriftart im Dokument mit ausgewählt ist die [CMFCToolBarFontComboBox::SetFont](#setfont) Methode.  
  
 Verwenden Sie zum Synchronisieren des Dokuments Schriftart mit den im Kombinationsfeld markierten Text der [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) Methode, um die Attribute der ausgewählten Schriftart abzurufen und diese Attribute verwenden, um das Erstellen einer [CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.  
  
 Die Schriftart Kombinationsfelds-Schaltfläche wird die Win32-Funktion [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) bestimmen die Bildschirm- und Schriftarten, die für das System verfügbar.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
##  <a name="a-namecmfctoolbarfontcomboboxa--cmfctoolbarfontcomboboxcmfctoolbarfontcombobox"></a><a name="cmfctoolbarfontcombobox"></a>CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
 Erstellt eine [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md) Objekt.  
  
```  
public:  
CMFCToolBarFontComboBox(
    UINT uiID,  
    int iImage,  
    int nFontType = DEVICE_FONTTYPE | RASTER_FONTTYPE | TRUETYPE_FONTTYPE,  
    BYTE nCharSet = DEFAULT_CHARSET,  
    DWORD dwStyle = CBS_DROPDOWN,  
    int iWidth = 0,  
    BYTE nPitchAndFamily = DEFAULT_PITCH);

 
protected:  
CMFCToolBarFontComboBox(
    CObList* pLstFontsExternal,  
    int nFontType,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily);  
  
CMFCToolBarFontComboBox();
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiID`  
 Die Befehls-ID des Kombinationsfelds.  
  
 [in] `iImage`  
 Der nullbasierte Index des Bildes einer Symbolleisten. Das Bild befindet sich in der [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.  
  
 [in] `nFontType`  
 Die Typen von Schriftarten, die im Kombinationsfeld enthält. Dieser Parameter kann eine Kombination (booleschen OR) der folgenden Werte sein:  
  
 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [in] `nCharSet`  
 Wenn auf DEFAULT_CHARSET im Kombinationsfeld alle eindeutigen Namen von Schriftarten in allen Zeichensätzen enthält. (Wenn zwei Schriftarten mit demselben Namen vorhanden sind, enthält das Kombinationsfeld einen davon.) Wenn auf einen gültigen Zeichen festgelegten Wert, der im Kombinationsfeld nur Schriftarten in den angegebenen Zeichensatz enthält. Finden Sie unter ["LogFont"](http://msdn.microsoft.com/library/windows/desktop/dd145037) für eine Liste der möglichen Zeichen fest.  
  
 [in] `dwStyle`  
 Das Format des Kombinationsfelds. (siehe [Kombinationsfeldstile](../../mfc/reference/combo-box-styles.md))  
  
 [in] `iWidth`  
 Die Breite des Edit-Steuerelements in Pixel.  
  
 [in] `nPitchAndFamily`  
 Wenn auf DEFAULT_PITCH im Kombinationsfeld festgelegt Schriftarten unabhängig von der Tonhöhe enthält. Wenn FIXED_PITCH oder VARIABLE_PITCH festgelegt, das Kombinationsfeld nur Schriftarten mit Pitch enthält. Filtern nach Schriftfamilie wird derzeit nicht unterstützt.  
  
 [out] `pLstFontsExternal`  
 Zeiger auf eine [CObList-Klasse](../../mfc/reference/coblist-class.md) -Objekt, das die verfügbaren Schriftarten gespeichert.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel `CMFCToolBarFontComboBox` Objekte speichern die Liste der verfügbaren Schriftarten in einer einzigen, gemeinsam genutzten `CObList` Objekt. Wenn Sie die zweite Überladung des Konstruktors verwenden, und geben Sie einen gültigen Zeiger auf `pLstFontsExternal`, `CMFCToolBarFontComboBox` Objekt füllt stattdessen die `CObList` , `pLstFontsExternal` verweist, mit verfügbaren Schriftarten.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCToolBarFontComboBox` Objekt. Dieser Codeausschnitt ist Teil der [WordPad-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad&#7;](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="a-namegetfontdesca--cmfctoolbarfontcomboboxgetfontdesc"></a><a name="getfontdesc"></a>CMFCToolBarFontComboBox::GetFontDesc  
 Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Gibt den nullbasierten Index des eine Kombinationsfeldelement.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf ein `CMFCFontInfo` Objekt. Wenn `iIndex` gibt keinen gültiges Elementindex, der Rückgabewert ist `NULL`.  
  
##  <a name="a-namemnfontheighta--cmfctoolbarfontcomboboxmnfontheight"></a><a name="m_nfontheight"></a>CMFCToolBarFontComboBox::m_nFontHeight  
 Gibt die Höhe in Pixel der Zeichen im Kombinationsfeld Schriftart verfügt das Kombinationsfeld Besitzer Stil zu zeichnen.  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `m_nFontHeight` Variable gleich 0 ist, die Höhe wird entsprechend der Standardschriftart des Kombinationsfelds automatisch berechnet. Die Höhe schließt die Versalhöhe der Zeichen über der Basislinie und die Unterlänge der Zeichen unterhalb der Basislinie.  
  
##  <a name="a-namesetfonta--cmfctoolbarfontcomboboxsetfont"></a><a name="setfont"></a>CMFCToolBarFontComboBox::SetFont  
 Wählt die Schriftart im Kombinationsfeld Schriftart entsprechend der Schriftartname und die Zeichen, die festlegen, werden in den Parametern angegeben.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Gibt die Schriftart oder das Präfix.  
  
 [in] `nCharSet`  
 Gibt den Zeichensatz an.  
  
 [in] `bExact`  
 Gibt an, ob `lpszName` enthält den Namen der Schriftart oder die Schriftart-Präfix.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schriftart erfolgreich aktiviert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bExact` ist `TRUE`, diese Methode wählt eine Schriftart, die genau, den Sie angegeben haben übereinstimmt, als `lpszName`. Wenn `bExact` ist `FALSE`, diese Methode wählt eine Schriftart, die mit dem Text, der als beginnt `lpszName` und den Zeichensatz, den Sie als angegeben verwendet `nCharSet`. Wenn `nCharSet` festgelegt ist, DEFAULT_CHARSET, der Zeichensatz werden ignoriert und nur `lpszName` wird verwendet, um eine Schriftart auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Einfügen von Steuerelementen in Symbolleisten](../../mfc/walkthrough-putting-controls-on-toolbars.md)




