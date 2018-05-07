---
title: CMFCToolBarFontComboBox Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::CMFCToolBarFontComboBox
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::GetFontDesc
- AFXTOOLBARFONTCOMBOBOX/CMFCToolBarFontComboBox::SetFont
dev_langs:
- C++
helpviewer_keywords:
- CMFCToolBarFontComboBox [MFC], CMFCToolBarFontComboBox
- CMFCToolBarFontComboBox [MFC], GetFontDesc
- CMFCToolBarFontComboBox [MFC], SetFont
ms.assetid: 25f8e08c-aadd-4cb5-9581-a99d49d444b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ea8f05c20c3a3276f51b4267b6763831dc23eacf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfctoolbarfontcombobox-class"></a>CMFCToolBarFontComboBox-Klasse
Eine Symbolleisten-Schaltfläche, die ein Kombinationsfeld-Steuerelement, die dem Benutzer ermöglicht enthält, wählen Sie eine Schriftart aus einer Liste von Systemschriftarten.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCToolBarFontComboBox : public CMFCToolBarComboBoxButton  
```  
  
## <a name="members"></a>Member  
  
### <a name="protected-constructors"></a>Geschützte Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::CMFCToolBarFontComboBox](#cmfctoolbarfontcombobox)|Erstellt ein `CMFCToolBarFontComboBox`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc)|Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.|  
|[CMFCToolBarFontComboBox::SetFont](#setfont)|Wählt einer Schriftart in das schriftartkombinationsfeld gemäß entweder den Namen der Schriftart oder welche Präfix und das Zeichen die Schriftart aus.|  
  
### <a name="data-members"></a>Datenmember  
 [CMFCToolBarFontComboBox::m_nFontHeight](#m_nfontheight)  
 Die Höhe der Zeichen in das schriftartkombinationsfeld.  
  
## <a name="remarks"></a>Hinweise  
 Um eine Schriftart kombinationsfeldschaltfläche eine Symbolleiste hinzugefügt haben, gehen Sie folgendermaßen vor:  
  
1.  Reservieren Sie eine Platzhalterressourcen-ID für die Schaltfläche in der übergeordneten Symbolleistenressource.  
  
2.  Konstruieren Sie ein `CMFCToolBarFontComboBox`-Objekt.  
  
3.  In der Message-Handler, der verarbeitet die `AFX_WM_RESETTOOLBAR` angezeigt wird, ersetzen Sie die Schaltfläche "ursprünglichen" mit der neuen kombinationsfeldschaltfläche mithilfe [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton).  
  
4.  Synchronisieren Sie die Schriftart, die im Kombinationsfeld mit der Schriftart im Dokument mit ausgewählt ist die [CMFCToolBarFontComboBox::SetFont](#setfont) Methode.  
  
 Verwenden Sie zum Synchronisieren der Schriftart für das Dokument mit der Schriftart im Kombinationsfeld markierten der [CMFCToolBarFontComboBox::GetFontDesc](#getfontdesc) Methode, um die Attribute der ausgewählten Schriftart abzurufen und diese Attribute verwenden, um das Erstellen einer [ CFont-Klasse](../../mfc/reference/cfont-class.md) Objekt.  
  
 Die Schriftart kombinationsfeldschaltfläche Ruft die Win32-Funktion [EnumFontFamiliesEx](http://msdn.microsoft.com/library/windows/desktop/dd162620) bestimmen die Bildschirm- und Schriftarten, die für das System verfügbar.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)  
  
 [CMFCToolBarFontComboBox](../../mfc/reference/cmfctoolbarfontcombobox-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxtoolbarfontcombobox.h  
  
##  <a name="cmfctoolbarfontcombobox"></a>  CMFCToolBarFontComboBox::CMFCToolBarFontComboBox  
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
 Der nullbasierte Index des ein Symbolleistenbild. Image befindet sich der [CMFCToolBarImages Klasse](../../mfc/reference/cmfctoolbarimages-class.md) Objekt, mit [CMFCToolBar Klasse](../../mfc/reference/cmfctoolbar-class.md) -Klasse verwaltet.  
  
 [in] `nFontType`  
 Die Typen von Schriftarten, die im Kombinationsfeld enthält. Dieser Parameter kann eine Kombination (boolesche OR) der folgenden Werte sein:  
  
 DEVICE_FONTTYPE  
  
 RASTER_FONTTYPE  
  
 TRUETYPE_FONTTYPE  
  
 [in] `nCharSet`  
 Wenn auf DEFAULT_CHARSET im Kombinationsfeld Schriftarten allen eindeutig benannt, in allen Zeichensätzen enthält. (Wenn es zwei Schriftarten mit demselben Namen sind, enthält im Kombinationsfeld eine von ihnen.) Wenn auf einen gültigen Zeichen festgelegten Wert, der im Kombinationsfeld nur die Schriftarten in den angegebenen Zeichensatz enthält. Finden Sie unter [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) für eine Liste der möglichen Zeichen fest.  
  
 [in] `dwStyle`  
 Das Format des Kombinationsfelds. (siehe [Kombinationsfeldstile](../../mfc/reference/styles-used-by-mfc.md#combo-box-styles))  
  
 [in] `iWidth`  
 Die Breite in Pixel des Edit-Steuerelements.  
  
 [in] `nPitchAndFamily`  
 Wenn auf DEFAULT_PITCH im Kombinationsfeld festgelegt Schriftarten unabhängig von der Tonhöhe enthält. Wenn auf FIXED_PITCH oder VARIABLE_PITCH festgelegt, der im Kombinationsfeld nur Schriftarten mit diesem Typ Tonhöhe enthält. Für die Schriftfamilie Filterung wird derzeit nicht unterstützt.  
  
 [out] `pLstFontsExternal`  
 Zeiger auf eine [CObList Klasse](../../mfc/reference/coblist-class.md) Objekt, das die verfügbaren Schriftarten speichert.  
  
### <a name="remarks"></a>Hinweise  
 In der Regel `CMFCToolBarFontComboBox` Speichern von Objekten die Liste der verfügbaren Schriftarten in einer einzigen, gemeinsam genutzten `CObList` Objekt. Wenn Sie die zweite Überladung des Konstruktors verwenden, und geben Sie einen gültigen Zeiger auf `pLstFontsExternal`, `CMFCToolBarFontComboBox` Objekt wird stattdessen Füllen der `CObList` , `pLstFontsExternal` verweist, mit den verfügbaren Schriftarten.  
  
### <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht das Erstellen einer `CMFCToolBarFontComboBox` Objekt. Dieser Codeausschnitt ist Teil des [WordPad-Beispiels](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_WordPad#7](../../mfc/reference/codesnippet/cpp/cmfctoolbarfontcombobox-class_1.cpp)]  
  
##  <a name="getfontdesc"></a>  CMFCToolBarFontComboBox::GetFontDesc  
 Gibt einen Zeiger auf die `CMFCFontInfo` Objekt für einen angegebenen Index im Kombinationsfeld.  
  
```  
const CMFCFontInfo* GetFontDesc(int iIndex=-1) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iIndex`  
 Gibt den nullbasierten Index des eine Kombinationsfeldelement an.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMFCFontInfo` Objekt. Wenn `iIndex` gibt keinen Index gültiges Element der Rückgabewert ist `NULL`.  
  
##  <a name="m_nfontheight"></a>  CMFCToolBarFontComboBox::m_nFontHeight  
 Gibt die Höhe in Pixel, der Zeichen in das schriftartkombinationsfeld, wenn das Kombinationsfeld Besitzer Stil zu zeichnen kann.  
  
```  
static int m_nFontHeight  
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn die `m_nFontHeight` Variable gleich 0 ist, die Höhe wird entsprechend die Standardschriftart des Kombinationsfelds automatisch berechnet. Die Höhe enthält sowohl die Versalhöhe der Zeichen über der Basislinie die Unterlänge unterhalb der Basislinie Zeichen.  
  
##  <a name="setfont"></a>  CMFCToolBarFontComboBox::SetFont  
 Wählt die Schriftart in der das schriftartkombinationsfeld entsprechend der Schriftartname und die Zeichen, die festgelegt werden in den Parametern angegeben.  
  
```  
BOOL SetFont(
    LPCTSTR lpszName,  
    BYTE nCharSet=DEFAULT_CHARSET,  
    BOOL bExact=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Gibt den Schriftartnamen oder Präfix.  
  
 [in] `nCharSet`  
 Gibt den Zeichensatz an.  
  
 [in] `bExact`  
 Gibt an, ob `lpszName` enthält den Namen der Schriftart oder das Präfix Schriftart.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Schriftart erfolgreich aktiviert wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn `bExact` ist `TRUE`, diese Methode wählt eine Schriftart, die genau mit dem Namen, die Sie angegeben haben übereinstimmt, als `lpszName`. Wenn `bExact` ist `FALSE`, diese Methode wählt eine Schriftart, die mit dem angegebenen als Text beginnt `lpszName` und den Zeichensatz, den Sie als angegeben verwendet `nCharSet`. Wenn `nCharSet` festgelegt ist, DEFAULT_CHARSET, der Zeichensatz werden ignoriert und nur `lpszName` wird verwendet, um eine Schriftart auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBar-Klasse](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton-Klasse](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton-Klasse](../../mfc/reference/cmfctoolbarcomboboxbutton-class.md)   
 [CMFCFontInfo-Klasse](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../../mfc/reference/cmfctoolbar-class.md#replacebutton)   
 [Exemplarische Vorgehensweise: Steuerelemente in eine Symbolleiste einfügen](../../mfc/walkthrough-putting-controls-on-toolbars.md)



