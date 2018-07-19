---
title: CMFCShellTreeCtrl-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::EnableShellContextMenu
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetItemPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::GetRelatedList
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnChildNotify
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemIcon
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::OnGetItemText
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::Refresh
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SelectPath
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetFlags
- AFXSHELLTREECTRL/CMFCShellTreeCtrl::SetRelatedList
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellTreeCtrl [MFC], EnableShellContextMenu
- CMFCShellTreeCtrl [MFC], GetFlags
- CMFCShellTreeCtrl [MFC], GetItemPath
- CMFCShellTreeCtrl [MFC], GetRelatedList
- CMFCShellTreeCtrl [MFC], OnChildNotify
- CMFCShellTreeCtrl [MFC], OnGetItemIcon
- CMFCShellTreeCtrl [MFC], OnGetItemText
- CMFCShellTreeCtrl [MFC], Refresh
- CMFCShellTreeCtrl [MFC], SelectPath
- CMFCShellTreeCtrl [MFC], SetFlags
- CMFCShellTreeCtrl [MFC], SetRelatedList
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c0508f0042f63441b3a9bdf66cd29ca0a9a73e6
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/05/2018
ms.locfileid: "37849801"
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl-Klasse
Die `CMFCShellTreeCtrl` -Klasse erweitert [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md) Funktionalität durch eine Hierarchie von shellelementen anzeigen.  

 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]    
## <a name="syntax"></a>Syntax  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Gibt eine Kombination von Flags, die übergeben werden [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Ruft den Pfad zu einem Element.|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Gibt einen Zeiger auf die [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das verwendet wird, zusammen mit dieser `CMFCShellTreeCtrl` Objekt zum Erstellen einer Explorer-ähnlichen-Fensters.|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Diese Memberfunktion wird von diesem Fenster des übergeordneten Fensters aufgerufen, wenn sie eine Meldung empfängt, die auf dieses Fenster bezieht. (Überschreibt [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|Aktualisiert und neu aufgebaut, das aktuelle `CMFCShellTreeCtrl` Objekt.|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Wählt die entsprechende Struktur-Steuerelement ein Element auf einer angegebenen PIDL oder Zeichenfolgenpfad basiert.|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Legt die Flags, die den Kontext für die Struktur zu filtern (ähnlich wie die Flags, die von verwendet `IShellFolder::EnumObjects`).|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Legt eine Beziehung zwischen dem aktuellen `CMFCShellTreeCtrl` Objekt und ein `CMFCShellListCtrl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erweitert die `CTreeCtrl` Klasse aktivieren Sie das Programm Windows-Shell-Elemente in der Struktur enthalten. Diese Klasse zugeordnet sein kann eine `CMFCShellListCtrl` Objekt, das eine vollständige Explorerfenster zu erstellen. Anschließend wird das Auswählen eines Elements in der Struktur eine Liste der Windows-Shell-Elemente in der Liste anzeigen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshelltreeCtrl.h  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CMFCShellTreeCtrl`-Klasse erstellt wird. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>  CMFCShellTreeCtrl::EnableShellContextMenu  
 Können das Kontextmenü an.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *bAktivieren*  
 Ein boolescher Wert, der angibt, ob das Kontextmenü zu aktivieren.  
  
##  <a name="getflags"></a>  CMFCShellTreeCtrl::GetFlags  
 Gibt die Flags legen Sie für die [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Legen Sie ein DWORD-Wert, der angibt, die Kombination von Flags aktuell.  
  
### <a name="remarks"></a>Hinweise  
 Die Flags legen Sie in der `CMFCShellTreeCtrl` gesendet werden, an die Methode [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) jedes Mal, wenn das Objekt aktualisiert wird. Sie können ändern, dass die Flags, mit der [CMFCShellTreeCtrl::SetFlags](#setflags) Methode.  
  
##  <a name="getitempath"></a>  CMFCShellTreeCtrl::GetItemPath  
 Ruft den Pfad eines Elements in der [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] *StrPath*  
 Ein Verweis auf einen Zeichenfolgenparameter. Die Methode schreibt den Pfad des Elements an diesen Parameter an.  
  
 [in] *HtreeItem*  
 Die Methode ruft den Pfad für dieses Strukturelement-Steuerelement ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL Wenn erfolgreich; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode schlägt fehl, *StrPath* enthält die leere Zeichenfolge.  
  
 Wenn Sie keinen angeben *hTreeItem*, versucht diese Methode, die die Zeichenfolge für das aktuell ausgewählte Element abzurufen. Wenn kein Element ausgewählt ist und *hTreeItem* NULL ist, diese Methode schlägt fehl.  
  
##  <a name="getrelatedlist"></a>  CMFCShellTreeCtrl::GetRelatedList  
 Gibt einen Zeiger auf die [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das mit dieser verknüpft ist [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CMFCShellListCtrl` -Objekt, das dieses Steuerelement Tree-Objekt zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe einer `CMFCShellListCtrl` -Objekt zusammen mit einer `CMFCShellTreeCtrl` Objekt ist, können Sie eine ähnlich wie in Explorer-Fenster erstellen. Verwenden Sie die Methode [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) die beiden Klassen zuordnen. Nachdem sie zugeordnet sind, aktualisiert das Framework automatisch die `CMFCShellListCtrl` Wenn die Auswahl in der `CMFCShellTreeCtrl` Änderungen.  
  
##  <a name="onchildnotify"></a>  CMFCShellTreeCtrl::OnChildNotify  

  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pLResult);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *Nachricht*  
 [in] *wParam-Parameter*  
 [in] *lParam*  
 [in] *pLResult*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongetitemicon"></a>  CMFCShellTreeCtrl::OnGetItemIcon  

  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pItem*  
 [in] *bSelected*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongetitemtext"></a>  CMFCShellTreeCtrl::OnGetItemText  

  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pItem*  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="refresh"></a>  CMFCShellTreeCtrl::Refresh  
 Aktualisiert und neu aufgebaut, die [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktualisieren der Hierarchie der Elemente angezeigt, der `CMFCShellTreeCtrl`.  
  
##  <a name="selectpath"></a>  CMFCShellTreeCtrl::SelectPath  
 Wählt ein Element in der [CMFCShellTreeCtrl-Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) basierend auf dem angegebenen Pfad.  
  
```  
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *LpszPath*  
 Eine Zeichenfolge, die den Pfad eines Elements angibt.  
  
 [in] *Lpidl*  
 Eine PIDL, der das Element angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; E_FAIL andernfalls.  
  
##  <a name="setflags"></a>  CMFCShellTreeCtrl::SetFlags  
 Legt die Flags, die den Kontext für die Struktur zu filtern.  
  
```  
void SetFlags(
    DWORD dwFlags,  
    BOOL bRefresh = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *DwFlags*  
 Die festzulegenden Flags.  
  
 [in] *bRefresh*  
 Ein boolescher Wert, der angibt, ob die `CMFCShellTreeCtrl` sofort aktualisiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCShellTreeCtrl` übergibt alle Flags, um festlegen [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Weitere Informationen zu den Werten der verschiedenen Kennzeichnungen, finden Sie unter [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>  CMFCShellTreeCtrl::SetRelatedList  
 Ordnet eine [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) Objekt mit einem [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] *pShellList*  
 Ein Zeiger auf eine `CMFCShellListCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet eine `CMFCShellListCtrl` mit einem `CMFCShellTreeCtrl`. Diese Objekte können als ein ähnlich wie in Explorer-Fenster angezeigt werden: klickt der Benutzer ein Objekt in der `CMFCShellTreeCtrl`, die verknüpften Elemente in der `CMFCShellListCtrl` automatisch aktualisiert.  
  
 Verwenden Sie die Methode [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) zum Abrufen der `CMFCShellListCtrl` zugeordneten eine `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md)
