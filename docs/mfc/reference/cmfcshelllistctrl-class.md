---
title: CMFCShellListCtrl Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCShellListCtrl
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellListCtrl class
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
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
ms.openlocfilehash: 8adac043d30d7555522c05165ffd3856c5999872
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl-Klasse
Die `CMFCShellListCtrl` -Klasse bietet Windows eine Liste und erweitert diese durch die Fähigkeit, eine Liste von shellelementen anzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Zeigt eine Liste der Elemente, die in einem angegebenen Ordner enthalten sind.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Zeigt eine Liste der Elemente, die im Ordner enthalten sind, die das übergeordnete Element des aktuellen Ordner ist.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Ruft den Pfad des aktuellen Ordners.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Ruft den Namen des aktuellen Ordners.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Gibt die PIDL des aktuellen Steuerelements Listenelements zurück.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Gibt einen Zeiger auf den aktuellen Shell-Ordner.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Gibt den Text Pfad eines Elements zurück.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Gibt die Shell-Elementtypen, die durch das Listensteuerelement angezeigt werden.|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Überprüft, ob es sich bei der aktuell ausgewählte Ordner des Ordners desktop ist.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Das Framework ruft diese Methode auf, wenn zwei Elemente verglichen. (Überschreibt [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Wird aufgerufen, wenn das Framework Ruft das Datum angezeigt, wenn das Listensteuerelement ab.|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Wird aufgerufen, wenn das Framework die Größe eines Steuerelements konvertiert.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Wird aufgerufen, wenn das Framework Ruft das Symbol für ein Listenelement-Steuerelement ab.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Wird aufgerufen, wenn das Framework den Text von einem Steuerelement ein Element konvertiert.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Wird vom Framework aufgerufen, wenn die Namen der Spalten festgelegt.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Wird aktualisiert und das Listensteuerelement aktualisiert.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Legt den Typ der Elemente, die durch das Listensteuerelement angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCShellListCtrl` -Klasse erweitert die Funktionalität der [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md) durch das Programm Windows-Shell-Elemente auflisten. Das Anzeigeformat, das verwendet wird, ist wie eine Ansicht für ein Explorer-Fenster.  
  
 Ein [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt zugeordnet werden kann ein `CMFCShellListCtrl` Objekt, um eine vollständige Explorer-Fenster zu erstellen. Wählen Sie dann, ein Element in der `CMFCShellTreeCtrl` führt dazu, dass die `CMFCShellListCtrl` Objekt zum Auflisten des Inhalts des ausgewählten Elements.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt von der `CMFCShellListCtrl` -Klasse und wie den übergeordnete Ordner des aktuell angezeigten Ordner angezeigt. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer&#1;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer&#2;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer&3;](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 `CMFCShellListCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshelllistCtrl.h  
  
##  <a name="a-namedisplayfoldera--cmfcshelllistctrldisplayfolder"></a><a name="displayfolder"></a>CMFCShellListCtrl::DisplayFolder  
 Zeigt eine Liste der Elemente, die im angegebenen Ordner enthalten sind.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPath`  
 Eine Zeichenfolge, die den Pfad eines Ordners enthält.  
  
 [in] `lpItemInfo`  
 Ein Zeiger auf eine `LPAFX_SHELLITEMINFO` -Struktur, die einen Ordner beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg; `E_FAIL` andernfalls.  
  
##  <a name="a-namedisplayparentfoldera--cmfcshelllistctrldisplayparentfolder"></a><a name="displayparentfolder"></a>CMFCShellListCtrl::DisplayParentFolder  
 Updates der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt, um den übergeordneten Ordner des aktuell angezeigten Ordners anzuzeigen.  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg; `E_FAIL` andernfalls.  
  
##  <a name="a-nameenableshellcontextmenua--cmfcshelllistctrlenableshellcontextmenu"></a><a name="enableshellcontextmenu"></a>CMFCShellListCtrl::EnableShellContextMenu  
 Können das Kontextmenü.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob das Framework das Kontextmenü ermöglicht.  
  
##  <a name="a-namegetcurrentfoldera--cmfcshelllistctrlgetcurrentfolder"></a><a name="getcurrentfolder"></a>CMFCShellListCtrl::GetCurrentFolder  
 Ruft den Pfad des ausgewählten Ordners in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strPath`  
 Ein Verweis auf einen Zeichenfolgenparameter, der die Methode den Pfad schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn es keine Ordner im ausgewählten der `CMFCShellListCtrl`.  
  
##  <a name="a-namegetcurrentfoldernamea--cmfcshelllistctrlgetcurrentfoldername"></a><a name="getcurrentfoldername"></a>CMFCShellListCtrl::GetCurrentFolderName  
 Ruft den Namen des aktuell ausgewählten Ordner in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strName`  
 Ein Verweis auf einen Zeichenfolgenparameter, der die Methode den Namen schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn es keine Ordner im ausgewählten der `CMFCShellListCtrl`.  
  
##  <a name="a-namegetcurrentitemidlista--cmfcshelllistctrlgetcurrentitemidlist"></a><a name="getcurrentitemidlist"></a>CMFCShellListCtrl::GetCurrentItemIdList  
 Gibt die PIDL des derzeit ausgewählten Elements zurück.  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die PIDL des aktuellen Elements.  
  
##  <a name="a-namegetcurrentshellfoldera--cmfcshelllistctrlgetcurrentshellfolder"></a><a name="getcurrentshellfolder"></a>CMFCShellListCtrl::GetCurrentShellFolder  
 Ruft einen Zeiger auf das aktuell ausgewählte Element in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [IShellFolder Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/bb775075) für das ausgewählte Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `NULL` Wenn derzeit kein Objekt ausgewählt ist.  
  
##  <a name="a-namegetitempatha--cmfcshelllistctrlgetitempath"></a><a name="getitempath"></a>CMFCShellListCtrl::GetItemPath  
 Ruft den Pfad für ein Element.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    int iItem) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strPath`  
 Ein Verweis auf eine Zeichenfolge, die den Pfad empfängt.  
  
 [in] `iItem`  
 Der Index des Listenelements.  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Bei Erfolg; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Der Index, der vom `iItem` basiert auf die derzeit vom angezeigten Elemente der [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
##  <a name="a-namegetitemtypesa--cmfcshelllistctrlgetitemtypes"></a><a name="getitemtypes"></a>CMFCShellListCtrl::GetItemTypes  
 Gibt den Typ der Elemente angezeigt, wenn die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539) Wert, der den Typ der Elemente, die in aufgeführten enthält die `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Hinweise  
 Beim Festlegen des Typs der Elemente, die gemäß einer `CMFCShellListCtrl`, rufen Sie [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="a-nameisdesktopa--cmfcshelllistctrlisdesktop"></a><a name="isdesktop"></a>CMFCShellListCtrl::IsDesktop  
 Bestimmt, ob der Ordner, die angezeigt wird, der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt ist der desktop-Ordner.  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die angezeigte Ordner des Ordners desktop ist. `FALSE` andernfalls.  
  
##  <a name="a-nameoncompareitemsa--cmfcshelllistctrloncompareitems"></a><a name="oncompareitems"></a>CMFCShellListCtrl::OnCompareItems  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual int OnCompareItems(
    LPARAM lParam1,  
    LPARAM lParam2,  
    int iColumn);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lParam1`  
 [in] `lParam2`  
 [in] `iColumn`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="a-nameonformatfiledatea--cmfcshelllistctrlonformatfiledate"></a><a name="onformatfiledate"></a>CMFCShellListCtrl::OnFormatFileDate  
 Das Framework ruft diese Methode auf, wenn sie das Datum, die einem Objekt zugeordnet sind, in eine Zeichenfolge konvertieren muss.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `tmFile`  
 Das Datum, die einer Datei zugeordnet.  
  
 [out] `str`  
 Eine Zeichenfolge, die das formatierte Datum enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt zeigt das Datum, die mit einer Datei verknüpft sind, müssen sie dieses Datum in ein Zeichenfolgenformat konvertieren. Die `CMFCShellListCtrl` wird mit dieser Methode, dass die Konvertierung vornehmen. Standardmäßig verwendet diese Methode das aktuelle Gebietsschema zum Formatieren des Datums in eine Zeichenfolge.  
  
##  <a name="a-nameonformatfilesizea--cmfcshelllistctrlonformatfilesize"></a><a name="onformatfilesize"></a>CMFCShellListCtrl::OnFormatFileSize  
 Das Framework ruft diese Methode auf, wenn die Größe eines Objekts in eine Zeichenfolge konvertiert.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lFileSize`  
 Die Größe der Datei, die das Framework angezeigt werden.  
  
 [out] `str`  
 Eine Zeichenfolge, die die Größe der Datei im Format enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt benötigt die Größe einer Datei anzeigen, um die Dateigröße in ein Zeichenfolgenformat zu konvertieren. Die `CMFCShellListCtrl` wird mit dieser Methode, dass die Konvertierung vornehmen. Standardmäßig wird diese Methode die Dateigröße von Bytes in Kilobytes konvertiert und anschließend das aktuelle Gebietsschema verwendet, um die Größe in Zeichenfolge formatieren.  
  
##  <a name="a-nameongetitemicona--cmfcshelllistctrlongetitemicon"></a><a name="ongetitemicon"></a>CMFCShellListCtrl::OnGetItemIcon  
 Das Framework ruft diese Methode, um das Symbol für ein Listenelement Shell abrufen.  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der Index des Elements.  
  
 [in] `pItem`  
 Ein `LPAFX_SHELLITEMINFO` -Parameter, der das Element beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Symbolbilds bei Erfolg;&1;, wenn die Funktion fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Symbol Bildindex basiert darauf, dass die Systembildliste.  
  
 Diese Methode benötigt standardmäßig auf die `pItem` Parameter. Der Wert des `iItem` wird in die standardmäßige Implementierung nicht verwendet. Sie können `iItem` , benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="a-nameongetitemtexta--cmfcshelllistctrlongetitemtext"></a><a name="ongetitemtext"></a>CMFCShellListCtrl::OnGetItemText  
 Das Framework ruft diese Methode auf, wenn den Text eines Shell-Elements abgerufen werden muss.  
  
```  
virtual CString OnGetItemText(
    int iItem,  
    int iColumn,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der Index des Elements.  
  
 [in] `iColumn`  
 Die Spalte von Interesse sind.  
  
 [in] `pItem`  
 Ein `LPAFX_SHELLITEMINFO` -Parameter, der das Element beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , der dem Element zugeordneten Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Element in der `CMFCShellListCtrl` Objekt kann Text in eine oder mehrere Spalten enthalten. Wenn das Framework diese Methode aufruft, wird die Spalte, der von Interesse sind. Wenn Sie diese Funktion manuell aufrufen, müssen Sie auch die Spalte angeben, der Sie interessiert sind.  
  
 Diese Methode benötigt standardmäßig auf die `pItem` Parameter zu bestimmen, die den Prozess Element. Der Wert des `iItem` wird in die standardmäßige Implementierung nicht verwendet.  
  
##  <a name="a-nameonsetcolumnsa--cmfcshelllistctrlonsetcolumns"></a><a name="onsetcolumns"></a>CMFCShellListCtrl::OnSetColumns  
 Das Framework ruft diese Methode auf, wenn die Namen der Spalten festgelegt.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig erstellt das Framework vier Spalten in einem `CMFCShellListCtrl` Objekt. Die Namen dieser Spalten sind `Name`, `Size`, `Type`, und `Modified`. Überschreiben Sie diese Methode, um die Anzahl der Spalten und deren Namen anpassen.  
  
##  <a name="a-namerefresha--cmfcshelllistctrlrefresh"></a><a name="refresh"></a>CMFCShellListCtrl::Refresh  
 Wird aktualisiert, und aktualisiert die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg; andernfalls einen Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktualisieren der Liste der Elemente angezeigt, wenn die `CMFCShellListCtrl` Objekt.  
  
##  <a name="a-namesetitemtypesa--cmfcshelllistctrlsetitemtypes"></a><a name="setitemtypes"></a>CMFCShellListCtrl::SetItemTypes  
 Legt den Typ der Elemente, die im aufgeführt sind die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTypes`  
 Eine Liste der Typen, die die `CMFCShellListCtrl` -Objekt unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen über die Liste von Elementtypen finden Sie unter [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)

