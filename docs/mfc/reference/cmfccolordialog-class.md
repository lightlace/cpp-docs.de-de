---
title: Klasse CMFCColorDialog | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCColorDialog
dev_langs:
- C++
helpviewer_keywords:
- CMFCColorDialog::m_CurrentColor data member
- CMFCColorDialog::m_pPropSheet data member
- CMFCColorDialog::m_btnColorSelect data member
- CMFCColorDialog class
- CMFCColorDialog::m_wndColors data member
- CMFCColorDialog::m_bIsMyPalette data member
- CMFCColorDialog::m_pColourSheetTwo data member
- CMFCColorDialog::m_NewColor data member
- CMFCColorDialog::m_pPalette data member
- CMFCColorDialog::m_wndStaticPlaceHolder data member
- CMFCColorDialog::m_pColourSheetOne data member
- CMFCColorDialog::m_hcurPicker data member
- CMFCColorDialog::PreTranslateMessage method
- CMFCColorDialog::m_bPickerMode data member
ms.assetid: 235bbbbc-a3b1-46e0-801b-fb55093ec579
caps.latest.revision: 30
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
ms.openlocfilehash: ac621157e0fcb5bcabef2ae8f367a1b141b4ace0
ms.lasthandoff: 02/24/2017

---
# <a name="cmfccolordialog-class"></a>CMFCColorDialog-Klasse
Die `CMFCColorDialog` -Klasse stellt ein Dialogfeld zur Farbauswahl dar.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCColorDialog : public CDialogEx  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorDialog::CMFCColorDialog](#cmfccolordialog)|Erstellt ein `CMFCColorDialog`-Objekt.|  
|`CMFCColorDialog::~CMFCColorDialog`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCColorDialog::GetColor](#getcolor)|Gibt den aktuelle ausgewählten Farbe zurück.|  
|[CMFCColorDialog::GetPalette](#getpalette)|Gibt die Farben-Palette.|  
|`CMFCColorDialog::PreTranslateMessage`|Windows-Nachrichten übersetzt, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. Syntax und Weitere Informationen finden Sie unter [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage). (Überschreibt `CDialogEx::PreTranslateMessage`.)|  
|[CMFCColorDialog::RebuildPalette](#rebuildpalette)|Leitet eine Palette der Systempalette.|  
|[CMFCColorDialog::SetCurrentColor](#setcurrentcolor)|Legt die aktuelle ausgewählte Farbe fest.|  
|[CMFCColorDialog::SetNewColor](#setnewcolor)|Legt die Farbe fest, das am häufigsten gleich einem angegebenen RGB-Wert.|  
|[CMFCColorDialog::SetPageOne](#setpageone)|Wählt einen RGB-Wert für die erste Eigenschaftenseite.|  
|[CMFCColorDialog::SetPageTwo](#setpagetwo)|Wählt einen RGB-Wert für die zweite Eigenschaftenseite.|  
  
### <a name="protected-data-members"></a>Geschützte Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`m_bIsMyPalette`|`TRUE`Wenn die Farbauswahl-Dialogfeld eine eigene Farbpalette verwendet oder `FALSE` Wenn das Dialogfeld eine Palette verwendet, die in angegeben ist die `CMFCColorDialog` Konstruktor.|  
|`m_bPickerMode`|`TRUE`während der Benutzer eine Farbe aus dem Auswahldialogfeld auswählen; andernfalls `FALSE`.|  
|`m_btnColorSelect`|Schaltfläche für die Farbe, die der Benutzer ausgewählt hat.|  
|`m_CurrentColor`|Die ausgewählte Farbe.|  
|`m_hcurPicker`|Der Cursor, der verwendet wird, um eine Farbe auszuwählen.|  
|`m_NewColor`|Die potenzielle ausgewählte Farbe, die dauerhaft ausgewählt oder auf die ursprüngliche Farbe zurückgesetzt werden kann.|  
|`m_pColourSheetOne`|Ein Zeiger auf der ersten Seite des Farbe Auswahl Eigenschaftenblatt.|  
|`m_pColourSheetTwo`|Ein Zeiger auf der zweiten Seite des Farbe Auswahl Eigenschaftenblatt.|  
|`m_pPalette`|Die aktuelle logische Palette.|  
|`m_pPropSheet`|Ein Zeiger auf die Eigenschaftenseite für die Farbauswahl-Dialogfeld.|  
|`m_wndColors`|Eine Farbe Datumsauswahl Control-Objekt.|  
|`m_wndStaticPlaceHolder`|Ein statisches Steuerelement, das ist ein Platzhalter für die Auswahl einer Farbe Eigenschaftenfenster.|  
  
## <a name="remarks"></a>Hinweise  
 Das Dialogfeld Farbe Auswahl wird als eine Eigenschaftenseite mit zwei Seiten angezeigt. Auf der ersten Seite Wählen Sie eine Standardfarbe der Systempalette; auf der zweiten Seite Wählen Sie eine benutzerdefinierte Farbe.  
  
 Konstruieren einer `CMFCColorDialog` -Objekt auf dem Stapel, und rufen Sie dann `DoModal`, übergeben die ursprüngliche Farbe als Parameter an die `CMFCColorDialog` Konstruktor. Das Dialogfeld Farbe Auswahl erstellt dann mehrere [CMFCColorPickerCtrl Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md) Objekte behandelt jede Farbpalette.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CDialogEx](../../mfc/reference/cdialogex-class.md)  
  
 [CMFCColorDialog](../../mfc/reference/cmfccolordialog-class.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Dialogfeld Farbe zu konfigurieren, indem Sie verschiedene Methoden in der `CMFCColorDialog` Klasse. Das Beispiel zeigt, wie die aktuelle und die neuen Farben im Dialogfeld festgelegt, und wie die Komponenten roten, grünen und blauen eine ausgewählte Farbe auf den zwei Eigenschaftenseiten im Dialogfeld Farbe festgelegt. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&3;](../../mfc/reference/codesnippet/cpp/cmfccolordialog-class_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcolordialog.h  
  
##  <a name="a-namecmfccolordialoga--cmfccolordialogcmfccolordialog"></a><a name="cmfccolordialog"></a>CMFCColorDialog::CMFCColorDialog  
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
 Ein Zeiger auf das Dialogfeld übergeordnete Fenster oder das Besitzer.  
  
 [in] `hPal`  
 Ein Handle für eine Farbpalette.  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcolora--cmfccolordialoggetcolor"></a><a name="getcolor"></a>CMFCColorDialog::GetColor  
 Ruft die Farbe, die der Benutzer das Dialogfeld "Farbe" ausgewählt.  
  
```  
COLORREF GetColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) Wert, der die RGB-Informationen für die im Dialogfeld "Farbe" ausgewählte Farbe enthält.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion aufrufen, nachdem Sie die `DoModal` Methode.  
  
##  <a name="a-namegetpalettea--cmfccolordialoggetpalette"></a><a name="getpalette"></a>CMFCColorDialog::GetPalette  
 Ruft die Farbpalette, die aktuelle Farbe im Dialogfeld verfügbar ist.  
  
```  
CPalette* GetPalette() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CPalette` -Objekt, das in angegeben wurde die `CMFCColorDialog` Konstruktor.  
  
### <a name="remarks"></a>Hinweise  
 Die Farbpalette gibt die Farben, die der Benutzer auswählen kann.  
  
##  <a name="a-namerebuildpalettea--cmfccolordialogrebuildpalette"></a><a name="rebuildpalette"></a>CMFCColorDialog::RebuildPalette  
 Leitet eine Palette der Systempalette.  
  
```  
void RebuildPalette();
```  
  
##  <a name="a-namesetcurrentcolora--cmfccolordialogsetcurrentcolor"></a><a name="setcurrentcolor"></a>CMFCColorDialog::SetCurrentColor  
 Legt die aktuelle Farbe des Dialogfelds fest.  
  
```  
void SetCurrentColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rgb`  
 Ein RGB-Farbwert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetnewcolora--cmfccolordialogsetnewcolor"></a><a name="setnewcolor"></a>CMFCColorDialog::SetNewColor  
 Legt die aktuelle Farbe die Farbe in der aktuellen Palette, die am ähnlichsten ist.  
  
```  
void SetNewColor(COLORREF rgb);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `rgb`  
 Ein [COLORREF](http://msdn.microsoft.com/library/windows/desktop/dd183449) , eine RGB-Farbe angibt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpageonea--cmfccolordialogsetpageone"></a><a name="setpageone"></a>CMFCColorDialog::SetPageOne  
 Explizit gibt die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf der ersten Seite des ein Dialogfeld Farbe.  
  
```  
void SetPageOne(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `R`  
 Gibt die roten Komponente den RGB-Wert.  
  
 [in] `G`  
 Gibt die grünen Komponente den RGB-Wert.  
  
 [in] `B`  
 Gibt die blaue Komponente den RGB-Wert.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetpagetwoa--cmfccolordialogsetpagetwo"></a><a name="setpagetwo"></a>CMFCColorDialog::SetPageTwo  
 Explizit gibt die roten, grünen und blauen Komponenten einer ausgewählten Farbe auf der zweiten Seite des ein Dialogfeld Farbe.  
  
```  
void SetPageTwo(
    BYTE R,  
    BYTE G,  
    BYTE B);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `R`  
 Gibt eine roten Komponente den RGB-Wert  
  
 [in] `G`  
 Gibt eine grüne Komponente der RGB-Wert  
  
 [in] `B`  
 Gibt eine blaue Komponente der RGB-Wert  
  
### <a name="remarks"></a>Hinweise  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCColorPickerCtrl-Klasse](../../mfc/reference/cmfccolorpickerctrl-class.md)

