---
title: Klasse CContextMenuManager | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::CContextMenuManager
- AFXCONTEXTMENUMANAGER/CContextMenuManager::AddMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuById
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuByName
- AFXCONTEXTMENUMANAGER/CContextMenuManager::GetMenuNames
- AFXCONTEXTMENUMANAGER/CContextMenuManager::LoadState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ResetState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SaveState
- AFXCONTEXTMENUMANAGER/CContextMenuManager::SetDontCloseActiveMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::ShowPopupMenu
- AFXCONTEXTMENUMANAGER/CContextMenuManager::TrackPopupMenu
dev_langs:
- C++
helpviewer_keywords:
- CContextMenuManager class
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: 32
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
ms.openlocfilehash: fab322d0c60b33454504620170d9c77a98401ec8
ms.lasthandoff: 02/24/2017

---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager-Klasse
Das `CContextMenuManager` Objekt verwaltet Kontextmenüs, auch bekannt als Kontextmenüs.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Erstellt ein `CContextMenuManager`-Objekt.|  
|`CContextMenuManager::~CContextMenuManager`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Fügt ein neues Kontextmenü.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Gibt ein Handle für das Menü, das die bereitgestellten Ressourcen-ID zugeordnet|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Gibt ein Handle auf das Menü, das den angegebenen Namen entspricht.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Gibt eine Liste von Menünamen.|  
|[CContextMenuManager::LoadState](#loadstate)|Lädt die Kontextmenüs, die in der Windows-Registrierung gespeichert.|  
|[CContextMenuManager::ResetState](#resetstate)|Löscht die Kontextmenüs aus dem Kontext-Menü-Manager.|  
|[CContextMenuManager::SaveState](#savestate)|Kontextmenüs in der Windows-Registrierung gespeichert.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Steuerelemente, ob die `CContextMenuManager` schließt das aktive Kontextmenü, wenn sie ein neues Kontextmenü angezeigt wird.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Zeigt das angegebene Kontextmenü an.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Zeigt das angegebene Kontextmenü an. Gibt den Index des ausgewählten Menübefehls.|  
  
## <a name="remarks"></a>Hinweise  
 `CContextMenuManager`verwaltet Kontextmenüs und stellt sicher, dass sie ein einheitliches Erscheinungsbild.  
  
 Erstellen Sie keine `CContextMenuManager` Objekt manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Sie sollten jedoch aufrufen [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) Wenn Ihre Anwendung initialisiert wird. Nach der Initialisierung des Kontext-Managers, verwenden Sie die Methode [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) um einen Zeiger auf den Kontext-Manager für Ihre Anwendung zu erhalten.  
  
 Sie können Kontextmenüs zur Laufzeit erstellen, durch Aufrufen von `AddMenu`. Wenn Sie das Menü ohne erste empfangenden Benutzereingaben anzeigen möchten, rufen Sie `ShowPopupMenu`. `TrackPopupMenu`wird verwendet, um ein Menü erstellt und wartet auf eine Benutzereingabe. `TrackPopupMenu`Gibt den Index des ausgewählten Befehls oder 0 zurück, wenn der Benutzer beendet, ohne eine Auswahl.  
  
 Die `CContextMenuManager` können auch speichern und Laden von Zuständen zur Windows-Registrierung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Menü Hinzufügen einer `CContextMenuManager` -Objekt, und wie Sie im Popupmenü active schließen bei der `CContextMenuManager` Objekt zeigt ein neues Popup-Menü. Dieser Codeausschnitt ist Teil der [benutzerdefinierte Seiten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages&4;](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CContextMenuManager`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxcontextmenumanager.h  
  
##  <a name="addmenu"></a>CContextMenuManager::AddMenu  
 Fügt ein neues Kontextmenü der [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
BOOL AddMenu(
    UINT uiMenuNameResId,  
    UINT uiMenuResId);

 
BOOL AddMenu(
    LPCTSTR lpszName,  
    UINT uiMenuResId);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiMenuNameResId`  
 Eine Ressourcen-ID für eine Zeichenfolge, die den Namen für das neue Menü enthält.  
  
 [in] `uiMenuResId`  
 Der Menü-Ressourcen-ID.  
  
 [in] `lpszName`  
 Eine Zeichenfolge, die den Namen für das neue Menü enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die Methode erfolgreich war; 0, wenn die Methode fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn `uiMenuResId` ist ungültig oder wird ein weiteres Menü mit demselben Namen bereits in der `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Erstellt eine [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen erstellen Sie keine `CContextMenuManager` manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Rufen Sie [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers auf dem Kontextmanager [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
##  <a name="getmenubyid"></a>CContextMenuManager::GetMenuById  
 Gibt ein Handle für das Menü, das eine bestimmte Ressource-ID zugeordnet ist  
  
```  
HMENU GetMenuById(UINT nMenuResId) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `nMenuResId`  
 Die Ressourcen-ID für das Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das zugehörige Menü oder `NULL` Wenn das Menü nicht gefunden wird.  
  
##  <a name="getmenubyname"></a>CContextMenuManager::GetMenuByName  
 Gibt ein Handle zu einem bestimmten Menü.  
  
```  
HMENU GetMenuByName(
    LPCTSTR lpszName,  
    UINT* puiOrigResID = NULL) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszName`  
 Eine Zeichenfolge, die den Namen des abzurufenden Menüs enthält.  
  
 [out] `puiOrigResID`  
 Ein Zeiger auf eine `UINT`. Dieser Parameter enthält die Ressourcen-ID des angegebenen Menüs, wenn gefunden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Handle für das Menü, das mit dem Namen übereinstimmt, der durch angegeben wurde `lpszName`. `NULL`Es ist kein Menü mit dem Namen `lpszName`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode ein Menü findet, entspricht `lpszName`, `GetMenuByName` speichert die Ressourcen-ID im Parameter `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Gibt die Liste der Menünamen hinzugefügt, die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `listOfNames`  
 Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Parameter. Diese Methode schreibt die Liste der Menünamen im für diesen Parameter.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 Lädt Informationen über die [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md) aus der Windows-Registrierung.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszProfileName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw..  
  
 Verwenden Sie die Methode [CContextMenuManager::SaveState](#savestate) zu den Kontextmenüs in der Registrierung speichern.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Löscht alle Elemente aus den zugeordneten Kontextmenüs der [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; `FALSE` , wenn ein Fehler auftritt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht den Popup-Menüs und entfernt sie aus der `CContextMenuManager`.  
  
##  <a name="savestate"></a>CContextMenuManager::SaveState  
 Speichert Informationen über die [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md) zur Windows-Registrierung.  
  
```  
virtual BOOL SaveState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszProfileName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standard-Registrierungsschlüssel für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder festlegen den Standard-Registrierungsschlüssel, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw..  
  
 Verwenden Sie die Methode [CContextMenuManager::LoadState](#loadstate) die Kontextmenüs aus der Registrierung geladen.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Steuerelemente, ob die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) im Popupmenü active schließt, wenn ein neues Popup-Menü angezeigt.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 Ein boolescher Parameter, der steuert, ob die aktive Popup-Menü zu schließen. Der Wert `TRUE` angibt, das aktive Popupmenü nicht geschlossen wird. `FALSE`Gibt an, dass die aktive Popupmenü geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 In der Standardeinstellung die `CContextMenuManager` schließt die aktive Popup-Menü.  
  
##  <a name="showpopupmenu"></a>CContextMenuManager::ShowPopupMenu  
 Zeigt das angegebene Kontextmenü an.  
  
```  
virtual BOOL ShowPopupMenu(
    UINT uiMenuResId,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bRightAlign = FALSE);

 
virtual CMFCPopupMenu* ShowPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bOwnMessage = FALSE,  
    BOOL bAutoDestroy = TRUE,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `uiMenuResId`  
 Die Ressourcen-ID des Menüs, das mit dieser Methode angezeigt wird.  
  
 [in] `x`  
 Der horizontale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `y`  
 Der vertikale Offset für das Kontextmenü in Clientkoordinaten  
  
 [in] `pWndOwner`  
 Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.  
  
 [in] `bOwnMessage`  
 Ein boolescher Parameter, der angibt, wie Nachrichten weitergeleitet werden. Wenn `bOwnMessage` ist `FALSE`, standard MFC routing verwendet wird. Andernfalls `pWndOwner` empfängt die Nachrichten.  
  
 [in] `hmenuPopup`  
 Das Handle des Menüs, das mit dieser Methode angezeigt wird.  
  
 [in] `bAutoDestroy`  
 Ein boolescher Parameter, der angibt, ob das Menü automatisch zerstört wird.  
  
 [in] `bRightAlign`  
 Ein boolescher Parameter, der angibt, wie die Elemente ausgerichtet werden. Wenn `bRightAlign` ist `TRUE`, klicken Sie im Menü wird rechts-nach-Links-Lesefolge rechtsbündig ausgerichtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste methodenüberladung gibt einen Wert ungleich NULL, wenn die Methode erfolgreich das Menü enthält. andernfalls 0. Die zweite methodenüberladung gibt einen Zeiger auf [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) im Kontextmenü angezeigt wird, ordnungsgemäß; andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt die Methode [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) , beide Methoden ein Kontextmenü anzuzeigen. Allerdings `TrackPopupMenu` gibt den Index des ausgewählten Menübefehls zurück.  
  
 Wenn der Parameter `bAutoDestroy` ist `FALSE`, müssen Sie manuell aufrufen, die geerbten `DestroyMenu` Methode, um Speicherressourcen freizugeben. Die standardmäßige Implementierung des `ShowPopupMenu` verwendet nicht den Parameter `bAutoDestroy`. Er wird bereitgestellt, für die zukünftige Verwendung oder für benutzerdefinierte Klassen abgeleitet der `CContextMenuManager` Klasse.  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 Zeigt das angegebene Kontextmenü, und gibt den Index des ausgewählten Kontextmenübefehls zurück.  
  
```  
virtual UINT TrackPopupMenu(
    HMENU hmenuPopup,  
    int x,  
    int y,  
    CWnd* pWndOwner,  
    BOOL bRightAlign = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `hmenuPopup`  
 Das Handle des Kontextmenüs, die dieser Methode angezeigt.  
  
 [in] `x`  
 Der horizontale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `y`  
 Der vertikale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `pWndOwner`  
 Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.  
  
 [in] `bRightAlign`  
 Ein boolescher Parameter, der angibt, wie Menüelemente ausgerichtet sind. Wenn `bRightAlign` ist `TRUE`, klicken Sie im Menü wird rechts-nach-Links-Lesefolge rechtsbündig ausgerichtet. Wenn `bRightAlign` ist `FALSE`, klicken Sie im Menü wird links-nach-rechts-Lesefolge linksbündig ausgerichtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Menübefehl-ID des Befehls, die der Benutzer auswählt; 0, wenn der Benutzer das Kontextmenü geschlossen wird, ohne Auswählen eines Menübefehls.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode fungiert als modales Aufruf ein Kontextmenü anzuzeigen. Die Anwendung wird nicht mit der folgenden Zeile im Code fortgesetzt, bis der Benutzer das Kontextmenü geschlossen oder einen Befehl auswählt. Eine alternative Methode, die Sie verwenden können, um ein Kontextmenü anzuzeigen ist [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Diese Methode ist nicht modal Aufruf und die ID des ausgewählten Befehls wird nicht zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)

