---
title: Klasse CMFCPropertyGridCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCPropertyGridCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCPropertyGridCtrl::get_accValue method
- CMFCPropertyGridCtrl::accHitTest method
- CMFCPropertyGridCtrl::get_accState method
- CMFCPropertyGridCtrl::accLocation method
- CMFCPropertyGridCtrl::get_accChild method
- CMFCPropertyGridCtrl::get_accName method
- CMFCPropertyGridCtrl::PreTranslateMessage method
- CMFCPropertyGridCtrl::get_accRole method
- CMFCPropertyGridCtrl::get_accDefaultAction method
- CMFCPropertyGridCtrl class
- CMFCPropertyGridCtrl::get_accDescription method
ms.assetid: 95877cae-2311-4a2a-9031-0c8c3cf0a5f9
caps.latest.revision: 35
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
ms.openlocfilehash: 93611d1b52d6372a81b91f08c5a5c7b215b584e3
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcpropertygridctrl-class"></a>CMFCPropertyGridCtrl-Klasse
[!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
 Unterstützt ein bearbeitbares Eigenschaftenraster-Steuerelement, das Eigenschaften in alphabetischer oder hierarchischer Reihenfolge anzeigen kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCPropertyGridCtrl : public CWnd  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](#cmfcpropertygridctrl)|Erstellt ein `CMFCPropertyGridCtrl`-Objekt.|  
|`CMFCPropertyGridCtrl::~CMFCPropertyGridCtrl`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|`CMFCPropertyGridCtrl::accHitTest`|Wird durch das Framework aufgerufen, um das untergeordnete Element oder untergeordnete Objekt an einem bestimmten Punkt auf dem Bildschirm abzurufen. (Überschreibt [CWnd::accHitTest](../../mfc/reference/cwnd-class.md#acchittest).)|  
|`CMFCPropertyGridCtrl::accLocation`|Wird durch das Framework aufgerufen, um die aktuelle Bildschirmposition des angegebenen Objekts abzurufen. (Überschreibt [CWnd::accLocation](../../mfc/reference/cwnd-class.md#acclocation).)|  
|[CMFCPropertyGridCtrl::accSelect](#accselect)|Wird durch das Framework aufgerufen, um die Auswahl zu ändern oder den Tastaturfokus des angegebenen Objekts zu verschieben. (Überschreibt [CWnd::accSelect](../../mfc/reference/cwnd-class.md#accselect).)|  
|[CMFCPropertyGridCtrl::AddProperty](#addproperty)|Ein Eigenschaftenraster-Steuerelement hinzugefügt eine neue Eigenschaft.|  
|[CMFCPropertyGridCtrl::AlwaysShowUserToolTip](#alwaysshowusertooltip)||  
|[CMFCPropertyGridCtrl::CloseColorPopup](#closecolorpopup)|Schließt das Dialogfeld Farbe Auswahl.|  
|[CMFCPropertyGridCtrl::Create](#create)|Erstellt ein Eigenschaftenraster-Steuerelement aus, und fügt ihn der Eigenschaft Grid Control-Objekt.|  
|[CMFCPropertyGridCtrl::DeleteProperty](#deleteproperty)|Löscht die angegebene Eigenschaft aus dem Eigenschaftenraster-Steuerelement.|  
|[CMFCPropertyGridCtrl::DrawControlBarColors](#drawcontrolbarcolors)||  
|[CMFCPropertyGridCtrl::EnableDescriptionArea](#enabledescriptionarea)|Aktiviert oder deaktiviert den Beschreibungsbereich, der unterhalb der Liste der Eigenschaften angezeigt wird.|  
|[CMFCPropertyGridCtrl::EnableHeaderCtrl](#enableheaderctrl)|Aktiviert oder deaktiviert das Kopfzeilen-Steuerelement am oberen Rand der Eigenschaftenraster-Steuerelement.|  
|[CMFCPropertyGridCtrl::EnsureVisible](#ensurevisible)|Verschiebt ein Eigenschaftenraster-Steuerelement und erweitert die Items-Eigenschaft, bis die angegebene Eigenschaft angezeigt wird.|  
|[CMFCPropertyGridCtrl::ExpandAll](#expandall)|Erweitert oder reduziert alle Eigenschaft Grid-Steuerelement-Knoten.|  
|[CMFCPropertyGridCtrl::FindItemByData](#finditembydata)|Ruft die Eigenschaft, die eine benutzerdefinierte zugeordnet ist `DWORD` Wert.|  
|`CMFCPropertyGridCtrl::get_accChild`|Wird durch das Framework aufgerufen, um die Adresse einer `IDispatch`-Schnittstelle für das angegebene, untergeordnete Element abzurufen. (Überschreibt [CWnd::get_accChild](../../mfc/reference/cwnd-class.md#get_accchild).)|  
|[CMFCPropertyGridCtrl::get_accChildCount](#get_accchildcount)|Wird durch das Framework aufgerufen, um die Zahl der untergeordneten Elemente abzurufen, die zu diesem Objekt gehören. (Überschreibt [CWnd::get_accChildCount](../../mfc/reference/cwnd-class.md#get_accchildcount).)|  
|`CMFCPropertyGridCtrl::get_accDefaultAction`|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die Standardaktion des Objekts beschreibt. (Überschreibt [CWnd::get_accDefaultAction](../../mfc/reference/cwnd-class.md#get_accdefaultaction).)|  
|`CMFCPropertyGridCtrl::get_accDescription`|Wird durch das Framework aufgerufen, um eine Zeichenfolge abzurufen, die die visuelle Darstellung des angegebenen Objekts beschreibt. (Überschreibt [CWnd::get_accDescription](../../mfc/reference/cwnd-class.md#get_accdescription).)|  
|[CMFCPropertyGridCtrl::get_accFocus](#get_accfocus)|Wird durch das Framework aufgerufen, um das Objekt abzurufen, das den Tastaturfokus hat. (Überschreibt [CWnd::get_accFocus](../../mfc/reference/cwnd-class.md#get_accfocus).)|  
|[CMFCPropertyGridCtrl::get_accHelp](#get_acchelp)|Zum Abrufen eines Objekts aufgerufen `Help` Eigenschaftenzeichenfolge. (Überschreibt [CWnd::get_accHelp](../../mfc/reference/cwnd-class.md#get_acchelp).)|  
|[CMFCPropertyGridCtrl::get_accHelpTopic](#get_acchelptopic)|Den vollständigen Pfad der abzurufenden aufgerufen der `WinHelp`Datei, die das angegebene Objekt und den Bezeichner der im entsprechenden Thema in der Datei zugeordnet. (Überschreibt [CWnd::get_accHelpTopic](../../mfc/reference/cwnd-class.md#get_acchelptopic).)|  
|[CMFCPropertyGridCtrl::get_accKeyboardShortcut](#get_acckeyboardshortcut)|Wird durch das Framework aufgerufen, um die Tastenkombination oder Zugriffstaste des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accKeyboardShortcut](../../mfc/reference/cwnd-class.md#get_acckeyboardshortcut).)|  
|`CMFCPropertyGridCtrl::get_accName`|Wird durch das Framework aufgerufen, um den Namen des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accName](../../mfc/reference/cwnd-class.md#get_accname).)|  
|`CMFCPropertyGridCtrl::get_accRole`|Wird durch das Framework aufgerufen, um Informationen abzurufen, die die Rolle des angegebenen Objekts beschreiben. (Überschreibt [CWnd::get_accRole](../../mfc/reference/cwnd-class.md#get_accrole).)|  
|[CMFCPropertyGridCtrl::get_accSelection](#get_accselection)|Wird durch das Framework aufgerufen, um die ausgewählten, untergeordneten Elemente dieses Objekts abzurufen. (Überschreibt [CWnd::get_accSelection](../../mfc/reference/cwnd-class.md#get_accselection).)|  
|`CMFCPropertyGridCtrl::get_accState`|Wird durch das Framework aufgerufen, um den aktuellen Status des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accState](../../mfc/reference/cwnd-class.md#get_accstate).)|  
|`CMFCPropertyGridCtrl::get_accValue`|Wird durch das Framework aufgerufen, um den Wert des angegebenen Objekts abzurufen. (Überschreibt [CWnd::get_accValue](../../mfc/reference/cwnd-class.md#get_accvalue).)|  
|[CMFCPropertyGridCtrl::GetBkColor](#getbkcolor)|Ruft die Hintergrundfarbe für die aktuelle Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetBoldFont](#getboldfont)|Ruft die Windows-Schriftart, die der Text im aktuellen Eigenschaftenraster in Fettdruck steuern.|  
|[CMFCPropertyGridCtrl::GetCurSel](#getcursel)|Ruft die derzeit ausgewählte Eigenschaft ab.|  
|[CMFCPropertyGridCtrl::GetCustomColors](#getcustomcolors)|Ruft die benutzerdefinierten Farben, die derzeit für die Eigenschaft Grid-Steuerelement Elemente definiert werden.|  
|[CMFCPropertyGridCtrl::GetDescriptionHeight](#getdescriptionheight)|Ruft die Höhe des Bereichs Beschreibung am unteren Rand der Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetDescriptionRows](#getdescriptionrows)|Ruft die Anzahl der Zeilen im Beschreibungsbereich der aktuellen Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetHeaderCtrl](#getheaderctrl)|Ruft die interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt, das Framework verwendet, um die aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.|  
|[CMFCPropertyGridCtrl::GetHeaderHeight](#getheaderheight)|Ruft die Höhe des Eigenschaft Grid Control-Headers ab.|  
|[CMFCPropertyGridCtrl::GetLeftColumnWidth](#getleftcolumnwidth)|Ruft die Breite der linken Spalte mit der aktuellen Eigenschaftenraster-Steuerelement, das den Namen jeder Eigenschaft enthält.|  
|[CMFCPropertyGridCtrl::GetListRect](#getlistrect)|Ruft das umschließende Rechteck für das Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetProperty](#getproperty)|Ruft einen Zeiger auf die Property-Objekt, das dem angegebenen Index, der eine Eigenschaft Grid-Steuerelement ein Element entspricht.|  
|[CMFCPropertyGridCtrl::GetPropertyColumnWidth](#getpropertycolumnwidth)|Ruft die aktuelle Breite der Spalte, die Eigenschaftswerte enthält.|  
|[CMFCPropertyGridCtrl::GetPropertyCount](#getpropertycount)|Ruft die Anzahl der Eigenschaften in einem Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetRowHeight](#getrowheight)|Ruft die Höhe einer Zeile in der Eigenschaftenraster-Steuerelement ab.|  
|[CMFCPropertyGridCtrl::GetScrollBarCtrl](#getscrollbarctrl)|Ruft einen Zeiger auf das ScrollBar-Steuerelement in das Eigenschaftenraster-Steuerelement ab. (Überschreibt [CWnd:: Getscrollbarctrl](../../mfc/reference/cwnd-class.md#getscrollbarctrl).)|  
|[CMFCPropertyGridCtrl::GetTextColor](#gettextcolor)|Ruft die Farbe des Texts in der Items-Eigenschaft in der aktuellen Eigenschaftenraster-Steuerelement ab.|  
|`CMFCPropertyGridCtrl::GetThisClass`|Vom Framework verwendet werden, um einen Zeiger auf die [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) -Objekt, das Klassentyp zugeordnet ist.|  
|[CMFCPropertyGridCtrl::HitTest](#hittest)|Ruft einen Zeiger auf die Eigenschaftenobjekt, das eine Eigenschaft Grid-Steuerelement ein Element entspricht, ist von ein angegebenen Punkt im Element ab. Diese Methode gibt auch den Bereich in das Eigenschaftenraster-Steuerelement, das den Punkt enthält.|  
|[CMFCPropertyGridCtrl::InitHeader](#initheader)|Initialisiert die interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt, das Framework verwendet, um die aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.|  
|[CMFCPropertyGridCtrl::IsAlphabeticMode](#isalphabeticmode)|Gibt an, ob ein Eigenschaftenraster-Steuerelement im alphabetischen Modus befindet.|  
|[CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip](#isalwaysshowusertooltip)||  
|[CMFCPropertyGridCtrl::IsDescriptionArea](#isdescriptionarea)|Gibt an, ob der Beschreibungsbereich der Eigenschaftenraster-Steuerelement angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsGroupNameFullWidth](#isgroupnamefullwidth)|Gibt an, ob jeder Eigenschaftsname für die Gruppe über die Breite des der aktuellen Eigenschaftenraster-Steuerelement angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsHeaderCtrl](#isheaderctrl)|Gibt an, ob das Kopfzeilen-Steuerelement angezeigt wird.|  
|[CMFCPropertyGridCtrl::IsMarkModifiedProperties](#ismarkmodifiedproperties)|Gibt an, wie das Eigenschaftenraster-Steuerelement geänderte Eigenschaften angezeigt.|  
|[CMFCPropertyGridCtrl::IsShowDragContext](#isshowdragcontext)|Gibt an, ob das Framework die Spalten Name-Wert, der den aktuellen Eigenschaftenraster-Steuerelement, aktualisiert Wenn ein Benutzer ändert die Größe der Spalten.|  
|[CMFCPropertyGridCtrl::IsVSDotNetLook](#isvsdotnetlook)|Gibt an, ob die Darstellung des Eigenschaftenraster-Steuerelement ist im Stil von Visual Studio .NET verwendet wird.|  
|[CMFCPropertyGridCtrl::MarkModifiedProperties](#markmodifiedproperties)|Gibt an, wie geänderte Eigenschaften anzuzeigen.|  
|`CMFCPropertyGridCtrl::PreTranslateMessage`|Von der Klasse verwendet [CWinApp](../../mfc/reference/cwinapp-class.md) auf fenstermeldungen zu übersetzen, bevor sie an verteilt sind die [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) und [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) Windows-Funktionen. (Überschreibt [CWnd:: PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).)|  
|[CMFCPropertyGridCtrl::RemoveAll](#removeall)|Entfernt alle Property-Objekte aus einem Eigenschaftenraster-Steuerelement.|  
|[CMFCPropertyGridCtrl::ResetOriginalValues](#resetoriginalvalues)|Stellt den ursprünglichen Wert aller Eigenschaften.|  
|[CMFCPropertyGridCtrl::SetAlphabeticMode](#setalphabeticmode)|Legt fest oder setzt alphabetischen Modus.|  
|[CMFCPropertyGridCtrl::SetBoolLabels](#setboollabels)|Gibt den Text der booleschen Bezeichnungen.|  
|[CMFCPropertyGridCtrl::SetCurSel](#setcursel)|Wählt eine Eigenschaft in einem Eigenschaftenraster-Steuerelement aus.|  
|[CMFCPropertyGridCtrl::SetCustomColors](#setcustomcolors)|Gibt benutzerdefinierte Farben für verschiedene Elemente der Eigenschaft Grid-Steuerelement an.|  
|[CMFCPropertyGridCtrl::SetDescriptionRows](#setdescriptionrows)|Gibt die Anzahl der Zeilen, die im Beschreibungsabschnitt "von der aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.|  
|[CMFCPropertyGridCtrl::SetGroupNameFullWidth](#setgroupnamefullwidth)|Gibt an, ob die gesamte Breite des der Kategoriename für eine Gruppe von Eigenschaften in der aktuellen Eigenschaftenraster-Steuerelement angezeigt werden soll.|  
|[CMFCPropertyGridCtrl::SetListDelimiter](#setlistdelimiter)|Definiert ein Zeichen, das als Trennzeichen in einer Liste von Eigenschaftswerten verwendet wird.|  
|[CMFCPropertyGridCtrl::SetShowDragContext](#setshowdragcontext)|Gibt an, ob das Framework die Spalten Name-Wert, der den aktuellen Eigenschaftenraster-Steuerelement, aktualisiert Wenn ein Benutzer ändert die Größe der Spalten.|  
|[CMFCPropertyGridCtrl::SetVSDotNetLook](#setvsdotnetlook)|Legt die Darstellung des Eigenschaftenraster-Steuerelement auf das Format, das in Visual Studio .NET verwendet wird.|  
|[CMFCPropertyGridCtrl::UpdateColor](#updatecolor)|Legt den Farbwert der Eigenschaft zurzeit ausgewählte Farbe fest.|  
  
### <a name="protected-methods"></a>Geschützte Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCPropertyGridCtrl::AdjustLayout](#adjustlayout)|Zeichnet das Eigenschaftenraster-Steuerelement und seine Eigenschaften.|  
|[CMFCPropertyGridCtrl::CompareProps](#compareprops)|Wird von der Eigenschaftenraster-Steuerelement zum Sortieren der Eigenschaften aufgerufen.|  
|[CMFCPropertyGridCtrl::EditItem](#edititem)|Wird vom Framework aufgerufen, wenn der Benutzer beginnt, eine Eigenschaft zu ändern.|  
|[CMFCPropertyGridCtrl::EndEditItem](#endedititem)|Wird vom Framework aufgerufen, wenn der Benutzer das Ändern einer Eigenschaft beendet.|  
|[CMFCPropertyGridCtrl::Init](#init)|Aufgerufen, um ein Eigenschaftenraster-Steuerelement zu initialisieren.|  
|[CMFCPropertyGridCtrl::OnChangeSelection](#onchangeselection)|Wird vom Framework aufgerufen, wenn die aktuelle Auswahl geändert wird.|  
|[CMFCPropertyGridCtrl::OnClickButton](#onclickbutton)|Wird vom Framework aufgerufen, wenn eine Eigenschaft Schaltfläche geklickt wird.|  
|[CMFCPropertyGridCtrl::OnDrawBorder](#ondrawborder)|Aufgerufen, um einen Rahmen um ein Eigenschaftenraster-Steuerelement zu zeichnen.|  
|[CMFCPropertyGridCtrl::OnDrawDescription](#ondrawdescription)|Vom Framework aufgerufen Beschreibungsbereich und den Text der Beschreibung anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnDrawList](#ondrawlist)|Aufgerufen, um die Liste der Eigenschaften in der Eigenschaftenraster-Steuerelement anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnDrawProperty](#ondrawproperty)|Aufgerufen, um eine Eigenschaft anzuzeigen.|  
|[CMFCPropertyGridCtrl::OnPropertyChanged](#onpropertychanged)|Wird vom Framework aufgerufen, wenn der Wert einer Eigenschaft geändert wird.|  
|[CMFCPropertyGridCtrl::OnSelectCombo](#onselectcombo)|Wird vom Framework aufgerufen, wenn eine Eigenschaft, die ein Kombinationsfeld-Steuerelement enthält, ausgewählt ist.|  
|[CMFCPropertyGridCtrl::ValidateItemData](#validateitemdata)|Aufgerufen, um die Daten zu überprüfen.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCPropertyGridCtrl` Klasse zeigt ein Eigenschaftenraster-Steuerelement, die von abgeleitete bearbeitbare Eigenschaften enthält die [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md) Klasse. Jede Eigenschaft kann einen Typ darstellen, und Unterelemente enthalten kann. Das Eigenschaftenraster-Steuerelement unterstützt einen in der Größe veränderbaren Bereich im unteren Bereich, der die Beschreibung der ausgewählten Eigenschaft angezeigt werden können.  
  
 Um ein Eigenschaftenraster-Steuerelement zu verwenden, erstellen Sie eine `CMFCPropertyGridCtrl` Objekt, und rufen Sie dann die [CMFCPropertyGridCtrl::Create](#create) Methode. Verwenden der [CMFCPropertyGridCtrl::AddProperty](#addproperty) Methode, um die Eigenschaften der Liste hinzuzufügen.  
  
## <a name="selection-properties"></a>Auswahl von Eigenschaften  
 Statt, die einen Wert darstellt, kann ein Eigenschaftenelement ein Dialogfeld starten, mit dem den Benutzer eine Farbe, die Datei oder die Schriftart auswählen können.  
  
 Die folgende Tabelle enthält vier Typen von Auswahl:  
  
|Klasse|Beschreibung|  
|-----------|-----------------|  
|[CMFCPropertyGridProperty-Klasse](../../mfc/reference/cmfcpropertygridproperty-class.md)|Eine Allzweck-Eigenschaft, die verwendet wird, um den Wert von Zeichenfolgen, boolesche Werte, Daten usw. anzugeben.|  
|[CMFCPropertyGridColorProperty-Klasse](../../mfc/reference/cmfcpropertygridcolorproperty-class.md)|Eine Eigenschaft, die verwendet wird, um einen Farbwert auszuwählen.|  
|[CMFCPropertyGridFileProperty-Klasse](../../mfc/reference/cmfcpropertygridfileproperty-class.md)|Eine Eigenschaft, die verwendet wird, um eine Datei auszuwählen.|  
|[CMFCPropertyGridFontProperty-Klasse](../../mfc/reference/cmfcpropertygridfontproperty-class.md)|Eine Eigenschaft, die zum Auswählen einer Schriftart verwendet wird.|  
  
## <a name="illustrations"></a>Abbildungen  
 In der folgenden Abbildung dargestellt ein Eigenschaftenraster-Steuerelement, das auf zwei Arten Eigenschaften anzeigt. Die erste Abbildung zeigt die Eigenschaften hierarchisch, und die zweite Eigenschaften alphabetisch angezeigt.  
  
 ![PropertySheet-Eigenschaftenliste](../../mfc/reference/media/proplist.png "Proplist")  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Eigenschaftenobjekt der Grid-Steuerelement zu konfigurieren, indem Sie mit verschiedenen Methoden in der `CMFCPropertyGridCtrl` Klasse. Im Beispiel wird veranschaulicht, wie das Kopfzeilen-Steuerelement zu aktivieren, aktivieren den Beschreibungsbereich, und legen Sie die Darstellung des Eigenschaftenraster-Steuerelement. Das Beispiel zeigt auch Gewusst wie: Festlegen dem alphabetischen Modus für das Steuerelement, bei dem das Steuerelement sortiert, alle Eigenschaften, die sie mit dem Namen ihrer Eigenschaft enthält, und wie Sie benutzerdefinierten Farben für die verschiedenen Elemente der Eigenschaftenraster-Steuerelement festlegen. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&14;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls Nr.&16;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_NewControls&20;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_3.cpp)]  
[!code-cpp[NVC_MFC_NewControls&21;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_4.cpp)]  
[!code-cpp[NVC_MFC_NewControls&#24;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_5.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CMFCPropertyGridCtrl](../../mfc/reference/cmfcpropertygridctrl-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxpropertygridctrl.h  
  
##  <a name="a-nameaccselecta--cmfcpropertygridctrlaccselect"></a><a name="accselect"></a>CMFCPropertyGridCtrl::accSelect  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT accSelect(
    long flagsSelect,  
    VARIANT varChild);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `flagsSelect`  
 [in] `varChild`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameaddpropertya--cmfcpropertygridctrladdproperty"></a><a name="addproperty"></a>CMFCPropertyGridCtrl::AddProperty  
 Ein Eigenschaftenraster-Steuerelement hinzugefügt eine neue Eigenschaft.  
  
```  
int AddProperty(
    CMFCPropertyGridProperty* pProp,  
    BOOL bRedraw=TRUE,  
    BOOL bAdjustLayout=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf eine Eigenschaft.  
  
 [in] `bRedraw`  
 `TRUE`die Eigenschaft sofort neu gezeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
 [in] `bAdjustLayout`  
 `TRUE`neu berechnen, wie zeichnen Sie den Text und den Wert der Eigenschaft und dann die Eigenschaft; `FALSE` zu vorhandene Berechnungen verwenden, um die Eigenschaft zu zeichnen. Der Standardwert ist `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn diese Methode, den nullbasierten Index der Position in der Eigenschaftenraster-Steuerelement erfolgreich ist, in dem die Eigenschaft hinzugefügt wird. andernfalls -1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fügt einen Zeiger auf die angegebene Eigenschaft am Ende der Liste der Eigenschaften in der Eigenschaftenraster-Steuerelement. Zerstören Sie die Eigenschaften nicht, und Verlassen des Bereichs vor der Zerstörung die Grid-Steuerelement zu ermöglichen. Wenn Sie mit dem Eigenschaftenraster-Steuerelement fertig sind, rufen Sie [CMFCPropertyGridCtrl::RemoveAll](#removeall) alle zusätzlichen Eigenschaften zu löschen. AddProperty-Methode schlägt fehl, wenn die angegebene Eigenschaft bereits zur Liste hinzugefügt wurde.  
  
##  <a name="a-nameadjustlayouta--cmfcpropertygridctrladjustlayout"></a><a name="adjustlayout"></a>CMFCPropertyGridCtrl::AdjustLayout  
 Zeichnet das Eigenschaftenraster-Steuerelement und seine Eigenschaften.  
  
```  
virtual void AdjustLayout();
```  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode berechnet die gesamte Eigenschaftenraster-Steuerelement und seine Eigenschaften, einschließlich Bildern, Schriftarten und Steuerelemente zeichnen.  
  
##  <a name="a-namealwaysshowusertooltipa--cmfcpropertygridctrlalwaysshowusertooltip"></a><a name="alwaysshowusertooltip"></a>CMFCPropertyGridCtrl::AlwaysShowUserToolTip  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
void AlwaysShowUserToolTip(BOOL bShow = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShow`  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameclosecolorpopupa--cmfcpropertygridctrlclosecolorpopup"></a><a name="closecolorpopup"></a>CMFCPropertyGridCtrl::CloseColorPopup  
 Schließt das Dialogfeld Farbe Auswahl.  
  
```  
virtual void CloseColorPopup();
```  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über das Dialogfeld Farbe Auswahl finden Sie unter [CMFCPropertyGridColorProperty Klasse](../../mfc/reference/cmfcpropertygridcolorproperty-class.md).  
  
##  <a name="a-namecmfcpropertygridctrla--cmfcpropertygridctrlcmfcpropertygridctrl"></a><a name="cmfcpropertygridctrl"></a>CMFCPropertyGridCtrl::CMFCPropertyGridCtrl  
 Erstellt ein `CMFCPropertyGridCtrl`-Objekt.  
  
```  
CMFCPropertyGridCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namecomparepropsa--cmfcpropertygridctrlcompareprops"></a><a name="compareprops"></a>CMFCPropertyGridCtrl::CompareProps  
 Wird von der Eigenschaftenraster-Steuerelement zum Sortieren der Eigenschaften aufgerufen.  
  
```  
virtual int CompareProps(
    const CMFCPropertyGridProperty* pProp1,  
    const CMFCPropertyGridProperty* pProp2) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `pProp1`  
 Ein Zeiger auf eine Eigenschaft.  
  
 `pProp2`  
 Ein Zeiger auf eine Eigenschaft.  
  
### <a name="return-value"></a>Rückgabewert  
  
|Rückgabewert|Beschreibung|  
|------------------|-----------------|  
|< 0|Der Name des der `pProp1` -Parameter ist kleiner als der Name des der `pProp2` Parameter.|  
|0|Der Name des der `pProp1` -Parameter ist identisch mit den Namen der `pProp2` Parameter.|  
|> 0|Der Name des der `pProp1` -Objekt ist größer als der Name des der `pProp2` Parameter.|  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode verwendet standardmäßig die [CString::Compare](../../atl-mfc-shared/reference/cstringt-class.md#compare) -Methode zum Vergleichen der `CMFCPropertyGridProperty::m_strName` Mitglieder der angegebenen Parameter.  
  
##  <a name="a-namecreatea--cmfcpropertygridctrlcreate"></a><a name="create"></a>CMFCPropertyGridCtrl::Create  
 Erstellt ein Eigenschaftenraster-Steuerelement aus, und fügt ihn der Eigenschaft Grid Control-Objekt.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwStyle`  
 Eine bitweise Kombination (OR) [Fensterstile](../../mfc/reference/window-styles.md).  
  
 [in] `rect`  
 Ein umschließendes Rechteck, der angibt, die Größe und Position des Fensters im Client-Koordinaten des `pParentWnd`.  
  
 [in] `pParentWnd`  
 Ein Zeiger auf das übergeordnete Fenster. Dieser Wert darf nicht `NULL` sein.  
  
 [in] `nID`  
 Die ID des untergeordneten Fensters.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Fenster erfolgreich erstellt wurde. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Die Erstellung eines Eigenschaftenraster-Steuerelement, das beim ersten Aufruf [CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](#cmfcpropertygridctrl) Eigenschaft Grid-Objekts erstellt. Rufen Sie dann `CMFCPropertyGridCtrl::Create`.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die `Create` -Methode in `CMFCPropertyGridCtrl` Klasse. Dieses Beispiel ist Teil der [Beispiel neue Steuerelemente](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls&#15;](../../mfc/reference/codesnippet/cpp/cmfcpropertygridctrl-class_6.cpp)]  
  
##  <a name="a-namedeletepropertya--cmfcpropertygridctrldeleteproperty"></a><a name="deleteproperty"></a>CMFCPropertyGridCtrl::DeleteProperty  
 Löscht die angegebene Eigenschaft aus dem Eigenschaftenraster-Steuerelement.  
  
```  
BOOL DeleteProperty(
    CMFCPropertyGridProperty*& pProp,  
    BOOL bRedraw=TRUE,  
    BOOL bAdjustLayout=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf eine Eigenschaft.  
  
 [in] `bRedraw`  
 `TRUE`das Eigenschaftenraster-Steuerelement neu gezeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
 [in] `bAdjustLayout`  
 `TRUE`neu berechnen, wie der Text, Bilder und Elemente in das Eigenschaftenraster-Steuerelement zu zeichnen, und zeichnen Sie das Steuerelement; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um eine Eigenschaft, und alle zugehörigen untergeordneten Elemente, über das Eigenschaftenraster-Steuerelement zu löschen.  
  
##  <a name="a-namedrawcontrolbarcolorsa--cmfcpropertygridctrldrawcontrolbarcolors"></a><a name="drawcontrolbarcolors"></a>CMFCPropertyGridCtrl::DrawControlBarColors  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL DrawControlBarColors() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameedititema--cmfcpropertygridctrledititem"></a><a name="edititem"></a>CMFCPropertyGridCtrl::EditItem  
 Wird vom Framework aufgerufen, wenn der Benutzer beginnt, eine Eigenschaft zu ändern.  
  
```  
virtual BOOL EditItem(
    CMFCPropertyGridProperty* pProp,  
    LPPOINT lptClick=NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf eine Eigenschaft.  
  
 [in] `lptClick`  
 Der Punkt in der Eigenschaftenraster-Steuerelement, das der Benutzer geklickt hat, um die Bearbeitung zu beginnen. Der Punkt ist in der Clientkoordinaten des Steuerelements. Der Standardwert ist `NULL`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameenabledescriptionareaa--cmfcpropertygridctrlenabledescriptionarea"></a><a name="enabledescriptionarea"></a>CMFCPropertyGridCtrl::EnableDescriptionArea  
 Aktiviert oder deaktiviert den Beschreibungsbereich, der unterhalb der Liste der Eigenschaften in der Eigenschaftenraster-Steuerelement angezeigt wird.  
  
```  
void EnableDescriptionArea(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`So aktivieren Sie den Beschreibungsbereich; `FALSE` Beschreibungsbereich zu deaktivieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Beschreibungsbereich wird am unteren Rand der Eigenschaftenraster-Steuerelement angezeigt. Standardmäßig ist der Beschreibungsbereich deaktiviert und nicht sichtbar.  
  
##  <a name="a-nameenableheaderctrla--cmfcpropertygridctrlenableheaderctrl"></a><a name="enableheaderctrl"></a>CMFCPropertyGridCtrl::EnableHeaderCtrl  
 Aktiviert oder deaktiviert das Kopfzeilen-Steuerelement am oberen Rand der Eigenschaftenraster-Steuerelement.  
  
```  
void EnableHeaderCtrl(
    BOOL bEnable=TRUE,  
    LPCTSTR lpszLeftColumn=_T("Property"),  
    LPCTSTR lpszRightColumn=_T("Value"));
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 `TRUE`um das Kopfzeilen-Steuerelement zu aktivieren. `FALSE` das Kopfzeilen-Steuerelement zu deaktivieren. Der Standardwert ist `TRUE`.  
  
 [in] `lpszLeftColumn`  
 Der Titel der linken Spalte mit dem Kopfzeilen-Steuerelement. Der Standardwert ist **Eigenschaft**.  
  
 [in] `lpszRightColumn`  
 Der Titel der rechten Spalte mit dem Kopfzeilen-Steuerelement. Der Standardwert ist **Wert**.  
  
##  <a name="a-nameendedititema--cmfcpropertygridctrlendedititem"></a><a name="endedititem"></a>CMFCPropertyGridCtrl::EndEditItem  
 Vom Framework aufgerufen, wenn der Benutzer eine Eigenschaft ändern.  
  
```  
virtual BOOL EndEditItem(BOOL bUpdateData=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bUpdateData`  
 `TRUE`um anzugeben, dass die geänderten Daten überprüft werden müssen, wenn der Bearbeitungsvorgang abgeschlossen ist; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Bearbeitungsvorgang erfolgreich beendet `FALSE` Wenn die geänderten Daten ungültig ist oder wenn der Bearbeitungsvorgang fortgesetzt werden soll.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameensurevisiblea--cmfcpropertygridctrlensurevisible"></a><a name="ensurevisible"></a>CMFCPropertyGridCtrl::EnsureVisible  
 Verschiebt ein Eigenschaftenraster-Steuerelement und erweitert die Items-Eigenschaft, bis die angegebene Eigenschaft angezeigt wird.  
  
```  
void EnsureVisible(
    CMFCPropertyGridProperty* pProp,  
    BOOL bExpandParents=FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf eine Eigenschaft.  
  
 [in] `bExpandParents`  
 `TRUE`Erweitern Sie übergeordnete Elemente, um die angegebene Eigenschaft sichtbar zu machen; andernfalls `FALSE`. Die Standardeinstellung ist `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameexpandalla--cmfcpropertygridctrlexpandall"></a><a name="expandall"></a>CMFCPropertyGridCtrl::ExpandAll  
 Erweitert oder reduziert alle Eigenschaft Grid-Steuerelement-Knoten.  
  
```  
void ExpandAll(BOOL bExpand=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bExpand`  
 `TRUE`Um alle Knoten zu erweitern; `FALSE` an alle Knoten zu reduzieren. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namefinditembydataa--cmfcpropertygridctrlfinditembydata"></a><a name="finditembydata"></a>CMFCPropertyGridCtrl::FindItemByData  
 Ruft die Eigenschaft, die eine benutzerdefinierte zugeordnet ist `DWORD` Wert.  
  
```  
CMFCPropertyGridProperty* FindItemByData(
    DWORD_PTR dwData,  
    BOOL bSearchSubItems=TRUE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwData`  
 Ein `DWORD`-Wert.  
  
 [in] `bSearchSubItems`  
 `TRUE`Eigenschaftenelemente gesucht werden soll. andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das Objekt zugeordnete Eigenschaft, wenn diese Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](#cmfcpropertygridctrl) Konstruktor oder [CMFCPropertyGridProperty::SetData](../../mfc/reference/cmfcpropertygridproperty-class.md#setdata) Methode zum Zuordnen einer `DWORD` mit einer Eigenschaft.  
  
##  <a name="a-namegetaccchildcounta--cmfcpropertygridctrlgetaccchildcount"></a><a name="get_accchildcount"></a>CMFCPropertyGridCtrl::get_accChildCount  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accChildCount(long* pcountChildren);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pcountChildren`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetaccfocusa--cmfcpropertygridctrlgetaccfocus"></a><a name="get_accfocus"></a>CMFCPropertyGridCtrl::get_accFocus  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accFocus(VARIANT* pvarChild);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pvarChild`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetacchelpa--cmfcpropertygridctrlgetacchelp"></a><a name="get_acchelp"></a>CMFCPropertyGridCtrl::get_accHelp  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accHelp(
    VARIANT varChild,  
    BSTR* pszHelp);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `varChild`  
 [in] `pszHelp`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetacchelptopica--cmfcpropertygridctrlgetacchelptopic"></a><a name="get_acchelptopic"></a>CMFCPropertyGridCtrl::get_accHelpTopic  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accHelpTopic(
    BSTR* pszHelpFile,  
    VARIANT varChild,  
    long* pidTopic);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pszHelpFile`  
 [in] `varChild`  
 [in] `pidTopic`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetacckeyboardshortcuta--cmfcpropertygridctrlgetacckeyboardshortcut"></a><a name="get_acckeyboardshortcut"></a>CMFCPropertyGridCtrl::get_accKeyboardShortcut  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accKeyboardShortcut(
    VARIANT varChild,  
    BSTR* pszKeyboardShortcut);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `varChild`  
 [in] `pszKeyboardShortcut`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetaccselectiona--cmfcpropertygridctrlgetaccselection"></a><a name="get_accselection"></a>CMFCPropertyGridCtrl::get_accSelection  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual HRESULT get_accSelection(VARIANT* pvarChildren);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pvarChildren`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetbkcolora--cmfcpropertygridctrlgetbkcolor"></a><a name="getbkcolor"></a>CMFCPropertyGridCtrl::GetBkColor  
 Ruft die Hintergrundfarbe für die aktuelle Eigenschaftenraster-Steuerelement ab.  
  
```  
COLORREF GetBkColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Farbe, die das Framework zum Zeichnen des Hintergrunds für das aktuelle Eigenschaftenraster-Steuerelement verwendet. Die [CMFCPropertyGridCtrl::GetTextColor](#gettextcolor) -Methode ruft die Vordergrundfarbe ab.  
  
##  <a name="a-namegetboldfonta--cmfcpropertygridctrlgetboldfont"></a><a name="getboldfont"></a>CMFCPropertyGridCtrl::GetBoldFont  
 Ruft die Windows-Schriftart, die zum Zeichnen von Text in der aktuellen Eigenschaftenraster-Steuerelement fett verwendet wird.  
  
```  
CFont& GetBoldFont();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf eine [CFont](../../mfc/reference/cfont-class.md) Objekt, das die Merkmale des fett beschreibt.  
  
##  <a name="a-namegetcursela--cmfcpropertygridctrlgetcursel"></a><a name="getcursel"></a>CMFCPropertyGridCtrl::GetCurSel  
 Ruft die derzeit ausgewählte Eigenschaft ab.  
  
```  
CMFCPropertyGridProperty* GetCurSel() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Eigenschaftenobjekt, das das ausgewählte Element in das Eigenschaftenraster-Steuerelement entspricht.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetcustomcolorsa--cmfcpropertygridctrlgetcustomcolors"></a><a name="getcustomcolors"></a>CMFCPropertyGridCtrl::GetCustomColors  
 Ruft die benutzerdefinierten Farben, die derzeit für die Eigenschaft Grid-Steuerelement Elemente definiert werden.  
  
```  
void GetCustomColors(
    COLORREF& clrBackground,  
    COLORREF& clrText,  
    COLORREF& clrGroupBackground,  
    COLORREF& clrGroupText,  
    COLORREF& clrDescriptionBackground,  
    COLORREF& clrDescriptionText,  
    COLORREF& clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `clrBackground`  
 Die Hintergrundfarbe von Eigenschaftswerten.  
  
 [out] `clrText`  
 Die Farbe der Eigenschaftsnamen und der Text der Eigenschaft-Wert.  
  
 [out] `clrGroupBackground`  
 Die Hintergrundfarbe einer Eigenschaftengruppe.  
  
 [out] `clrGroupText`  
 Die Farbe des Texts in der Eigenschaftengruppe.  
  
 [out] `clrDescriptionBackground`  
 Die Hintergrundfarbe im Bereich Beschreibung.  
  
 [out] `clrDescriptionText`  
 Die Farbe des Texts im Beschreibungsbereich.  
  
 [out] `clrLine`  
 Die Farbe der Zeilen, die zwischen Eigenschaften gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::SetCustomColors](#setcustomcolors) Methode, um benutzerdefinierte Farben festzulegen.  
  
##  <a name="a-namegetdescriptionheighta--cmfcpropertygridctrlgetdescriptionheight"></a><a name="getdescriptionheight"></a>CMFCPropertyGridCtrl::GetDescriptionHeight  
 Ruft die Höhe des Bereichs Beschreibung, die Sie am unteren Rand der Eigenschaftenraster-Steuerelement ab.  
  
```  
int GetDescriptionHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe in Pixel Bereich Beschreibung.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe der Beschreibungsbereich wird automatisch berechnet und auf 1/4 die Höhe der Eigenschaftenraster-Steuerelement festgelegt ist.  
  
 Verwenden der [CMFCPropertyGridCtrl::EnableDescriptionArea](#enabledescriptionarea) Methode anzuzeigenden bzw. auszublendenden Beschreibungsbereich. Verwenden der [CMFCPropertyGridCtrl::IsDescriptionArea](#isdescriptionarea) Methode, um zu bestimmen, ob der Beschreibungsbereich angezeigt oder ausgeblendet wird.  
  
##  <a name="a-namegetdescriptionrowsa--cmfcpropertygridctrlgetdescriptionrows"></a><a name="getdescriptionrows"></a>CMFCPropertyGridCtrl::GetDescriptionRows  
 Ruft die Anzahl der Zeilen im Beschreibungsbereich der aktuellen Eigenschaftenraster-Steuerelement ab.  
  
```  
int GetDescriptionRows() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen im Beschreibungsbereich der aktuellen Eigenschaftenraster-Steuerelement.  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](#cmfcpropertygridctrl) Konstruktor initialisiert den Beschreibungsbereich 3 Zeilen.  
  
##  <a name="a-namegetheaderctrla--cmfcpropertygridctrlgetheaderctrl"></a><a name="getheaderctrl"></a>CMFCPropertyGridCtrl::GetHeaderCtrl  
 Ruft die interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt, das Framework verwendet, um die aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.  
  
```  
virtual CMFCHeaderCtrl& GetHeaderCtrl();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Verweis auf ein `CMFCHeaderCtrl`-Objekt.  
  
##  <a name="a-namegetheaderheighta--cmfcpropertygridctrlgetheaderheight"></a><a name="getheaderheight"></a>CMFCPropertyGridCtrl::GetHeaderHeight  
 Ruft die Höhe des Headers ein Eigenschaftenraster-Steuerelement ab.  
  
```  
int GetHeaderHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe des Headers, in Pixel.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetleftcolumnwidtha--cmfcpropertygridctrlgetleftcolumnwidth"></a><a name="getleftcolumnwidth"></a>CMFCPropertyGridCtrl::GetLeftColumnWidth  
 Ruft ab, der die Breite der linken Spalte mit der aktuellen Eigenschaftenraster-Steuerelement, das den Namen jeder Eigenschaft enthält.  
  
```  
int GetLeftColumnWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Breite der Spalte.  
  
### <a name="remarks"></a>Hinweise  
 Die rechte Spalte ein Rastersteuerelement Eigenschaft enthält den Wert jeder Eigenschaft.  
  
##  <a name="a-namegetlistrecta--cmfcpropertygridctrlgetlistrect"></a><a name="getlistrect"></a>CMFCPropertyGridCtrl::GetListRect  
 Ruft das umschließende Rechteck für das Eigenschaftenraster-Steuerelement ab.  
  
```  
CRect GetListRect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das umschließende Rechteck für das Eigenschaftenraster-Steuerelement. Diese Rectange umfasst nicht den Beschreibungsbereich und Header.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpropertya--cmfcpropertygridctrlgetproperty"></a><a name="getproperty"></a>CMFCPropertyGridCtrl::GetProperty  
 Ruft einen Zeiger auf die Eigenschaftenobjekt, das dem angegebenen Index eines Elements in einem Eigenschaftenraster-Steuerelement entspricht.  
  
```  
CMFCPropertyGridProperty* GetProperty(int nIndex) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nIndex`  
 Der nullbasierte Index, der eine Eigenschaft Grid-Steuerelement ein Element.  
  
 Diese Methode überprüft, wenn die `nIndex` -Parameter ist kleiner als&0; (null) oder größer als oder gleich der Anzahl von Eigenschaften.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die Eigenschaftenobjekt, das dem angegebenen Index entspricht, wenn diese Methode erfolgreich ist; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetpropertycolumnwidtha--cmfcpropertygridctrlgetpropertycolumnwidth"></a><a name="getpropertycolumnwidth"></a>CMFCPropertyGridCtrl::GetPropertyColumnWidth  
 Ruft die aktuelle Breite der Spalte, die Eigenschaftswerte enthält.  
  
```  
int GetPropertyColumnWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die aktuelle Breite der Spalte, die Eigenschaftswerte enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die Spalte auf der rechten Seite in das Eigenschaftenraster-Steuerelement enthält die Eigenschaftswerte. Ein Kunde kann das Teilen von dem Eigenschaftenraster-Steuerelement verwenden, so ändern Sie die Breite der Wertespalte.  
  
##  <a name="a-namegetpropertycounta--cmfcpropertygridctrlgetpropertycount"></a><a name="getpropertycount"></a>CMFCPropertyGridCtrl::GetPropertyCount  
 Ruft die Anzahl der Eigenschaften in einem Eigenschaftenraster-Steuerelement ab.  
  
```  
int GetPropertyCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Eigenschaften.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namegetrowheighta--cmfcpropertygridctrlgetrowheight"></a><a name="getrowheight"></a>CMFCPropertyGridCtrl::GetRowHeight  
 Ruft die Höhe einer Zeile in der Eigenschaftenraster-Steuerelement ab.  
  
```  
int GetRowHeight() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Höhe einer Zeile.  
  
### <a name="remarks"></a>Hinweise  
 Die Höhe einer Zeile ist gleich der aktuellen Schriftarthöhe plus 4 Pixel.  
  
##  <a name="a-namegetscrollbarctrla--cmfcpropertygridctrlgetscrollbarctrl"></a><a name="getscrollbarctrl"></a>CMFCPropertyGridCtrl::GetScrollBarCtrl  
 Ruft einen Zeiger auf das ScrollBar-Steuerelement in das Eigenschaftenraster-Steuerelement ab.  
  
```  
virtual CScrollBar* GetScrollBarCtrl(int nBar) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nBar`  
 Die Ausrichtung der Bildlaufleiste, muss sich `SB_VERT`.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine Bildlaufleiste fest, oder `NULL` Wenn keine Bildlaufleiste vorhanden ist oder die Ausrichtung der Schiebeleiste `SB_HORZ`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode, um direkten Zugriff auf die vertikale Bildlaufleiste.  
  
##  <a name="a-namegettextcolora--cmfcpropertygridctrlgettextcolor"></a><a name="gettextcolor"></a>CMFCPropertyGridCtrl::GetTextColor  
 Ruft die Farbe, die zum Zeichnen des Texts Items-Eigenschaft in der aktuellen Eigenschaftenraster-Steuerelement verwendet wird.  
  
```  
COLORREF GetTextColor() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ruft die Farbe, die das Framework zum Zeichnen des Vordergrunds des die aktuelle Eigenschaftenraster-Steuerelement verwendet. Die [CMFCPropertyGridCtrl::GetBkColor](#getbkcolor) -Methode ruft die Hintergrundfarbe ab.  
  
##  <a name="a-namehittesta--cmfcpropertygridctrlhittest"></a><a name="hittest"></a>CMFCPropertyGridCtrl::HitTest  
 Ruft einen Zeiger auf die Eigenschaftenobjekt, das eine Eigenschaft Grid-Steuerelement ein Element entspricht, ist von ein angegebenen Punkt im Element ab. Diese Methode gibt auch den Bereich in das Eigenschaftenraster-Steuerelement, das den Punkt enthält.  
  
```  
CMFCPropertyGridProperty* HitTest(
    CPoint pt,  
    CMFCPropertyGridProperty::ClickArea* pnArea=NULL,  
    BOOL bPropsOnly=FALSE) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pt`  
 Ein Punkt in Clientkoordinaten.  
  
 [in, out] `pnArea`  
 Ein Zeiger auf eine `ClickArea` Variable. Wenn diese Methode zurückgibt, gibt die Variable an die *Eigenschaft Bereich* , die den angegebenen Punkt enthält. Weitere Informationen über eine Eigenschaft Bereich finden Sie unter "Hinweise".  
  
 [in] `bPropsOnly`  
 `TRUE`So testen Sie nur für den Bereich Eigenschaft; `FALSE` zum Testen der *Beschreibungsbereich* ist der angegebene Punkt nicht in den Bereich der Eigenschaft. Der Standardwert ist `FALSE`. Weitere Informationen zu den Beschreibungsbereich finden Sie unter "Hinweise".  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die `bPropsOnly` Parameter ist `TRUE` und der angegebene Punkt befindet sich in einem Eigenschaft-Bereich, der Rückgabewert ist ein Zeiger auf das entsprechende Eigenschaftenobjekt. Darüber hinaus die `pnArea` Parametersatz, der bestimmten Bereich, der den angegebenen Punkt enthält. Andernfalls der Rückgabewert ist `NULL` und `pnArea` Parameter nicht geändert.  
  
 Wenn die `bPropsOnly` Parameter ist `FALSE`, der Rückgabewert ist immer `NULL`. Jedoch, wenn der angegebene Punkt im Beschreibungsbereich wird die `pnArea` Parameter den Wert `CMFCPropertyGridProperty::ClickDescription`.  
  
### <a name="remarks"></a>Hinweise  
 Der Begriff *Eigenschaft Bereich* bezieht sich auf alle mit dem Namen, Wert, oder Erweitern Sie im Feld Bereiche einer Eigenschaft Grid-Steuerelement ein Element. Die *Beschreibungsbereich* ist die Zone am Ende ein Eigenschaftenraster-Steuerelement. Wenn Sie eine Eigenschaft Grid-Steuerelement ein Element klicken, zeigt der Beschreibungsbereich eine Beschreibung der entsprechenden Eigenschaft.  
  
 Diese Methode legt den Wert der Variablen fest, die den `pnArea` -Parameter zeigt. Die folgende Tabelle enthält die möglichen Werte und die entsprechenden Bereiche.  
  
|Wert|Bereich|  
|-----------|----------|  
|`ClickArea::ClickExpandBox`|-Eigenschaft erweitern-Steuerelement.|  
|`ClickArea::ClickName`|Der Eigenschaftenname.|  
|`ClickArea::ClickValue`|Der Eigenschaftswert.|  
|`CMFCPropertyGridProperty::ClickDescription`|Eigenschaft Steuerelement Beschreibung Rasterbereich.|  
  
##  <a name="a-nameinita--cmfcpropertygridctrlinit"></a><a name="init"></a>CMFCPropertyGridCtrl::Init  
 Aufgerufen, um ein Eigenschaftenraster-Steuerelement zu initialisieren.  
  
```  
virtual void Init();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameinitheadera--cmfcpropertygridctrlinitheader"></a><a name="initheader"></a>CMFCPropertyGridCtrl::InitHeader  
 Initialisiert die interne [CMFCHeaderCtrl](../../mfc/reference/cmfcheaderctrl-class.md) Objekt, das Framework verwendet, um die aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.  
  
```  
virtual void InitHeader();
```  
  
##  <a name="a-nameisalphabeticmodea--cmfcpropertygridctrlisalphabeticmode"></a><a name="isalphabeticmode"></a>CMFCPropertyGridCtrl::IsAlphabeticMode  
 Gibt an, ob ein Eigenschaftenraster-Steuerelement im alphabetischen Modus befindet.  
  
```  
BOOL IsAlphabeticMode() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Eigenschaftenraster-Steuerelement im alphabetischen Modus ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Eigenschaftenraster-Steuerelement im alphabetischen Modus befindet, werden alle Eigenschaften nach Namen alphabetisch sortiert. Andernfalls werden Eigenschaften unter ihre übergeordneten Knoten gruppiert.  
  
 Verwenden der [CMFCPropertyGridCtrl::SetAlphabeticMode](#setalphabeticmode) Methode zum Aktivieren oder Deaktivieren von alphabetischen Modus.  
  
##  <a name="a-nameisalwaysshowusertooltipa--cmfcpropertygridctrlisalwaysshowusertooltip"></a><a name="isalwaysshowusertooltip"></a>CMFCPropertyGridCtrl::IsAlwaysShowUserToolTip  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL IsAlwaysShowUserToolTip() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisdescriptionareaa--cmfcpropertygridctrlisdescriptionarea"></a><a name="isdescriptionarea"></a>CMFCPropertyGridCtrl::IsDescriptionArea  
 Gibt an, ob der Beschreibungsbereich der Eigenschaftenraster-Steuerelement angezeigt wird.  
  
```  
BOOL IsDescriptionArea() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn der Beschreibungsbereich angezeigt wird; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::EnableDescriptionArea](#enabledescriptionarea) Methode, um den Beschreibungsbereich angezeigt oder ausgeblendet.  
  
##  <a name="a-nameisgroupnamefullwidtha--cmfcpropertygridctrlisgroupnamefullwidth"></a><a name="isgroupnamefullwidth"></a>CMFCPropertyGridCtrl::IsGroupNameFullWidth  
 Gibt an, ob jeder Eigenschaftsname für die Gruppe über die Breite des der aktuellen Eigenschaftenraster-Steuerelement angezeigt wird.  
  
```  
BOOL IsGroupNameFullWidth() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Breite des der Eigenschaftenraster-Steuerelement Gruppennamen angezeigt werden; `FALSE` wenn Gruppennamen, indem Sie die Spalte nach rechts (Wert) des Steuerelements abgeschnitten werden.  
  
### <a name="remarks"></a>Hinweise  
 Ein *Gruppe* ist eine Sammlung verwandter Eigenschaften in einem Eigenschaftenraster-Steuerelement. Wenn das Steuerelement hierarchisch angezeigt wird die *Gruppenname* als eine Kategorietitel in der Zeile oberhalb der Gruppe angezeigt wird.  
  
##  <a name="a-nameisheaderctrla--cmfcpropertygridctrlisheaderctrl"></a><a name="isheaderctrl"></a>CMFCPropertyGridCtrl::IsHeaderCtrl  
 Gibt an, ob das Kopfzeilen-Steuerelement angezeigt wird.  
  
```  
BOOL IsHeaderCtrl() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Kopfzeilen-Steuerelement angezeigt wird. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::EnableHeaderCtrl](#enableheaderctrl) Methode, um das Kopfzeilen-Steuerelement angezeigt oder ausgeblendet.  
  
##  <a name="a-nameismarkmodifiedpropertiesa--cmfcpropertygridctrlismarkmodifiedproperties"></a><a name="ismarkmodifiedproperties"></a>CMFCPropertyGridCtrl::IsMarkModifiedProperties  
 Gibt an, wie das Eigenschaftenraster-Steuerelement geänderte Eigenschaften angezeigt.  
  
```  
BOOL IsMarkModifiedProperties() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Eigenschaften geändert, fett angezeigt wird; `FALSE` Eigenschaften geändert, wenn Schriftschnitt zur Anzeige verwendet wird.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameisshowdragcontexta--cmfcpropertygridctrlisshowdragcontext"></a><a name="isshowdragcontext"></a>CMFCPropertyGridCtrl::IsShowDragContext  
 Gibt an, ob das Framework die Spalten Name-Wert, der den aktuellen Eigenschaftenraster-Steuerelement, aktualisiert Wenn ein Benutzer ändert die Größe der Spalten.  
  
```  
BOOL IsShowDragContext() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Framework die Spalten Name und Wert während eines Vorgangs zum Ändern der Größe, zeichnet `FALSE` Wenn das Framework die Spalten neu zeichnet, nachdem der Ziehvorgang abgeschlossen ist.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer kann die Spalten Name und Wert, der ein Eigenschaftenraster-Steuerelement durch Ziehen der Leiste für geteilte, die zwischen den Spalten ändern. Wenn der Drag-Kontext angezeigt wird, werden die Spalten Name und Wert angepasst, solange der Benutzer den Fensterteiler zieht. Andernfalls verschiebt der Fensterteiler, aber die Spalten werden nicht neu gezeichnet, bis der Ziehvorgang abgeschlossen ist.  
  
##  <a name="a-nameisvsdotnetlooka--cmfcpropertygridctrlisvsdotnetlook"></a><a name="isvsdotnetlook"></a>CMFCPropertyGridCtrl::IsVSDotNetLook  
 Gibt an, ob die Darstellung des Eigenschaftenraster-Steuerelement im Stil von Visual Studio .NET ist.  
  
```  
BOOL IsVSDotNetLook() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn das Eigenschaftenraster-Steuerelement im Stil von Visual Studio .NET ist. andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::SetVSDotNetLook](#setvsdotnetlook) Methode, um den Stil von Visual Studio .NET das Eigenschaftenraster-Steuerelement fest.  
  
##  <a name="a-namemarkmodifiedpropertiesa--cmfcpropertygridctrlmarkmodifiedproperties"></a><a name="markmodifiedproperties"></a>CMFCPropertyGridCtrl::MarkModifiedProperties  
 Gibt an, wie geänderte Eigenschaften anzuzeigen.  
  
```  
void MarkModifiedProperties(
    BOOL bMark=TRUE,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bMark`  
 `TRUE`Eigenschaften in Fettdruck angezeigt geändert; `FALSE` in Schriftschnitt geänderte Eigenschaften angezeigt. Der Standardwert ist `TRUE`.  
  
 [in] `bRedraw`  
 `TRUE`das Eigenschaftenraster-Steuerelement sofort neu gezeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonchangeselectiona--cmfcpropertygridctrlonchangeselection"></a><a name="onchangeselection"></a>CMFCPropertyGridCtrl::OnChangeSelection  
 Wird vom Framework aufgerufen, wenn die aktuelle Auswahl geändert wird.  
  
```  
virtual void OnChangeSelection(
    CMFCPropertyGridProperty* pNewSel,   
    CMFCPropertyGridProperty* pOldSel);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pNewSel`|Ein Zeiger auf die neu ausgewählte Eigenschaft.|  
|[in] `pOldSel`|Ein Zeiger auf die zuvor ausgewählte Eigenschaft.|  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung dieser Methode wird keine Aktion ausgeführt.  
  
##  <a name="a-nameonclickbuttona--cmfcpropertygridctrlonclickbutton"></a><a name="onclickbutton"></a>CMFCPropertyGridCtrl::OnClickButton  
 Wird vom Framework aufgerufen, wenn eine Eigenschaft Schaltfläche geklickt wird.  
  
```  
virtual void OnClickButton(CPoint point);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `point`  
 Ein Punkt in Clientkoordinaten.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig aktualisiert diese Methode den aktuellen Eigenschaftenwert.  
  
##  <a name="a-nameondrawbordera--cmfcpropertygridctrlondrawborder"></a><a name="ondrawborder"></a>CMFCPropertyGridCtrl::OnDrawBorder  
 Aufgerufen, um einen Rahmen um ein Eigenschaftenraster-Steuerelement zu zeichnen.  
  
```  
virtual void OnDrawBorder(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawdescriptiona--cmfcpropertygridctrlondrawdescription"></a><a name="ondrawdescription"></a>CMFCPropertyGridCtrl::OnDrawDescription  
 Vom Framework aufgerufen Beschreibungsbereich und den Text der Beschreibung anzuzeigen.  
  
```  
virtual void OnDrawDescription(
    CDC* pDC,  
    CRect rect);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `rect`  
 Ein Rechteck, das angibt, wo Sie den Beschreibungsbereich zeichnen.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden der [CMFCPropertyGridCtrl::EnableDescriptionArea](#enabledescriptionarea) -Methode Beschreibungsbereich angezeigt.  
  
##  <a name="a-nameondrawlista--cmfcpropertygridctrlondrawlist"></a><a name="ondrawlist"></a>CMFCPropertyGridCtrl::OnDrawList  
 Aufgerufen, um die Liste der Eigenschaften in der Eigenschaftenraster-Steuerelement anzuzeigen.  
  
```  
virtual void OnDrawList(CDC* pDC);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameondrawpropertya--cmfcpropertygridctrlondrawproperty"></a><a name="ondrawproperty"></a>CMFCPropertyGridCtrl::OnDrawProperty  
 Aufgerufen, um eine Eigenschaft anzuzeigen.  
  
```  
virtual int OnDrawProperty(
    CDC* pDC,  
    CMFCPropertyGridProperty* pProp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pDC`  
 Ein Zeiger zu einem Gerätekontext.  
  
 [in] `pProp`  
 Ein Zeiger auf ein Objekt.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn diese Methode erfolgreich ist; andernfalls `FALSE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonpropertychangeda--cmfcpropertygridctrlonpropertychanged"></a><a name="onpropertychanged"></a>CMFCPropertyGridCtrl::OnPropertyChanged  
 Wird vom Framework aufgerufen, wenn der Wert einer Eigenschaft geändert wird.  
  
```  
virtual void OnPropertyChanged(CMFCPropertyGridProperty* pProp) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf ein Objekt, dessen Wert geändert wurde.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode sendet standardmäßig die [AFX_WM_PROPERTY_CHANGED](../../mfc/reference/afx-messages.md) Nachricht an den Besitzer der Eigenschaftenraster-Steuerelement.  
  
##  <a name="a-nameonselectcomboa--cmfcpropertygridctrlonselectcombo"></a><a name="onselectcombo"></a>CMFCPropertyGridCtrl::OnSelectCombo  
 Wird vom Framework aufgerufen, wenn eine Eigenschaft, die ein Kombinationsfeld-Steuerelement enthält, ausgewählt ist.  
  
```  
void OnSelectCombo();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameremovealla--cmfcpropertygridctrlremoveall"></a><a name="removeall"></a>CMFCPropertyGridCtrl::RemoveAll  
 Entfernt alle Property-Objekte aus einem Eigenschaftenraster-Steuerelement.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameresetoriginalvaluesa--cmfcpropertygridctrlresetoriginalvalues"></a><a name="resetoriginalvalues"></a>CMFCPropertyGridCtrl::ResetOriginalValues  
 Stellt die ursprünglichen Werte aller Eigenschaften.  
  
```  
void ResetOriginalValues(BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bRedraw`  
 `TRUE`zum Neuzeichnen der Eigenschaftenliste andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetalphabeticmodea--cmfcpropertygridctrlsetalphabeticmode"></a><a name="setalphabeticmode"></a>CMFCPropertyGridCtrl::SetAlphabeticMode  
 Legt fest oder setzt alphabetischen Modus zurück.  
  
```  
void SetAlphabeticMode(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`zum Festlegen von alphabetischen Modus; `FALSE` alphabetischen Zurücksetzmodus. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn das Eigenschaftenraster-Steuerelement im alphabetischen Modus befindet, sortiert das Steuerelement die Eigenschaften, die sie mit dem Namen ihrer Eigenschaft enthält.  
  
##  <a name="a-namesetboollabelsa--cmfcpropertygridctrlsetboollabels"></a><a name="setboollabels"></a>CMFCPropertyGridCtrl::SetBoolLabels  
 Gibt den Text der booleschen Bezeichnungen.  
  
```  
void SetBoolLabels(
    LPCTSTR lpszTrue,  
    LPCTSTR lpszFalse);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszTrue`  
 Die Zeichenfolge für den booleschen Wert "true" angezeigt.  
  
 [in] `lpszFalse`  
 Die Zeichenfolge für den booleschen Wert "false" angezeigt.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-namesetcursela--cmfcpropertygridctrlsetcursel"></a><a name="setcursel"></a>CMFCPropertyGridCtrl::SetCurSel  
 Wählt eine Eigenschaft in einem Eigenschaftenraster-Steuerelement aus.  
  
```  
void SetCurSel(
    CMFCPropertyGridProperty* pProp,  
    BOOL bRedraw=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pProp`  
 Ein Zeiger auf ein Objekt.  
  
 [in] `bRedraw`  
 `TRUE`das Eigenschaftenraster-Steuerelement sofort neu gezeichnet; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diese Methode zum Aufheben der Auswahl des aktuellen Elements in der Eigenschaftenraster-Steuerelement, und wählen Sie dann das Element, das der angegebenen Eigenschaft entspricht.  
  
##  <a name="a-namesetcustomcolorsa--cmfcpropertygridctrlsetcustomcolors"></a><a name="setcustomcolors"></a>CMFCPropertyGridCtrl::SetCustomColors  
 Gibt benutzerdefinierte Farben für die verschiedenen Elemente der Eigenschaftenraster-Steuerelement an.  
  
```  
void SetCustomColors(
    COLORREF clrBackground,  
    COLORREF clrText,  
    COLORREF clrGroupBackground,  
    COLORREF clrGroupText,  
    COLORREF clrDescriptionBackground,  
    COLORREF clrDescriptionText,  
    COLORREF clrLine);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `clrBackground`  
 Die Hintergrundfarbe von Eigenschaftswerten.  
  
 [in] `clrText`  
 Die Farbe der Eigenschaftsnamen und der Text der Eigenschaft-Wert.  
  
 [in] `clrGroupBackground`  
 Die Hintergrundfarbe einer Eigenschaftengruppe.  
  
 [in] `clrGroupText`  
 Die neue Textfarbe Eigenschaftengruppe.  
  
 [in] `clrDescriptionBackground`  
 Die Hintergrundfarbe im Bereich Beschreibung.  
  
 [in] `clrDescriptionText`  
 Die Farbe des Texts im Beschreibungsbereich.  
  
 [in] `clrLine`  
 Die Farbe der Zeilen, die zwischen Eigenschaften gezeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Geben Sie für alle Parameter der `((COLORREF)-1)` Farbwert die Standardfarbe für dieses Element von der Eigenschaftenraster-Steuerelement verwenden.  
  
 Um die Darstellung einer bestimmten Eigenschaft anzupassen, leiten Sie eine Klasse von der [CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md) Klasse, und überschreiben Sie dann die [CMFCPropertyGridProperty::OnDrawName](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawname), [CMFCPropertyGridProperty::OnDrawValue](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawvalue), [CMFCPropertyGridProperty::OnDrawExpandBox](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawexpandbox), und [CMFCPropertyGridProperty::OnDrawButton](../../mfc/reference/cmfcpropertygridproperty-class.md#ondrawbutton) Methoden.  
  
##  <a name="a-namesetdescriptionrowsa--cmfcpropertygridctrlsetdescriptionrows"></a><a name="setdescriptionrows"></a>CMFCPropertyGridCtrl::SetDescriptionRows  
 Gibt die Anzahl der Zeilen, die im Beschreibungsabschnitt "von der aktuellen Eigenschaftenraster-Steuerelement anzuzeigen.  
  
```  
void SetDescriptionRows(int nDescRows);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nDescRows`  
 Die Anzahl der Zeilen in der Beschreibung der Eigenschaft angezeigt.  
  
##  <a name="a-namesetgroupnamefullwidtha--cmfcpropertygridctrlsetgroupnamefullwidth"></a><a name="setgroupnamefullwidth"></a>CMFCPropertyGridCtrl::SetGroupNameFullWidth  
 Gibt an, ob die gesamte Breite des der Kategoriename für eine Gruppe von Eigenschaften in der aktuellen Eigenschaftenraster-Steuerelement angezeigt werden soll.  
  
```  
void SetGroupNameFullWidth(
    BOOL bGroupNameFullWidth = TRUE,  
    BOOL bRedraw = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bGroupNameFullWidth`  
 `TRUE`die vollständige Breite unabhängig von der Breite der Eigenschaftenspalte den Namen der Kategorie an. `FALSE`die Breite der Namen der Kategorie, der die Breite der Eigenschaftenspalte zu begrenzen. Der Standardwert ist `TRUE`.  
  
 [in] `bRedraw`  
 `TRUE`um das Eigenschaftenraster-Steuerelement sofort zu aktualisieren; `FALSE` des Steuerelements zu aktualisieren, wenn die nächste Clientbereich Ereignis auftritt. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Das Eigenschaftenraster-Steuerelement besteht aus einem mit veränderbarer Größe *Eigenschaftennamen* Spalte und eine *Eigenschaftswert* Spalte. Das Ende der Namensspalte wird auch am Anfang der Wertspalte. Ziehen Sie den Rand zwischen den Spalten, um die Größe der Spalten.  
  
 Die Begriffe *Gruppenname* und *Kategorienamen* werden in dieser Methode synonym verwendet. Der Kategoriename wird in einer Zeile angezeigt, die einen Satz verwandter Eigenschaften und Werte leitet. Diese Methode gibt an, ob die Breite der Eigenschaftenspalte auch die Breite des Kategorienamens angezeigt gibt.  
  
##  <a name="a-namesetlistdelimitera--cmfcpropertygridctrlsetlistdelimiter"></a><a name="setlistdelimiter"></a>CMFCPropertyGridCtrl::SetListDelimiter  
 Definiert ein Zeichen, das als Trennzeichen in einer Liste von Eigenschaftswerten verwendet wird.  
  
```  
void SetListDelimiter(TCHAR c);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `c`  
 Ein Zeichen als Trennzeichen dienen.  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Methode können Sie ein Trennzeichen in einer Liste von Eigenschaftswerten in zum Definieren der [CMFCPropertyGridProperty::CMFCPropertyGridProperty](../../mfc/reference/cmfcpropertygridproperty-class.md#cmfcpropertygridproperty) Konstruktor. Legen Sie diesen Konstruktor, der `bIsValueList` Parameter `TRUE`.  
  
 In der Standardeinstellung die [CMFCPropertyGridCtrl::CMFCPropertyGridCtrl](#cmfcpropertygridctrl) -Konstruktor legt die Trennzeichen auf Komma (',').  
  
##  <a name="a-namesetshowdragcontexta--cmfcpropertygridctrlsetshowdragcontext"></a><a name="setshowdragcontext"></a>CMFCPropertyGridCtrl::SetShowDragContext  
 Gibt an, ob das Framework die Spalten Name-Wert, der den aktuellen Eigenschaftenraster-Steuerelement, aktualisiert Wenn ein Benutzer ändert die Größe der Spalten.  
  
```  
void SetShowDragContext(BOOL bShowDragContext = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bShowDragContext`  
 `TRUE`während eines Vorgangs zum Ändern der Größe der Spalten für Name und Wert neu gezeichnet; `FALSE` Spalten neu zeichnen, nachdem der Ziehvorgang abgeschlossen ist. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Der Benutzer kann die Spalten Name und Wert, der ein Eigenschaftenraster-Steuerelement durch Ziehen der Leiste für geteilte, die zwischen den Spalten ändern. Wenn der Drag-Kontext angezeigt wird, werden die Spalten Name und Wert angepasst, solange der Benutzer den Fensterteiler zieht. Andernfalls verschiebt der Fensterteiler, aber die Spalten werden nicht neu gezeichnet, bis der Ziehvorgang abgeschlossen ist.  
  
##  <a name="a-namesetvsdotnetlooka--cmfcpropertygridctrlsetvsdotnetlook"></a><a name="setvsdotnetlook"></a>CMFCPropertyGridCtrl::SetVSDotNetLook  
 Legt die Darstellung des Eigenschaftenraster-Steuerelement auf das Format, das in Visual Studio .NET verwendet wird.  
  
```  
void SetVSDotNetLook(BOOL bSet=TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 `TRUE`das Eigenschaftenraster-Steuerelement auf das Format festlegen, die in Visual Studio .NET verwendet wird; andernfalls `FALSE`. Der Standardwert ist `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameupdatecolora--cmfcpropertygridctrlupdatecolor"></a><a name="updatecolor"></a>CMFCPropertyGridCtrl::UpdateColor  
 Legt den Farbwert der Eigenschaft zurzeit ausgewählte Farbe fest.  
  
```  
virtual void UpdateColor(COLORREF color);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `color`  
 Ein Wert für den RGB-Farbe.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode bestätigt im Debug-Modus bei der aktuell ausgewählte Eigenschaft das Eigenschaftenraster-Steuerelement keine Color-Eigenschaft.  
  
##  <a name="a-namevalidateitemdataa--cmfcpropertygridctrlvalidateitemdata"></a><a name="validateitemdata"></a>CMFCPropertyGridCtrl::ValidateItemData  
 Aufgerufen, um die Daten zu überprüfen.  
  
```  
virtual BOOL ValidateItemData(CMFCPropertyGridProperty* pProp);
```  
  
### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|[in] `pProp`|Ein Zeiger auf eine Eigenschaft. Dieser Parameter wird nicht verwendet.|  
  
### <a name="return-value"></a>Rückgabewert  
 Immer `TRUE`.  
  
### <a name="remarks"></a>Hinweise  
 Die [CMFCPropertyGridCtrl::EndEditItem](#endedititem) -Methode ruft diese Methode zum Validieren von Daten. Standardmäßig wird diese Methode nicht verwenden die `pProp` Parameter und der Rückgabewert ist immer `TRUE`.  
  
 Wenn Sie diese Methode überschreiben, zurück `TRUE` , wenn die angegebene Eigenschaftendaten gültig sind. Andernfalls zurück `FALSE`, in diesem Fall das Framework die Eigenschaft nicht aktualisiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

