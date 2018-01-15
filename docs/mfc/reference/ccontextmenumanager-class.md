---
title: CContextMenuManager Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords:
- CContextMenuManager [MFC], CContextMenuManager
- CContextMenuManager [MFC], AddMenu
- CContextMenuManager [MFC], GetMenuById
- CContextMenuManager [MFC], GetMenuByName
- CContextMenuManager [MFC], GetMenuNames
- CContextMenuManager [MFC], LoadState
- CContextMenuManager [MFC], ResetState
- CContextMenuManager [MFC], SaveState
- CContextMenuManager [MFC], SetDontCloseActiveMenu
- CContextMenuManager [MFC], ShowPopupMenu
- CContextMenuManager [MFC], TrackPopupMenu
ms.assetid: 1de20640-243c-47e1-85de-1baa4153bc83
caps.latest.revision: "32"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 38bfaec077501173fade6fa15fba3516cde534b9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccontextmenumanager-class"></a>CContextMenuManager-Klasse
Die `CContextMenuManager` Objekt verwaltet Kontextmenüs, auch als Verknüpfungsmenüs bezeichnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CContextMenuManager : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContextMenuManager::CContextMenuManager](#ccontextmenumanager)|Erstellt ein `CContextMenuManager`-Objekt.|  
|`CContextMenuManager::~CContextMenuManager`|Destruktor.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CContextMenuManager::AddMenu](#addmenu)|Fügt ein neues Kontextmenü an.|  
|[CContextMenuManager::GetMenuById](#getmenubyid)|Gibt ein Handle für das Menü, das die angegebenen Ressourcen-ID zugeordnet ist|  
|[CContextMenuManager::GetMenuByName](#getmenubyname)|Gibt ein Handle auf das Menü, das der angegebene Name entspricht.|  
|[CContextMenuManager::GetMenuNames](#getmenunames)|Gibt eine Liste der Menünamen zurück.|  
|[CContextMenuManager::LoadState](#loadstate)|Lädt die Kontextmenüs, die in der Windows-Registrierung gespeichert.|  
|[CContextMenuManager::ResetState](#resetstate)|Löscht die Kontextmenüs aus dem Kontext-Manager im Menü an.|  
|[CContextMenuManager::SaveState](#savestate)|Kontextmenüs in der Windows-Registrierung gespeichert.|  
|[CContextMenuManager::SetDontCloseActiveMenu](#setdontcloseactivemenu)|Steuert, ob die `CContextMenuManager` schließt das aktive Kontextmenü, wenn sie ein neues Kontextmenü angezeigt wird.|  
|[CContextMenuManager::ShowPopupMenu](#showpopupmenu)|Zeigt das angegebene Kontextmenü an.|  
|[CContextMenuManager::TrackPopupMenu](#trackpopupmenu)|Zeigt das angegebene Kontextmenü an. Gibt den Index des ausgewählten Menübefehls zurück.|  
  
## <a name="remarks"></a>Hinweise  
 `CContextMenuManager`verwaltet Kontextmenüs und stellt sicher, dass sie eine konsistente Darstellung haben.  
  
 Sie sollten keine erstellen eine `CContextMenuManager` Objekt manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Sie sollten jedoch aufrufen [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) Wenn Ihre Anwendung initialisiert wird. Wenn nach der Initialisierung des Kontext-Managers, verwenden Sie die Methode [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager) um einen Zeiger auf die Kontext-Manager für Ihre Anwendung abzurufen.  
  
 Erstellen Kontextmenüs während der Laufzeit durch Aufrufen von `AddMenu`. Wenn Sie das Menü ohne erste empfangenden Benutzereingaben anzeigen möchten, rufen Sie `ShowPopupMenu`. `TrackPopupMenu`wird verwendet, wenn Sie verwenden möchten, erstellen Sie ein Menü, und Benutzereingaben. `TrackPopupMenu`Gibt den Index des ausgewählten Befehls oder 0 zurück, wenn der Benutzer beendet, ohne etwas auszuwählen.  
  
 Die `CContextMenuManager` können auch speichern und Laden von Zuständen an der Windows-Registrierung.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein Menü Hinzufügen einer `CContextMenuManager` Objekt sowie zum nicht aktive Popupmenü schließen bei der `CContextMenuManager` Objekt ein neues Popupmenü anzeigt. Dieser Codeausschnitt ist Teil der [benutzerdefinierte Seiten Beispiel](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_CustomPages#4](../../mfc/reference/codesnippet/cpp/ccontextmenumanager-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
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
 Wert ungleich NULL, wenn die Methode erfolgreich ausgeführt wurde; 0, wenn die Methode fehlschlägt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode schlägt fehl, wenn `uiMenuResId` ist ungültig oder wird ein weiteres Menü mit dem gleichen Namen bereits in der `CContextMenuManager`.  
  
##  <a name="ccontextmenumanager"></a>CContextMenuManager::CContextMenuManager  
 Erstellt eine [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) Objekt.  
  
```  
CContextMenuManager();
```  
  
### <a name="remarks"></a>Hinweise  
 In den meisten Fällen sollten Sie keine erstellen eine `CContextMenuManager` manuell. Das Framework der Anwendung erstellt die `CContextMenuManager` Objekt. Rufen Sie [CWinAppEx::InitContextMenuManager](../../mfc/reference/cwinappex-class.md#initcontextmenumanager) während der Initialisierung der Anwendung. Rufen Sie zum Abrufen eines Zeigers auf dem Kontextmanager [CWinAppEx::GetContextMenuManager](../../mfc/reference/cwinappex-class.md#getcontextmenumanager).  
  
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
 Gibt ein Handle zu einem bestimmten Menü zurück.  
  
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
 Ein Handle für das Menü, das mit dem Namen übereinstimmt, die von angegeben wurde `lpszName`. `NULL`Es ist kein Menü aufgerufen `lpszName`.  
  
### <a name="remarks"></a>Hinweise  
 Wenn diese Methode ein Menü findet, entspricht `lpszName`, `GetMenuByName` speichert die Ressourcen-ID im Menü im Parameters `puiOrigResID`.  
  
##  <a name="getmenunames"></a>CContextMenuManager::GetMenuNames  
 Gibt die Liste der Menünamen hinzugefügt, um die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
void GetMenuNames(CStringList& listOfNames) const;  
```  
  
### <a name="parameters"></a>Parameter  
 [out] `listOfNames`  
 Ein Verweis auf eine [CStringList](../../mfc/reference/cstringlist-class.md) Parameter. Diese Methode schreibt die Liste der Menünamen an diesen Parameter an.  
  
##  <a name="loadstate"></a>CContextMenuManager::LoadState  
 Zugeordnete Informationen lädt die [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md) aus der Windows-Registrierung.  
  
```  
virtual BOOL LoadState(LPCTSTR lpszProfileName = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `lpszProfileName`  
 Eine Zeichenfolge, die den relativen Pfad eines Registrierungsschlüssels enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Methode erfolgreich ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `lpszProfileName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standardschlüssel für die Registrierung für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder Festlegen des Standard-Registrierungsschlüssels, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw.  
  
 Verwenden Sie die Methode [CContextMenuManager::SaveState](#savestate) auf den Kontextmenüs in der Registrierung speichern.  
  
##  <a name="resetstate"></a>CContextMenuManager::ResetState  
 Löscht alle Elemente aus der zugeordneten Kontextmenüs der [CContextMenuManager Klasse](../../mfc/reference/ccontextmenumanager-class.md).  
  
```  
virtual BOOL ResetState();
```  
  
### <a name="return-value"></a>Rückgabewert  
 `TRUE`Wenn die Methode erfolgreich ist; `FALSE` tritt ein Fehler auf.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode löscht die Popupmenüs und entfernt sie aus der `CContextMenuManager`.  
  
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
 Die `lpszProfileName` Parameter ist nicht der absolute Pfad für einen Registrierungseintrag. Es ist ein relativer Pfad, der an das Ende der Standardschlüssel für die Registrierung für Ihre Anwendung hinzugefügt wird. Verwenden Sie zum Abrufen oder Festlegen des Standard-Registrierungsschlüssels, die Methoden [CWinAppEx::GetRegistryBase](../../mfc/reference/cwinappex-class.md#getregistrybase) und [CWinAppEx::SetRegistryBase](../../mfc/reference/cwinappex-class.md#setregistrybase) bzw.  
  
 Verwenden Sie die Methode [CContextMenuManager::LoadState](#loadstate) Kontextmenüs aus der Registrierung geladen.  
  
##  <a name="setdontcloseactivemenu"></a>CContextMenuManager::SetDontCloseActiveMenu  
 Steuert, ob die [CContextMenuManager](../../mfc/reference/ccontextmenumanager-class.md) aktive Popupmenü schließt, wenn sie ein neues Popup-Menü wird angezeigt.  
  
```  
void SetDontCloseActiveMenu (BOOL bSet = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 [in] `bSet`  
 Ein boolescher Parameter, der steuert, ob die aktive Popupmenü zu schließen. Der Wert `TRUE` gibt an, die aktive Popupmenü ist nicht geschlossen. `FALSE`Gibt an, dass ein aktive Popupmenü geschlossen wird.  
  
### <a name="remarks"></a>Hinweise  
 Wird standardmäßig die `CContextMenuManager` schließt aktive Popupmenü.  
  
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
 Die Ressourcen-ID des Menüs, die diese Methode angezeigt werden.  
  
 [in] `x`  
 Der horizontale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `y`  
 Der vertikale Offset für das Kontextmenü in Clientkoordinaten  
  
 [in] `pWndOwner`  
 Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.  
  
 [in] `bOwnMessage`  
 Ein boolescher Parameter, der angibt, wie die Nachrichten weitergeleitet werden. Wenn `bOwnMessage` ist `FALSE`, standard-MFC-routing verwendet wird. Andernfalls `pWndOwner` empfängt die Nachrichten.  
  
 [in] `hmenuPopup`  
 Das Handle des Menüs, die diese Methode angezeigt werden.  
  
 [in] `bAutoDestroy`  
 Ein boolescher Parameter, der angibt, ob das Menü automatisch zerstört wird.  
  
 [in] `bRightAlign`  
 Ein boolescher Parameter, der angibt, wie die Menüelemente ausgerichtet sind. Wenn `bRightAlign` ist `TRUE`, klicken Sie im Menü wird rechts für rechts-nach-Links-Lesefolge ausgerichtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Die erste methodenüberladung gibt ungleich NULL, wenn die Methode erfolgreich das Menü enthält. andernfalls 0. Die zweite methodenüberladung gibt einen Zeiger auf [CMFCPopupMenu](../../mfc/reference/cmfcpopupmenu-class.md) im Kontextmenü angezeigt wird, ordnungsgemäß andernfalls `NULL`.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode ähnelt die Methode [CContextMenuManager::TrackPopupMenu](#trackpopupmenu) dahingehend, dass beide Methoden ein Kontextmenü anzuzeigen. Allerdings `TrackPopupMenu` gibt den Index des ausgewählten Menübefehls zurück.  
  
 Wenn der Parameter `bAutoDestroy` ist `FALSE`, müssen Sie manuell aufrufen, die geerbte `DestroyMenu` Methode, um Speicherressourcen freizugeben. Die standardmäßige Implementierung des `ShowPopupMenu` verwendet nicht den Parameter `bAutoDestroy`. Er wird bereitgestellt, für die zukünftige Verwendung oder für benutzerdefinierte Klassen abgeleitet wurde. die `CContextMenuManager` Klasse.  
  
##  <a name="trackpopupmenu"></a>CContextMenuManager::TrackPopupMenu  
 Zeigt das Kontextmenü für die angegebenen und den Index des ausgewählten Kontextmenübefehl zurückgibt.  
  
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
 Das Handle des Kontextmenüs, die von dieser Methode wird angezeigt.  
  
 [in] `x`  
 Der horizontale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `y`  
 Der vertikale offset für das Kontextmenü in Clientkoordinaten.  
  
 [in] `pWndOwner`  
 Ein Zeiger auf das übergeordnete Fenster des Kontextmenüs.  
  
 [in] `bRightAlign`  
 Ein boolescher Parameter, der angibt, wie Menüelemente ausgerichtet sind. Wenn `bRightAlign` ist `TRUE`, klicken Sie im Menü wird rechts für rechts-nach-Links-Lesefolge ausgerichtet. Wenn `bRightAlign` ist `FALSE`, das Menü ist für die Lesefolge von links nach rechts linksbündig ausgerichtet.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Menübefehl-ID des Befehls ab, die der Benutzer auswählt; 0, wenn der Benutzer im Kontextmenü schließt, ohne einen Menübefehl auszuwählen.  
  
### <a name="remarks"></a>Hinweise  
 Diese Methode funktioniert wie ein modales Aufruf ein Kontextmenü anzuzeigen. Die Anwendung wird nicht mit der folgenden Zeile im Code fortgesetzt, bis der Benutzer das Kontextmenü geschlossen oder einen Befehl auswählt. Ist eine alternative Methode, die Sie verwenden können, um ein Kontextmenü anzuzeigen [CContextMenuManager::ShowPopupMenu](#showpopupmenu). Diese Methode nicht modalen aufgerufen wird und nicht die ID des ausgewählten Befehls zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [Klassen](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx-Klasse](../../mfc/reference/cwinappex-class.md)
