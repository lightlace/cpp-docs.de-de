---
title: CMFCShellListCtrl Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::DisplayParentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::EnableShellContextMenu
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentFolderName
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentItemIdList
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetCurrentShellFolder
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemPath
- AFXSHELLLISTCTRL/CMFCShellListCtrl::GetItemTypes
- AFXSHELLLISTCTRL/CMFCShellListCtrl::IsDesktop
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnCompareItems
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileDate
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnFormatFileSize
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemIcon
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnGetItemText
- AFXSHELLLISTCTRL/CMFCShellListCtrl::OnSetColumns
- AFXSHELLLISTCTRL/CMFCShellListCtrl::Refresh
- AFXSHELLLISTCTRL/CMFCShellListCtrl::SetItemTypes
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellListCtrl [MFC], DisplayFolder
- CMFCShellListCtrl [MFC], DisplayParentFolder
- CMFCShellListCtrl [MFC], EnableShellContextMenu
- CMFCShellListCtrl [MFC], GetCurrentFolder
- CMFCShellListCtrl [MFC], GetCurrentFolderName
- CMFCShellListCtrl [MFC], GetCurrentItemIdList
- CMFCShellListCtrl [MFC], GetCurrentShellFolder
- CMFCShellListCtrl [MFC], GetItemPath
- CMFCShellListCtrl [MFC], GetItemTypes
- CMFCShellListCtrl [MFC], IsDesktop
- CMFCShellListCtrl [MFC], OnCompareItems
- CMFCShellListCtrl [MFC], OnFormatFileDate
- CMFCShellListCtrl [MFC], OnFormatFileSize
- CMFCShellListCtrl [MFC], OnGetItemIcon
- CMFCShellListCtrl [MFC], OnGetItemText
- CMFCShellListCtrl [MFC], OnSetColumns
- CMFCShellListCtrl [MFC], Refresh
- CMFCShellListCtrl [MFC], SetItemTypes
ms.assetid: ad472958-5586-4c50-aadf-1844c30bf6e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9073c3443b1c74a27c9de9be142c67fab7f40ba8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="cmfcshelllistctrl-class"></a>CMFCShellListCtrl-Klasse
Die `CMFCShellListCtrl` Klasse bietet Windows eine Liste und erweitert diese durch die Fähigkeit, eine Liste von shellelementen anzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCShellListCtrl : public CMFCListCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCShellListCtrl::DisplayFolder](#displayfolder)|Zeigt eine Liste von Elementen, die in einem angegebenen Ordner enthalten sind.|  
|[CMFCShellListCtrl::DisplayParentFolder](#displayparentfolder)|Zeigt eine Liste von Elementen, die im Ordner enthalten sind, die das übergeordnete Element des aktuell angezeigten Ordners ist.|  
|[CMFCShellListCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellListCtrl::GetCurrentFolder](#getcurrentfolder)|Ruft den Pfad des aktuellen Ordners ab.|  
|[CMFCShellListCtrl::GetCurrentFolderName](#getcurrentfoldername)|Ruft den Namen des aktuellen Ordners.|  
|[CMFCShellListCtrl::GetCurrentItemIdList](#getcurrentitemidlist)|Gibt die PIDL von dem aktuellen Listenelement-Steuerelement zurück.|  
|[CMFCShellListCtrl::GetCurrentShellFolder](#getcurrentshellfolder)|Gibt einen Zeiger auf die aktuelle Shellordner zurück.|  
|[CMFCShellListCtrl::GetItemPath](#getitempath)|Gibt den Text Pfad eines Elements zurück.|  
|[CMFCShellListCtrl::GetItemTypes](#getitemtypes)|Gibt die Shell work Item Types, die durch das Strukturelement-Steuerelement angezeigt werden.|  
|[CMFCShellListCtrl::IsDesktop](#isdesktop)|Überprüft, ob der aktuell ausgewählte Ordner Ordners "desktop" ist.|  
|[CMFCShellListCtrl::OnCompareItems](#oncompareitems)|Das Framework ruft diese Methode auf, wenn es sich um zwei Elemente vergleicht. (Überschreibt [CMFCListCtrl::OnCompareItems](../../mfc/reference/cmfclistctrl-class.md#oncompareitems).)|  
|[CMFCShellListCtrl::OnFormatFileDate](#onformatfiledate)|Wird aufgerufen, wenn das Framework Ruft das Datum angezeigt, indem das Strukturelement-Steuerelement ab.|  
|[CMFCShellListCtrl::OnFormatFileSize](#onformatfilesize)|Wird aufgerufen, wenn das Framework die Dateigröße eines Listensteuerelements konvertiert.|  
|[CMFCShellListCtrl::OnGetItemIcon](#ongetitemicon)|Wird aufgerufen, wenn das Framework Ruft das Symbol eines Listenelement-Steuerelement ab.|  
|[CMFCShellListCtrl::OnGetItemText](#ongetitemtext)|Wird aufgerufen, wenn das Framework den Text eines Listenelement-Steuerelement konvertiert.|  
|[CMFCShellListCtrl::OnSetColumns](#onsetcolumns)|Vom Framework aufgerufen, wenn sie den Namen der Spalten festlegt.|  
|[CMFCShellListCtrl::Refresh](#refresh)|Wird aktualisiert, und aktualisiert das Strukturelement-Steuerelement.|  
|[CMFCShellListCtrl::SetItemTypes](#setitemtypes)|Legt den Typ der Elemente, die durch das Strukturelement-Steuerelement angezeigt.|  
  
## <a name="remarks"></a>Hinweise  
 Die `CMFCShellListCtrl` Klasse erweitert die Funktionalität von der [CMFCListCtrl Klasse](../../mfc/reference/cmfclistctrl-class.md) durch Aktivieren des Programms Windows Shell Elemente auflisten. Das Anzeigeformat, das verwendet wird, ist wie eine Listenansicht für ein Explorer-Fenster.  
  
 Ein [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt zugeordnet werden kann ein `CMFCShellListCtrl` Objekt beim Erstellen eines vollständigen Explorer-Fensters. Klicken Sie dann, Auswählen eines Elements in der `CMFCShellTreeCtrl` führt dazu, dass die `CMFCShellListCtrl` Objekt, das der Inhalt des ausgewählten Elements aufgelistet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Objekt von der `CMFCShellListCtrl` Klasse und wie den übergeordnete Ordner des aktuell angezeigten Ordner angezeigt. Dieser Codeausschnitt ist Teil der [Explorer (Beispiel)](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#1](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#2](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_2.cpp)]  
[!code-cpp[NVC_MFC_Explorer#3](../../mfc/reference/codesnippet/cpp/cmfcshelllistctrl-class_3.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListCtrl](../../mfc/reference/clistctrl-class.md)  
  
 [CMFCListCtrl](../../mfc/reference/cmfclistctrl-class.md)  
  
 `CMFCShellListCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshelllistCtrl.h  
  
##  <a name="displayfolder"></a>  CMFCShellListCtrl::DisplayFolder  
 Zeigt eine Liste von Elementen, die im angegebenen Ordner enthalten sind.  
  
```  
virtual HRESULT DisplayFolder(LPCTSTR lpszPath);
virtual HRESULT DisplayFolder(LPAFX_SHELLITEMINFO lpItemInfo);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPath`  
 Eine Zeichenfolge, die den Pfad eines Ordners enthält.  
  
 [in] `lpItemInfo`  
 Ein Zeiger auf eine `LPAFX_SHELLITEMINFO` -Struktur, die beschreibt, einen Ordner anzeigen.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK` Bei Erfolg; `E_FAIL` andernfalls.  
  
##  <a name="displayparentfolder"></a>  CMFCShellListCtrl::DisplayParentFolder  
 Updates der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt, das den übergeordneten Ordner der aktuell angezeigten Ordner anzuzeigen.  
  
```  
virtual HRESULT DisplayParentFolder();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK` Bei Erfolg; `E_FAIL` andernfalls.  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellListCtrl::EnableShellContextMenu  
 Ermöglicht das Kontextmenü an.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob das Framework das Kontextmenü aktiviert.  
  
##  <a name="getcurrentfolder"></a>  CMFCShellListCtrl::GetCurrentFolder  
 Ruft den Pfad des derzeit ausgewählten Ordners in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
BOOL GetCurrentFolder(CString& strPath) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strPath`  
 Ein Verweis auf einen Zeichenfolgenparameter, an die Methode den Pfad schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn es kein Ordner im ausgewählten ist der `CMFCShellListCtrl`.  
  
##  <a name="getcurrentfoldername"></a>  CMFCShellListCtrl::GetCurrentFolderName  
 Ruft den Namen des gerade ausgewählten Ordners in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
BOOL GetCurrentFolderName(CString& strName) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strName`  
 Ein Verweis auf einen Zeichenfolgenparameter, an die Methode den Namen schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn es kein Ordner im ausgewählten ist der `CMFCShellListCtrl`.  
  
##  <a name="getcurrentitemidlist"></a>  CMFCShellListCtrl::GetCurrentItemIdList  
 Gibt die PIDL des derzeit ausgewählten Elements zurück.  
  
```  
LPITEMIDLIST GetCurrentItemIdList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die PIDL des aktuellen Elements.  
  
##  <a name="getcurrentshellfolder"></a>  CMFCShellListCtrl::GetCurrentShellFolder  
 Ruft einen Zeiger auf das aktuell ausgewählte Element in der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
const IShellFolder* GetCurrentShellFolder() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die [IShellFolder Schnittstelle](http://msdn.microsoft.com/library/windows/desktop/bb775075) für das ausgewählte Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode gibt `NULL` Wenn derzeit kein Objekt ausgewählt ist.  
  
##  <a name="getitempath"></a>  CMFCShellListCtrl::GetItemPath  
 Ruft den Pfad für ein Element ab.  
  
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
 `TRUE` Bei Erfolg; `FALSE` andernfalls.  
  
### <a name="remarks"></a>Hinweise  
 Der Index von bereitgestellten `iItem` basiert auf der derzeit vom angezeigten Elemente die [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
##  <a name="getitemtypes"></a>  CMFCShellListCtrl::GetItemTypes  
 Gibt den Typ der Elemente angezeigt, indem die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
SHCONTF GetItemTypes() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539) -Wert, der den Typ der aufgeführten enthält die `CMFCShellListCtrl`.  
  
### <a name="remarks"></a>Hinweise  
 Beim Festlegen des Typs der Elemente aufgeführt, die einem `CMFCShellListCtrl`, rufen Sie [CMFCShellListCtrl::SetItemTypes](#setitemtypes).  
  
##  <a name="isdesktop"></a>  CMFCShellListCtrl::IsDesktop  
 Bestimmt, ob der Ordner ist, die angezeigt wird, der [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt ist der Ordner "desktop".  
  
```  
BOOL IsDesktop() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE` Wenn die angezeigte Ordner den Ordner "desktop" ist. `FALSE` andernfalls.  
  
##  <a name="oncompareitems"></a>  CMFCShellListCtrl::OnCompareItems  
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
  
##  <a name="onformatfiledate"></a>  CMFCShellListCtrl::OnFormatFileDate  
 Das Framework ruft diese Methode auf, wenn sie das Datum, die einem Objekt zugeordnet sind, in eine Zeichenfolge konvertieren muss.  
  
```  
virtual void OnFormatFileDate(
    const CTime& tmFile,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `tmFile`  
 Das Datum, an einer Datei zugeordnet.  
  
 [out] `str`  
 Eine Zeichenfolge, die das formatierte Datum enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt zeigt das Datum, die einer Datei zugeordnet, es muss dieses Datum ein Zeichenfolgenformat zu konvertieren. Die `CMFCShellListCtrl` verwendet diese Methode, dass die Konvertierung zu vornehmen. Standardmäßig verwendet diese Methode das aktuelle Gebietsschema zum Formatieren des Datums in eine Zeichenfolge.  
  
##  <a name="onformatfilesize"></a>  CMFCShellListCtrl::OnFormatFileSize  
 Das Framework ruft diese Methode auf, wenn die Größe eines Objekts in eine Zeichenfolge konvertiert werden.  
  
```  
virtual void OnFormatFileSize(
    long lFileSize,  
    CString& str);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lFileSize`  
 Die Größe der Datei, die das Framework angezeigt werden.  
  
 [out] `str`  
 Eine Zeichenfolge, die die formatierte Dateigröße enthält.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt benötigt, um die Größe einer Datei anzuzeigen, müssen die Dateigröße in ein Zeichenfolgenformat zu konvertieren. Die `CMFCShellListCtrl` verwendet diese Methode, dass die Konvertierung zu vornehmen. Standardmäßig wird diese Methode konvertiert die Dateigröße in Bytes Kilobyte und klicken Sie dann so formatieren Sie die Größe in der Zeichenfolge verwendet das aktuelle Gebietsschema.  
  
##  <a name="ongetitemicon"></a>  CMFCShellListCtrl::OnGetItemIcon  
 Das Framework ruft diese Methode, um ein Shell-Listenelement zugeordnete Symbol abzurufen.  
  
```  
virtual int OnGetItemIcon(
    int iItem,  
    LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `iItem`  
 Der Index des Elements.  
  
 [in] `pItem`  
 Ein `LPAFX_SHELLITEMINFO` Parameter, der das Element beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Index des Bilds Symbol "bei Erfolg; -1, wenn die Funktion fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Das Symbol "Abbildindex basiert auf die Systembildliste.  
  
 Standardmäßig verwendet diese Methode auf die `pItem` Parameter. Der Wert des `iItem` wird nicht in der Standardimplementierung verwendet. Sie können `iItem` , benutzerdefiniertes Verhalten zu implementieren.  
  
##  <a name="ongetitemtext"></a>  CMFCShellListCtrl::OnGetItemText  
 Das Framework ruft diese Methode auf, wenn sie den Text ein Shellelement abrufen muss.  
  
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
 Der betreffenden Spalte.  
  
 [in] `pItem`  
 Ein `LPAFX_SHELLITEMINFO` Parameter, der das Element beschreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , die dem Element zugeordneten Text enthält.  
  
### <a name="remarks"></a>Hinweise  
 Jedes Element in der `CMFCShellListCtrl` Objekt kann Text in einer oder mehreren Spalten enthalten. Wenn das Framework über diese Methode aufruft, wird die Spalte, der von Interesse sind. Wenn Sie diese Funktion manuell aufrufen, müssen Sie auch die Spalte angeben, der Sie interessiert sind.  
  
 Standardmäßig verwendet diese Methode auf die `pItem` Parameter zu bestimmen, die den Prozess Element. Der Wert des `iItem` wird nicht in der Standardimplementierung verwendet.  
  
##  <a name="onsetcolumns"></a>  CMFCShellListCtrl::OnSetColumns  
 Das Framework ruft diese Methode auf, wenn er festlegt, dass die Namen der Spalten.  
  
```  
virtual void OnSetColumns();
```  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig erstellt das Framework vier Spalten in einem `CMFCShellListCtrl` Objekt. Die Namen dieser Spalten sind `Name`, `Size`, `Type`, und `Modified`. Sie können diese Methode, um die Anzahl der Spalten und deren Namen anpassen überschreiben.  
  
##  <a name="refresh"></a>  CMFCShellListCtrl::Refresh  
 Aktualisiert und aktualisiert die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
virtual HRESULT Refresh();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK` Bei Erfolg; andernfalls einen Fehler zurück.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktualisieren der Liste der Elemente angezeigt, indem die `CMFCShellListCtrl` Objekt.  
  
##  <a name="setitemtypes"></a>  CMFCShellListCtrl::SetItemTypes  
 Legt den Typ der Elemente, die in aufgeführt sind die [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt.  
  
```  
void SetItemTypes(SHCONTF nTypes);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nTypes`  
 Eine Liste der Typen, die die `CMFCShellListCtrl` -Objekt unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Liste der work Item Types, finden Sie unter [SHCONTF](http://msdn.microsoft.com/library/windows/desktop/bb762539).  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CMFCListCtrl-Klasse](../../mfc/reference/cmfclistctrl-class.md)   
 [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md)
