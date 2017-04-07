---
title: Klasse CShellManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- CShellManager class
ms.assetid: f15c4c1a-6fae-487d-9913-9b7369b33da0
caps.latest.revision: 23
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 2bf6be5c0d106344024d32e90cc6cfb1e3299075
ms.lasthandoff: 02/24/2017

---
# <a name="cshellmanager-class"></a>CShellManager-Klasse
Implementiert mehrere Möglichkeiten für die Verwendung von Zeigern auf Bezeichnerlisten (PIDLs).  
  
## <a name="syntax"></a>Syntax  
  
```  
class CShellManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CShellManager::CShellManager](#cshellmanager)|Erstellt ein `CShellManager`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CShellManager::BrowseForFolder](#browseforfolder)|Zeigt ein Dialogfeld, mit dem den Benutzer einen Shell-Ordner auswählen kann.|  
|[CShellManager::ConcatenateItem](#concatenateitem)|Verkettet zwei PIDLs.|  
|[CShellManager::CopyItem](#copyitem)|Erstellt eine neue PIDL und kopiert die angegebenen PIDL zu.|  
|[CShellManager::CreateItem](#createitem)|Erstellt eine neue PIDL mit der angegebenen Größe.|  
|[CShellManager::FreeItem](#freeitem)|Löscht den angegebenen PIDL.|  
|[CShellManager::GetItemCount](#getitemcount)|Gibt die Anzahl der Elemente in der angegebenen PIDL zurück.|  
|[CShellManager::GetItemSize](#getitemsize)|Gibt die Größe der angegebenen PIDL zurück.|  
|[CShellManager::GetNextItem](#getnextitem)|Gibt das nächste Element aus der PIDL zurück.|  
|[CShellManager::GetParentItem](#getparentitem)|Ruft das übergeordnete Element des angegebenen Elements ab.|  
|[CShellManager::ItemFromPath](#itemfrompath)|Ruft die PIDL für das Element mit dem angegebenen Pfad identifiziert.|  
  
## <a name="remarks"></a>Hinweise  
 Die Methoden der `CShellManager` -Klasse alle PIDLs behandeln. Ein PIDL ist ein eindeutiger Bezeichner für ein Shellobjekt.  
  
 Erstellen Sie keine `CShellManager` Objekt manuell. Es wird automatisch vom Framework der Anwendung erstellt werden. Sie sollten jedoch aufrufen [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers an dem Shell-Manager für Ihre Anwendung [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 [CShellManager](../../mfc/reference/cshellmanager-class.md)  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxshellmanager.h  
  
##  <a name="browseforfolder"></a>CShellManager::BrowseForFolder  
 Zeigt ein Dialogfeld, mit dem den Benutzer einen Shell-Ordner auswählen kann.  
  
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
 Die Zeichenfolge, die von der Methode verwendet wird, um den Pfad des ausgewählten Ordners zu speichern.  
  
 [in] `pWndParent`  
 Ein Zeiger auf das übergeordnete Fenster.  
  
 [in] `lplszInitialFolder`  
 Eine Zeichenfolge, die den Ordner enthält, der standardmäßig aktiviert ist, wenn das Dialogfeld angezeigt wird.  
  
 [in] `lpszTitle`  
 Der Titel für das Dialogfeld.  
  
 [in] `ulFlags`  
 Flags, die Optionen für das Dialogfeld. Finden Sie unter [BROWSEINFO](http://msdn.microsoft.com/library/windows/desktop/bb773205) für die detaillierte Beschreibung.  
  
 [out] `piFolderImage`  
 Ein Zeiger auf die ganze Zahl, in denen die Methode den Index des Bildes des ausgewählten Ordners schreibt.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Benutzer einen Ordner aus dem Dialogfeld auswählt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie diese Methode aufrufen, wird die Anwendung erstellt und zeigt ein Dialogfeld, das dem Benutzer ermöglicht, einen Ordner auszuwählen. Die Methode schreibt den Pfad des Ordners, in dem `strOutFolder` Parameter.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie zum Abrufen eines Verweises auf eine `CShellManager` -Objekt unter Verwendung der `CWinAppEx::GetShellManager` -Methode und zum Verwenden der `BrowseForFolder` Methode. Dieser Codeausschnitt ist Teil der [Explorer-Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_Explorer&6;](../../mfc/reference/codesnippet/cpp/cshellmanager-class_1.cpp)]  
  
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
 Ein Zeiger auf die neuen Elementliste, wenn die Funktion erfolgreich, andernfalls ist `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode erstellt ein neues [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) groß genug für beide `pidl1` und `pidl2`. Kopiert dann `pidl1` und `pidl2` in die neue Liste.  
  
##  <a name="copyitem"></a>CShellManager::CopyItem  
 Kopiert eine Elementliste an.  
  
```  
LPITEMIDLIST CopyItem(LPCITEMIDLIST pidlSource);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidlSource`  
 Der ursprüngliche Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf die neu erstellte Element-Liste, wenn erfolgreich; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Die neu erstellten Liste hat die gleiche Größe wie der Quellliste-Element.  
  
##  <a name="createitem"></a>CShellManager::CreateItem  
 Erstellt eine neue PIDL.  
  
```  
LPITEMIDLIST CreateItem(UINT cbSize);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `cbSize`  
 Die Größe der Elementliste.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf das erstellte Element-Liste, wenn erfolgreich; andernfalls `NULL`.  
  
##  <a name="cshellmanager"></a>CShellManager::CShellManager  
 Erstellt ein `CShellManager`-Objekt.  
  
```  
CShellManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen Sie müssen nicht zum Erstellen einer `CShellManager` direkt. Standardmäßig erstellt das Framework für Sie. Um einen Zeiger auf die `CShellManager`, rufen Sie [CWinAppEx::GetShellManager](../../mfc/reference/cwinappex-class.md#getshellmanager). Wenn Sie erstellen ein `CShellManager` manuell müssen initialisieren Sie diesen mit der Methode [CWinAppEx::InitShellManager](../../mfc/reference/cwinappex-class.md#initshellmanager).  
  
##  <a name="freeitem"></a>CShellManager::FreeItem  
 Löscht eine Elementliste an.  
  
```  
void FreeItem(LPITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Eine Liste zu löschen.  
  
##  <a name="getitemcount"></a>CShellManager::GetItemCount  
 Gibt die Anzahl der Elemente in einer Liste zurück.  
  
```  
UINT GetItemCount(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Ein Zeiger auf eine Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in der Elementliste.  
  
##  <a name="getitemsize"></a>CShellManager::GetItemSize  
 Gibt die Größe einer Liste mit Elementen zurück.  
  
```  
UINT GetItemSize(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Ein Zeiger auf eine Liste.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Größe der Elementliste.  
  
##  <a name="getnextitem"></a>CShellManager::GetNextItem  
 Ruft das nächste Element von einem Zeiger auf eine Liste der Bezeichner (PIDL) ab.  
  
```  
LPITEMIDLIST GetNextItem(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `pidl`  
 Die Liste der Elemente durchlaufen.  
  
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
 Ein PIDL, dessen übergeordnetes Element abgerufen wird.  
  
 [out] `lpidlParent`  
 Ein Verweis auf eine PIDL, in dem die Methode das Ergebnis gespeichert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Ebene des übergeordneten PIDL.  
  
### <a name="remarks"></a>Hinweise  
 Die Zugriffsebene einer PIDL ist relativ zum Desktop. Der desktop PIDL gilt eine Ebene 0.  
  
##  <a name="itemfrompath"></a>CShellManager::ItemFromPath  
 Ruft den Zeiger auf eine Liste der Bezeichner (PIDL) aus dem Element, das von einem Zeichenfolgenpfad identifiziert ab.  
  
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
 Gibt `NOERROR` Wenn erfolgreich, ein OLE definierter Fehlerwert.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)

