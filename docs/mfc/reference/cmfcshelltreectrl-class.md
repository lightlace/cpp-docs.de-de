---
title: Klasse CMFCShellTreeCtrl | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- CMFCShellTreeCtrl class
ms.assetid: 3d1da715-9554-4ed7-968c-055c48146267
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
ms.openlocfilehash: cf9c7c3577646895546c443c975a92431194d3f4
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcshelltreectrl-class"></a>CMFCShellTreeCtrl-Klasse
Die `CMFCShellTreeCtrl` Klasse erweitert [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md) Funktionalität, indem Sie eine Hierarchie von shellelementen anzeigen.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMFCShellTreeCtrl : public CTreeCtrl  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMFCShellTreeCtrl::EnableShellContextMenu](#enableshellcontextmenu)|Aktiviert oder deaktiviert das Kontextmenü.|  
|[CMFCShellTreeCtrl::GetFlags](#getflags)|Gibt eine Kombination von Flags, die übergeben werden [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).|  
|[CMFCShellTreeCtrl::GetItemPath](#getitempath)|Ruft den Pfad zu einem Element.|  
|[CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist)|Gibt einen Zeiger auf die [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das zusammen mit dieser verwendet `CMFCShellTreeCtrl` Objekt zum Erstellen einer Explorer-ähnlichen-Fensters.|  
|[CMFCShellTreeCtrl::OnChildNotify](#onchildnotify)|Diese Memberfunktion ist dieses Fenster übergeordnete Fenster aufgerufen, wenn er eine Benachrichtigung empfängt, die in diesem Fenster angewendet wird. (Überschreibt [CWnd:: OnChildNotify](../../mfc/reference/cwnd-class.md#onchildnotify).)|  
|[CMFCShellTreeCtrl::OnGetItemIcon](#ongetitemicon)||  
|[CMFCShellTreeCtrl::OnGetItemText](#ongetitemtext)||  
|[CMFCShellTreeCtrl::Refresh](#refresh)|Wird aktualisiert, und aktualisiert die aktuelle `CMFCShellTreeCtrl` Objekt.|  
|[CMFCShellTreeCtrl::SelectPath](#selectpath)|Wählt die entsprechende Struktur-Steuerelement ein Element basierend auf einer angegebenen PIDL oder Zeichenfolgenpfad.|  
|[CMFCShellTreeCtrl::SetFlags](#setflags)|Flag zum Filtern des Struktur-Kontexts (ähnlich den Flags von `IShellFolder::EnumObjects`).|  
|[CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist)|Legt eine Beziehung zwischen dem aktuellen `CMFCShellTreeCtrl` Objekt und ein `CMFCShellListCtrl` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Diese Klasse erweitert die `CTreeCtrl` Klasse, indem Sie das Programm Windows-Shell-Einträge in der Struktur enthalten. Diese Klasse kann zugeordnet werden ein `CMFCShellListCtrl` Objekt, um eine vollständige Explorer-Fenster zu erstellen. Anschließend wird das Auswählen eines Elements in der Struktur eine Liste der Windows-Shell-Elemente in der zugehörigen Liste anzeigen.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CTreeCtrl](../../mfc/reference/ctreectrl-class.md)  
  
 `CMFCShellTreeCtrl`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshelltreeCtrl.h  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein Objekt der `CMFCShellTreeCtrl`-Klasse erstellt wird. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer&4;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_1.h)]  
[!code-cpp[NVC_MFC_Explorer&5;](../../mfc/reference/codesnippet/cpp/cmfcshelltreectrl-class_2.cpp)]  
  
##  <a name="enableshellcontextmenu"></a>CMFCShellTreeCtrl::EnableShellContextMenu  
 Können das Kontextmenü.  
  
```  
void EnableShellContextMenu(BOOL bEnable = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bEnable`  
 Ein boolescher Wert, der angibt, ob das Kontextmenü zu aktivieren.  
  
##  <a name="getflags"></a>CMFCShellTreeCtrl::GetFlags  
 Gibt die Flags legen Sie für die [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
DWORD GetFlags() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `DWORD` Wert, der derzeit die Kombination von Flags angibt.  
  
### <a name="remarks"></a>Hinweise  
 Die Flags festgelegt, der `CMFCShellTreeCtrl` gesendet werden, an die Methode [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066) jedes Mal, wenn das Objekt aktualisiert wird. Sie können ändern, dass die Flags, mit der [CMFCShellTreeCtrl::SetFlags](#setflags) Methode.  
  
##  <a name="getitempath"></a>CMFCShellTreeCtrl::GetItemPath  
 Ruft den Pfad eines Elements in der [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
BOOL GetItemPath(
    CString& strPath,  
    HTREEITEM htreeItem = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strPath`  
 Ein Verweis auf einen Zeichenfolgenparameter. Die Methode gibt den Pfad des Elements an diesen Parameter.  
  
 [in] `htreeItem`  
 Die Methode ruft den Pfad für dieses Strukturelement-Steuerelement ab.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode fehlschlägt, `strPath` die leere Zeichenfolge enthält.  
  
 Wenn Sie keinen angeben `hTreeItem`, versucht diese Methode, die die Zeichenfolge für das aktuell ausgewählte Element abzurufen. Wenn kein Element ausgewählt ist und `hTreeItem` ist `NULL`, diese Methode schlägt fehl.  
  
##  <a name="getrelatedlist"></a>CMFCShellTreeCtrl::GetRelatedList  
 Gibt einen Zeiger auf die [CMFCShellListCtrl Klasse](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt, das zugeordnet ist [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
CMFCShellListCtrl* GetRelatedList() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die `CMFCShellListCtrl` -Objekt, das dieser Struktur Control-Objekt zugeordnet ist.  
  
### <a name="remarks"></a>Hinweise  
 Mithilfe einer `CMFCShellListCtrl` -Objekt zusammen mit einer `CMFCShellTreeCtrl` -Objekt, können Sie ein Fenster ähnlich wie in Explorer erstellen. Verwenden Sie die Methode [CMFCShellTreeCtrl::SetRelatedList](#setrelatedlist) die beiden Klassen zuordnen. Nachdem sie zugeordnet sind, aktualisiert das Framework automatisch die `CMFCShellListCtrl` Wenn die Auswahl in der `CMFCShellTreeCtrl` ändert.  
  
##  <a name="onchildnotify"></a>CMFCShellTreeCtrl::OnChildNotify  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
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
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual CString OnGetItemText(LPAFX_SHELLITEMINFO pItem);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pItem`  
  
### <a name="return-value"></a>Rückgabewert  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="refresh"></a>CMFCShellTreeCtrl::Refresh  
 Wird aktualisiert, und aktualisiert die [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md).  
  
```  
void Refresh();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Methode zum Aktualisieren der Hierarchie der Elemente der `CMFCShellTreeCtrl`.  
  
##  <a name="selectpath"></a>CMFCShellTreeCtrl::SelectPath  
 Wählt ein Element in der [CMFCShellTreeCtrl Klasse](../../mfc/reference/cmfcshelltreectrl-class.md) basierend auf dem angegebenen Pfad.  
  
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
 Legt die Flags an, die den Kontext der Struktur zu filtern.  
  
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
 Die `CMFCShellTreeCtrl` übergibt alle Flags auf [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066). Weitere Informationen zu den Werten der anderen Flags finden Sie unter [IShellFolder::EnumObjects](http://msdn.microsoft.com/library/windows/desktop/bb775066).  
  
##  <a name="setrelatedlist"></a>CMFCShellTreeCtrl::SetRelatedList  
 Ordnet eine [CMFCShellListCtrl](../../mfc/reference/cmfcshelllistctrl-class.md) -Objekt mit einem [CMFCShellTreeCtrl](../../mfc/reference/cmfcshelltreectrl-class.md) Objekt.  
  
```  
void SetRelatedList(CMFCShellListCtrl* pShellList);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pShellList`  
 Ein Zeiger auf ein `CMFCShellListCtrl` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ordnet eine `CMFCShellListCtrl` mit einem `CMFCShellTreeCtrl`. Diese Objekte können als ein Fenster ähnlich wie in Explorer angezeigt werden: klickt der Benutzer ein Objekt in der `CMFCShellTreeCtrl`, die verknüpften Elemente in der `CMFCShellListCtrl` automatisch aktualisiert.  
  
 Verwenden Sie die Methode [CMFCShellTreeCtrl::GetRelatedList](#getrelatedlist) zum Abrufen der `CMFCShellListCtrl` zugeordneten eine `CMFCShellTreeCtrl`.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CTreeCtrl-Klasse](../../mfc/reference/ctreectrl-class.md)   
 [CMFCShellListCtrl-Klasse](../../mfc/reference/cmfcshelllistctrl-class.md)

