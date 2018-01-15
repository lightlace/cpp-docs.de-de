---
title: CMFCShellTreeCtrl Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
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
dev_langs: C++
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
caps.latest.revision: "30"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 727b0032687ed22692f07f9b5e9e5fe8b2813071
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl-Klasse
Die `CMFCShellTreeCtrl` -Klasse erweitert [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md) Funktionalität durch eine Hierarchie mit shellelementen anzeigen.  

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
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Ruft den Pfad zu einem Element ab.|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Gibt einen Zeiger auf die [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das verwendet wird, zusammen mit dieser `CMFCShellTreeCtrl` Objekt beim Erstellen einer Explorer-ähnlichen-Fensters.|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Diese Memberfunktion wird durch dieses Fenster übergeordnetes Fenster aufgerufen, wenn er eine Meldung empfängt, die für dieses Fenster gilt. (Überschreibt [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|Aktualisiert und aktualisiert das aktuelle `CMFCShellTreeCtrl` Objekt.|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Wählt die entsprechende Struktur-Steuerelement ein Element basierend auf einer angegebenen PIDL oder zeichenfolgepfad an.|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Legt die Flags, um den Kontext der Struktur zu filtern (ähnlich wie die vom verwendeten Flags `IShellFolder::EnumObjects`).|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Legt eine Beziehung zwischen dem aktuellen `CMFCShellTreeCtrl` Objekt und ein `CMFCShellListCtrl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erweitert die `CTreeCtrl` Klasse durch Aktivieren des Programms, Windows-Shell-Elemente in der Struktur enthalten. Diese Klasse kann zugewiesen werden, mit einer `CMFCShellListCtrl` Objekt beim Erstellen eines vollständigen Explorer-Fensters. Auswählen eines Elements in der Struktur anzuzeigen klicken Sie dann eine Liste von Windows-Shell-Elementen in der zugeordneten Liste.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshelltreeCtrl.h  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CMFCShellTreeCtrl`-Klasse erstellt wird. Dieser Codeausschnitt ist Teil der [Explorer (Beispiel)](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#4](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer#5](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl::EnableShellContextMenu  
 Ermöglicht das Kontextmenü an.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob das Kontextmenü aktiviert.  
  
##  <a name="getflags"></a>CMFCShellTreeCtrl::GetFlags  
 Gibt die Flags, legen Sie für die [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der derzeit die Kombination der Flags angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Flags festgelegt, der `CMFCShellTreeCtrl` gesendet werden, an die Methode [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) immer das Objekt aktualisiert wird. Sie können ändern, dass die Flags, mit der [CMFCShellTreeCtrl::SetFlags](#setflags) Methode.  
  
##  <a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath  
 Ruft den Pfad eines Elements in der [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strPath`  
 Ein Verweis auf einen Zeichenfolgenparameter. Die Methode schreibt den Pfad des Elements an diesen Parameter an.  
  
 [in] `htreeItem`  
 Die Methode ruft den Pfad für diese Strukturelement-Steuerelement ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode fehlschlägt, `strPath` die leere Zeichenfolge enthält.  
  
 Wenn Sie keinen angeben `hTreeItem`, diese Methode versucht, die Zeichenfolge für das aktuell ausgewählte Element abzurufen. Wenn kein Element ausgewählt ist und `hTreeItem` ist `NULL`, diese Methode ein Fehler auftritt.  
  
##  <a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList  
 Gibt einen Zeiger auf die [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das mit dieser verknüpft ist [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CMFCShellListCtrl` -Objekt, das diesem Steuerelement-Funktionsstruktur-Objekt zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe einer `CMFCShellListCtrl` -Objekt zusammen mit einem `CMFCShellTreeCtrl` -Objekt, können Sie ein Explorer-ähnliche-Fenster erstellen. Verwenden Sie die Methode [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) die beiden Klassen zuordnen. Nachdem sie zugeordnet sind, aktualisiert das Framework automatisch die `CMFCShellListCtrl` Wenn die Auswahl in der `CMFCShellTreeCtrl` Änderungen.  
  
##  <a name="onchildnotify"></a>CMFCShellTreeCtrl::OnChildNotify  

  
```  
virtual BOOL OnChildNotify(
    UINT message,  
    WPARAM wParam,  
    LPARAM lParam,  
    LRESULT* pLResult);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `message`  
 [in] `wParam`  
 [in] `lParam`  
 [in] `pLResult`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongetitemicon"></a>CMFCShellTreeCtrl::OnGetItemIcon  

  
```  
virtual int OnGetItemIcon(
    LPAFX_SHELLITEMINFO pItem,  
    BOOL bSelected);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pItem`  
 [in] `bSelected`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="ongetitemtext"></a>CMFCShellTreeCtrl::OnGetItemText  

  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pItem`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="refresh"></a>CMFCShellTreeCtrl::Refresh  
 Aktualisiert und aktualisiert die [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktualisieren der Hierarchie der Elemente der `CMFCShellTreeCtrl`.  
  
##  <a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath  
 Wählt ein Element in der [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) auf Grundlage des angegebenen Pfads.  
  
```  
BOOL SelectPath(LPCTSTR lpszPath);
BOOL SelectPath(LPCITEMIDLIST lpidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPath`  
 Eine Zeichenfolge, die den Pfad eines Elements angibt.  
  
 [in] `lpidl`  
 Ein PIDL, der das Element angibt.  
  
### <a name="return-value"></a>Rückgabewert  
 `S_OK`Bei Erfolg; `E_FAIL` andernfalls.  
  
##  <a name="setflags"></a>CMFCShellTreeCtrl::SetFlags  
 Legt die Flags, um den Kontext der Struktur zu filtern.  
  
```  
void SetFlags(
    DWORD dwFlags,  
    BOOL bRefresh = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `dwFlags`  
 Die festzulegenden Flags.  
  
 [in] `bRefresh`  
 Ein boolescher Wert, der angibt, ob die `CMFCShellTreeCtrl` sofort aktualisiert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die `CMFCShellTreeCtrl` übergibt alle Flags, um festlegen [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Weitere Informationen zu den Werten der anderen Flags finden Sie unter [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList  
 Ordnet eine [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt mit einem [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pShellList`  
 Ein Zeiger auf eine `CMFCShellListCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet eine `CMFCShellListCtrl` mit einem `CMFCShellTreeCtrl`. Diese Objekte können als ein Explorer-ähnliche-Fenster angezeigt werden: klickt der Benutzer ein Objekt in der `CMFCShellTreeCtrl`, die verknüpften Elemente in der `CMFCShellListCtrl` automatisch aktualisiert.  
  
 Verwenden Sie die Methode [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) zum Abrufen der `CMFCShellListCtrl` zugeordneten eine `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md)
