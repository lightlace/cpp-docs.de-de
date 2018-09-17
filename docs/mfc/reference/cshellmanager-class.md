---
title: CShellManager-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48312e4840436b1e0cc7c3e176d86f1783ff1746
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714660"
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
|[CShellManager::BrowseForFolder](#browseforfolder)|Zeigt ein Dialogfeld an, die dem Benutzer ermöglicht, einen Shellordner auszuwählen.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Verkettet zwei PIDLs an.|  
|[CShellManager::CopyItem](#copyitem)|Erstellt eine neue PIDL und kopiert die angegebene PIDL dorthin.|  
|[CShellManager::CreateItem](#createitem)|Erstellt eine neue PIDL der angegebenen Größe an.|  
|[CShellManager::FreeItem](#freeitem)|Löscht die angegebene PIDL an.|  
|[CShellManager::GetItemCount](#getitemcount)|Gibt die Anzahl der Elemente in der angegebenen PIDL zurück.|  
|[CShellManager::GetItemSize](#getitemsize)|Gibt die Größe der bereitgestellten PIDL zurück.|  
|[CShellManager::GetNextItem](#getnextitem)|Gibt das nächste Element aus der PIDL zurück.|  
|[CShellManager::GetParentItem](#getparentitem)|Ruft das übergeordnete Element des angegebenen Elements ab.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Ruft ab, der PIDL für das Element, das durch den angegebenen Pfad identifiziert wird.|  
  
## <a name="remarks"></a>Hinweise  
 Die Methoden der `CShellManager` alle viel mit PIDLs Klasse. Eine PIDL ist ein eindeutiger Bezeichner für ein PowerShell-Objekt.  
  
 Erstellen Sie keine `CShellManager` Objekt manuell. Es wird automatisch durch das Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) während der Initialisierung der Anwendung. Um einen Zeiger an dem Shell-Manager für Ihre Anwendung zu erhalten, rufen [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>  CShellManager::BrowseForFolder  
 Zeigt ein Dialogfeld an, die dem Benutzer ermöglicht, einen Shellordner auszuwählen.  
  
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
*strOutFolder*<br/>
[out] Die Zeichenfolge, die von der Methode zum Speichern des Pfads des ausgewählten Ordners verwendet wird.  
  
*pWndParent*<br/>
[in] Ein Zeiger auf das übergeordnete Fenster.  
  
*lplszInitialFolder*<br/>
[in] Eine Zeichenfolge mit dem Ordner, der standardmäßig ausgewählt ist, wenn das Dialogfeld angezeigt wird.  
  
*lpszTitle*<br/>
[in] Der Titel für das Dialogfeld.  
  
*ulFlags*<br/>
[in] Flags, die Optionen für das Dialogfeld angeben. Finden Sie unter [BROWSEINFO](/windows/desktop/api/shlobj_core/ns-shlobj_core-_browseinfoa) für die ausführliche Beschreibung.  
  
*piFolderImage*<br/>
[out] Ein Zeiger auf den ganzzahligen Wert, der die Methode den Bildindex des ausgewählten Ordners schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, wenn der Benutzer einen Ordner aus dem Dialogfeld auswählt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode aufrufen, wird die Anwendung erstellt und zeigt ein Dialogfeld an, die dem Benutzer ermöglicht, einen Ordner auszuwählen. Die Methode schreibt den Pfad des Ordners, in der *StrOutFolder* Parameter.  
  
### <a name="example"></a>Beispiel  
 Im folgende Beispiel wird veranschaulicht, wie zum Abrufen eines Verweises auf eine `CShellManager` -Objekt unter Verwendung der `CWinAppEx::GetShellManager` -Methode und zum Verwenden der `BrowseForFolder` Methode. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer#6](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
##  <a name="concatenateitem"></a>  CShellManager::ConcatenateItem  
 Erstellt eine neue Liste, die zwei PIDLs enthält.  
  
```  
LPITEMIDLIST ConcatenateItem(
    LPCITEMIDLIST pidl1,  
    LPCITEMIDLIST pidl2);
```  
  
### <a name="parameters"></a>Parameter  
*pidl1*<br/>
[in] Das erste Element.  
  
*pidl2*<br/>
[in] Das zweite Element.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neue Elementliste aus, wenn die Funktion erfolgreich ist, andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt ein neues [ITEMIDLIST](/windows/desktop/api/shtypes/ns-shtypes-_itemidlist) groß genug für beide *pidl1* und *pidl2*. Anschließend kopiert *pidl1* und *pidl2* in die neue Liste.  
  
##  <a name="copyitem"></a>  CShellManager::CopyItem  
 Kopiert eine Elementliste an.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parameter  
*pidlSource*<br/>
[in] Der ursprünglichen Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Element-Liste, wenn erfolgreich; andernfalls NULL.  
  
### <a name="remarks"></a>Hinweise  
 Die Liste der neu erstellte Element verfügt über die gleiche Größe wie der Item Quellliste.  
  
##  <a name="createitem"></a>  CShellManager::CreateItem  
 Erstellt eine neue PIDL an.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parameter  
*cbSize*<br/>
[in] Die Größe der Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erstellte Element-Liste, wenn erfolgreich; andernfalls NULL.  
  
##  <a name="cshellmanager"></a>  CShellManager::CShellManager  
 Erstellt ein `CShellManager`-Objekt.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen, Sie müssen keine Erstellung einer `CShellManager` direkt. Standardmäßig erstellt das Framework für Sie. Um einen Zeiger auf die `CShellManager`, rufen Sie [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Wenn Sie erstellen eine `CShellManager` manuell müssen initialisiert es mit der Methode [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>  CShellManager::FreeItem  
 Löscht eine Elementliste an.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
*PIDL*<br/>
[in] Eine Elementliste zu löschen.  
  
##  <a name="getitemcount"></a>  CShellManager::GetItemCount  
 Gibt die Anzahl der Elemente in der Liste ein Element zurück.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
*PIDL*<br/>
[in] Ein Zeiger auf eine Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Elementliste.  
  
##  <a name="getitemsize"></a>  CShellManager::GetItemSize  
 Gibt die Größe der Liste ein Element zurück.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
*PIDL*<br/>
[in] Ein Zeiger auf eine Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Elementliste.  
  
##  <a name="getnextitem"></a>  CShellManager::GetNextItem  
 Ruft das nächste Element von einem Zeiger auf eine Elementliste Bezeichner (PIDL) ab.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
*PIDL*<br/>
[in] Die Liste der Elemente, die durchlaufen werden soll.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das nächste Element in der Liste.  
  
### <a name="remarks"></a>Hinweise  
 Wenn in der Liste keine Elemente mehr vorhanden sind, gibt diese Methode NULL zurück.  
  
##  <a name="getparentitem"></a>  CShellManager::GetParentItem  
 Ruft das übergeordnete Element eines Zeigers auf eine Elementliste Bezeichner (PIDL) ab.  
  
```  
int GetParentItem(
    LPCITEMIDLIST lpidl,  
    LPITEMIDLIST& lpidlParent);
```  
  
### <a name="parameters"></a>Parameter  
*lpidl*<br/>
[in] Eine PIDL, dessen übergeordnetes Element abgerufen werden.  
  
*lpidlParent*<br/>
[out] Ein Verweis auf eine PIDL, in denen die Methode das Ergebnis gespeichert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ebene des übergeordneten Elements PIDL.  
  
### <a name="remarks"></a>Hinweise  
 Die Ebene von einem PIDL ist relativ zum Desktop. Der desktop PIDL gilt ein gewisses Maß an 0.  
  
##  <a name="itemfrompath"></a>  CShellManager::ItemFromPath  
 Ruft die Zeiger auf eine Elementliste Bezeichner (PIDL) ab, aus dem Element, das von einem zeichenfolgepfad identifiziert.  
  
```  
HRESULT ItemFromPath(
    LPCTSTR lpszPath,  
    LPITEMIDLIST& pidl);
```  
  
### <a name="parameters"></a>Parameter  
*lpszPath*<br/>
[in] Eine Zeichenfolge, die den Pfad für das Element angibt.  
  
*PIDL*<br/>
[out] Ein Verweis auf eine PIDL. Die Methode verwendet diesen PIDL zum Speichern des Zeigers auf den Rückgabewert an.  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt "noError" ZURÜCKGEGEBEN, wenn erfolgreich; ein OLE definierter Fehlerwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)
