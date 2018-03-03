---
title: CShellManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CShellManager
- AFXSHELLMANAGER/CShellManager
- AFXSHELLMANAGER/CShellManager::CShellManager
- AFXSHELLMANAGER/CShellManager::BrowseForFolder
- AFXSHELLMANAGER/CShellManager::ConcatenateItem
- AFXSHELLMANAGER/CShellManager::CopyItem
- AFXSHELLMANAGER/CShellManager::CreateItem
- AFXSHELLMANAGER/CShellManager::FreeItem
- AFXSHELLMANAGER/CShellManager::GetItemCount
- AFXSHELLMANAGER/CShellManager::GetItemSize
- AFXSHELLMANAGER/CShellManager::GetNextItem
- AFXSHELLMANAGER/CShellManager::GetParentItem
- AFXSHELLMANAGER/CShellManager::ItemFromPath
dev_langs:
- C++
helpviewer_keywords:
- CShellManager [MFC], CShellManager
- CShellManager [MFC], BrowseForFolder
- CShellManager [MFC], ConcatenateItem
- CShellManager [MFC], CopyItem
- CShellManager [MFC], CreateItem
- CShellManager [MFC], FreeItem
- CShellManager [MFC], GetItemCount
- CShellManager [MFC], GetItemSize
- CShellManager [MFC], GetNextItem
- CShellManager [MFC], GetParentItem
- CShellManager [MFC], ItemFromPath
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1e3fcff06b2937df8218ce1ab32b91ddf22a7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cshellmanager-class"></a>CShellManager-Klasse
Implementiert mehrere Möglichkeiten für die Verwendung von Zeigern auf Bezeichnerlisten (PIDLs).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Erstellt ein `CShellManager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Zeigt ein Dialogfeld, das dem Benutzer ermöglicht, einen Shellordner auswählen.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Verkettet zwei PIDLs an.|  
|[CShellManager::CopyItem](#copyitem)|Erstellt eine neue PIDL und kopiert die angegebenen PIDL darauf.|  
|[CShellManager::CreateItem](#createitem)|Erstellt eine neue PIDL der angegebenen Größe.|  
|[CShellManager::FreeItem](#freeitem)|Löscht die angegebene PIDL an.|  
|[CShellManager::GetItemCount](#getitemcount)|Gibt die Anzahl der Elemente in der angegebenen PIDL zurück.|  
|[CShellManager::GetItemSize](#getitemsize)|Gibt die Größe des bereitgestellten PIDL zurück.|  
|[CShellManager::GetNextItem](#getnextitem)|Gibt das nächste Element aus der PIDL zurück.|  
|[CShellManager::GetParentItem](#getparentitem)|Ruft das übergeordnete Element des angegebenen Elements ab.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Ruft die PIDL für das Element mit dem angegebenen Pfad identifiziert.|  
  
## <a name="remarks"></a>Hinweise  
 Die Methoden der `CShellManager` -Klasse PIDLs alle behandeln. Eine PIDL ist ein eindeutiger Bezeichner für ein Shellobjekt.  
  
 Sie sollten keine erstellen eine `CShellManager` Objekt manuell. Es wird automatisch durch das Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers auf dem Manager Shell für Ihre Anwendung [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 Zeigt ein Dialogfeld, das dem Benutzer ermöglicht, einen Shellordner auswählen.  
  
```  
BOOL BrowseForFolder(
    CString& strOutFolder,  
    CWnd* pWndParent = NULL,  
    LPCTSTR lplszInitialFolder = NULL,  
    LPCTSTR lpszTitle = NULL,  
    UINT ulFlags = BIF_RETURNONLYFSDIRS,  
    LPINT piFolderImage = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [out] `strOutFolder`  
 Die Zeichenfolge, die von der Methode zum Speichern des Pfades des ausgewählten Ordners verwendet wird.  
  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `lplszInitialFolder`  
 Eine Zeichenfolge, die den Ordner enthält, der standardmäßig ausgewählt ist, wenn das Dialogfeld angezeigt wird.  
  
 [in] `lpszTitle`  
 Der Titel für das Dialogfeld.  
  
 [in] `ulFlags`  
 Flags, die angeben von Optionen für das Dialogfeld. Finden Sie unter [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) für die detaillierte Beschreibung.  
  
 [out] `piFolderImage`  
 Ein Zeiger auf den ganzzahligen Wert, an die Methode den Bildindex des ausgewählten Ordners schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer einen Ordner aus dem Dialogfeld auswählt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode aufrufen, wird die Anwendung erstellt und zeigt ein Dialogfeld, das dem Benutzer ermöglicht, einen Ordner auszuwählen. Die Methode schreibt den Pfad des Ordners in der `strOutFolder` Parameter.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie einen Verweis zum Abrufen einer `CShellManager` Objekt mithilfe der `CWinAppEx::GetShellManager` -Methode sowie zum Verwenden der `BrowseForFolder` Methode. Dieser Codeausschnitt ist Teil der [Explorer (Beispiel)](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>CShellManager::ConcatenateItem  
 Erstellt eine neue Liste mit zwei PIDLs.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl1`  
 Das erste Element.  
  
 [in] `pidl2`  
 Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue Elementliste, wenn die Funktion erfolgreich, andernfalls ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt ein neues [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) groß genug für beide `pidl1` und `pidl2`. Kopiert dann `pidl1` und `pidl2` in die neue Liste.  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 Kopiert eine Elementliste an.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidlSource`  
 Die ursprüngliche Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Elementliste im Erfolgsfall; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Die neu erstellte Elementliste hat die gleiche Größe wie der Quellliste Element aus.  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 Erstellt eine neue PIDL an.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `cbSize`  
 Die Größe der Liste mit Elementen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die erstellte Elementliste im Erfolgsfall; andernfalls `NULL`.  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 Erstellt ein `CShellManager`-Objekt.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen Sie keine zum Erstellen einer `CShellManager` direkt. Standardmäßig erstellt das Framework einer für Sie. Um einen Zeiger auf die `CShellManager`, rufen Sie [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Wenn Sie erstellen eine `CShellManager` manuell müssen initialisieren Sie diesen mit der Methode [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 Löscht eine Elementliste an.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Eine Liste zu löschen.  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 Gibt die Anzahl der Elemente in der Liste ein Element zurück.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Ein Zeiger auf eine Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Elementliste.  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 Gibt die Größe der Liste ein Element zurück.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Ein Zeiger auf eine Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Liste mit Elementen.  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 Ruft das nächste Element von einem Zeiger auf eine Liste der Bezeichner (PIDL) ab.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Die Liste der Elemente durchlaufen werden kann.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Element in der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Wenn in der Liste keine Elemente mehr vorhanden sind, gibt diese Methode `NULL`.  
  
##  <a name="getparentitem"></a>CShellManager::GetParentItem  
 Ruft das übergeordnete Element eines Zeigers auf eine Liste der Bezeichner (PIDL) ab.  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpidl`  
 Ein PIDL, dessen übergeordnetes Objekt abgerufen wird.  
  
 [out] `lpidlParent`  
 Ein Verweis auf eine PIDL, in dem die Methode das Ergebnis gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ebene des übergeordneten Elements PIDL.  
  
### <a name="remarks"></a>Hinweise  
 Das Maß an einem PIDL ist relativ zu dem Desktop. Der desktop PIDL gilt eine Ebene 0 haben.  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 Ruft ab den Zeiger auf eine Liste der Bezeichner (PIDL) aus dem Element, das von einem zeichenfolgepfad identifiziert.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszPath`  
 Eine Zeichenfolge, die den Pfad für das Element angibt.  
  
 [out] `pidl`  
 Ein Verweis auf eine PIDL. Die Methode verwendet diese PIDL zum Speichern des Zeigers auf den Rückgabewert.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt `NOERROR` Wenn erfolgreich, ein Fehlerwert mit OLE definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
