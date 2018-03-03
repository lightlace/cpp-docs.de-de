---
title: CMenu-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMenu
- AFXWIN/CMenu
- AFXWIN/CMenu::CMenu
- AFXWIN/CMenu::AppendMenu
- AFXWIN/CMenu::Attach
- AFXWIN/CMenu::CheckMenuItem
- AFXWIN/CMenu::CheckMenuRadioItem
- AFXWIN/CMenu::CreateMenu
- AFXWIN/CMenu::CreatePopupMenu
- AFXWIN/CMenu::DeleteMenu
- AFXWIN/CMenu::DeleteTempMap
- AFXWIN/CMenu::DestroyMenu
- AFXWIN/CMenu::Detach
- AFXWIN/CMenu::DrawItem
- AFXWIN/CMenu::EnableMenuItem
- AFXWIN/CMenu::FromHandle
- AFXWIN/CMenu::GetDefaultItem
- AFXWIN/CMenu::GetMenuContextHelpId
- AFXWIN/CMenu::GetMenuInfo
- AFXWIN/CMenu::GetMenuItemCount
- AFXWIN/CMenu::GetMenuItemID
- AFXWIN/CMenu::GetMenuItemInfo
- AFXWIN/CMenu::GetMenuState
- AFXWIN/CMenu::GetMenuString
- AFXWIN/CMenu::GetSafeHmenu
- AFXWIN/CMenu::GetSubMenu
- AFXWIN/CMenu::InsertMenu
- AFXWIN/CMenu::InsertMenuItem
- AFXWIN/CMenu::LoadMenu
- AFXWIN/CMenu::LoadMenuIndirect
- AFXWIN/CMenu::MeasureItem
- AFXWIN/CMenu::ModifyMenu
- AFXWIN/CMenu::RemoveMenu
- AFXWIN/CMenu::SetDefaultItem
- AFXWIN/CMenu::SetMenuContextHelpId
- AFXWIN/CMenu::SetMenuInfo
- AFXWIN/CMenu::SetMenuItemBitmaps
- AFXWIN/CMenu::SetMenuItemInfo
- AFXWIN/CMenu::TrackPopupMenu
- AFXWIN/CMenu::TrackPopupMenuEx
- AFXWIN/CMenu::m_hMenu
dev_langs:
- C++
helpviewer_keywords:
- CMenu [MFC], CMenu
- CMenu [MFC], AppendMenu
- CMenu [MFC], Attach
- CMenu [MFC], CheckMenuItem
- CMenu [MFC], CheckMenuRadioItem
- CMenu [MFC], CreateMenu
- CMenu [MFC], CreatePopupMenu
- CMenu [MFC], DeleteMenu
- CMenu [MFC], DeleteTempMap
- CMenu [MFC], DestroyMenu
- CMenu [MFC], Detach
- CMenu [MFC], DrawItem
- CMenu [MFC], EnableMenuItem
- CMenu [MFC], FromHandle
- CMenu [MFC], GetDefaultItem
- CMenu [MFC], GetMenuContextHelpId
- CMenu [MFC], GetMenuInfo
- CMenu [MFC], GetMenuItemCount
- CMenu [MFC], GetMenuItemID
- CMenu [MFC], GetMenuItemInfo
- CMenu [MFC], GetMenuState
- CMenu [MFC], GetMenuString
- CMenu [MFC], GetSafeHmenu
- CMenu [MFC], GetSubMenu
- CMenu [MFC], InsertMenu
- CMenu [MFC], InsertMenuItem
- CMenu [MFC], LoadMenu
- CMenu [MFC], LoadMenuIndirect
- CMenu [MFC], MeasureItem
- CMenu [MFC], ModifyMenu
- CMenu [MFC], RemoveMenu
- CMenu [MFC], SetDefaultItem
- CMenu [MFC], SetMenuContextHelpId
- CMenu [MFC], SetMenuInfo
- CMenu [MFC], SetMenuItemBitmaps
- CMenu [MFC], SetMenuItemInfo
- CMenu [MFC], TrackPopupMenu
- CMenu [MFC], TrackPopupMenuEx
- CMenu [MFC], m_hMenu
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 104c965da403040308386e019d56684577318eee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cmenu-class"></a>CMenu-Klasse
Eine Kapselung von Windows- `HMENU`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|Erstellt ein `CMenu`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|Fügt ein neues Element am Ende dieses Menü an.|  
|[CMenu::Attach](#attach)|Fügt ein Windows-Menü-Handle für ein `CMenu` Objekt.|  
|[CMenu::CheckMenuItem](#checkmenuitem)|Setzt ein Häkchen neben oder entfernt ein Häkchen aus ein Menüelement im Popupmenü.|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Ein Optionsfeld neben einem Menüelement platziert, und das Optionsfeld aus allen die anderen Menüelemente, die Sie in der Gruppe entfernt.|  
|[CMenu::CreateMenu](#createmenu)|Erstellt ein leeres Menü und fügt es einer `CMenu` Objekt.|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|Erstellt ein leeres Popup-Menü und fügt es einer `CMenu` Objekt.|  
|[:: DeleteMenu auf](#deletemenu)|Löscht ein angegebenes Element aus dem Menü an. Wenn dem Menüelement, das ein zugeordnetes Popupmenü verfügt, zerstört das Handle für das Menü das Popupmenü und gibt die von diesem verwendeten Arbeitsspeicher frei.|  
|[CMenu::DeleteTempMap](#deletetempmap)|Löscht temporäre `CMenu` Objekte erstellt, indem die `FromHandle` Memberfunktion.|  
|[CMenu::DestroyMenu](#destroymenu)|Zerstört das Menü an der ein `CMenu` -Objekt und Speicher, der das Menü belegt frei.|  
|[CMenu::Detach](#detach)|Trennt ein Windows-Menü-Handle aus einem `CMenu` -Objekt und gibt das Handle zurück.|  
|[CMenu::DrawItem](#drawitem)|Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Menü ändert.|  
|[CMenu:: EnableMenuItem](#enablemenuitem)|Aktiviert, deaktiviert oder abgeblendet (grau) eines Menüelements.|  
|[CMenu::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CMenu` Objekt anhand einer Windows-Menü-Handles.|  
|[CMenu::GetDefaultItem](#getdefaultitem)|Bestimmt das Standardmenüelement auf das angegebene Menü an.|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Ruft die Hilfekontext-ID verknüpft sind, mit dem Menü ab.|  
|[CMenu::GetMenuInfo](#getmenuinfo)|Ruft die Informationen in einem bestimmten Menü ab.|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Bestimmt die Anzahl der Elemente in einem Menü Popup bzw. der obersten Ebene an.|  
|[CMenu::GetMenuItemID](#getmenuitemid)|Ruft das Menüelement Bezeichner für ein Menüelement, an der angegebenen Position befindet.|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Ruft Informationen über ein Menüelement ab.|  
|[CMenu::GetMenuState](#getmenustate)|Gibt den Status des angegebenen Menüelements oder die Anzahl der Elemente in einem Popupmenü zurück.|  
|[CMenu::GetMenuString](#getmenustring)|Ruft die Bezeichnung des angegebenen Menüelements ab.|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|Gibt die `m_hMenu` von diesem umschlossenen `CMenu` Objekt.|  
|[CMenu::GetSubMenu](#getsubmenu)|Ruft einen Zeiger auf ein Popupmenü ab.|  
|[CMenu::InsertMenu](#insertmenu)|Fügt ein neues Menüelement an der angegebenen Position, andere Elemente im Menü verschieben.|  
|[CMenu::InsertMenuItem](#insertmenuitem)|Fügt ein neues Menüelement an der angegebenen Position in einem Menü an.|  
|[CMenu::LoadMenu](#loadmenu)|Lädt eine Menüressource aus der ausführbaren Datei und fügt es einer `CMenu` Objekt.|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Lädt ein Menü aus einer Menüvorlage im im Arbeitsspeicher und fügt es einer `CMenu` Objekt.|  
|[CMenu::MeasureItem](#measureitem)|Wird aufgerufen, durch das Framework Menü Dimensionen zu bestimmen, wann ein vom Besitzer gezeichnetes Menü erstellt wird.|  
|[CMenu::ModifyMenu](#modifymenu)|Ändert eine vorhandene Menüelement, an der angegebenen Position.|  
|[CMenu::RemoveMenu](#removemenu)|Löscht ein Menüelement mit einer zugeordneten Popupmenü aus dem angegebenen Menü an.|  
|[CMenu::SetDefaultItem](#setdefaultitem)|Legt das Standardmenüelement für das angegebene Menü fest.|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Legt die Hilfekontext-ID mit dem Menü zugeordnet werden soll.|  
|[CMenu::SetMenuInfo](#setmenuinfo)|Legt die Informationen in einem bestimmten Menü fest.|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Ordnet die angegebene Häkchen Bitmaps eines Menüelements.|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Ändert die Informationen über ein Menüelement.|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Ein unverankertes Popupmenü anzeigt, an der angegebenen Position und verfolgt die Auswahl von Elementen im Popupmenü.|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Ein unverankertes Popupmenü anzeigt, an der angegebenen Position und verfolgt die Auswahl von Elementen im Popupmenü.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|Ruft das Handle für das Menu-Objekt ab.|  
|[CMenu::operator! =](#operator_neq)|Bestimmt, ob zwei Menu-Objekte ungleich sind.|  
|[CMenu::operator ==](#operator_eq_eq)|Bestimmt, ob zwei Menu-Objekte gleich sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|Gibt das Handle für das Windows-Menü angefügt, um die `CMenu` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Es stellt Memberfunktionen zum Erstellen, nachverfolgen, aktualisieren und löschen ein Menü bereit.  
  
 Erstellen einer `CMenu` Objekt im Stapelrahmen als lokales, rufen Sie dann `CMenu`des Member-Funktionen, um das neue Menü zu bearbeiten, nach Bedarf. Rufen Sie als Nächstes [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) für ein Fenster im Menü festzulegen, unmittelbar gefolgt von einem Aufruf der `CMenu` des Objekts [trennen](#detach) Memberfunktion. Die `CWnd::SetMenu` Memberfunktion legt das Menü des Fensters für das neue Menü des Fensters neu gezeichnet werden, damit die Änderung im Menü angezeigt wird und übergibt außerdem den Besitz des Menüs für das Fenster. Der Aufruf von **trennen** trennt die `HMENU` aus der `CMenu` -Objekt, sodass bei der lokalen `CMenu` -Variable übergibt außerhalb des gültigen Bereichs, der `CMenu` Objektdestruktor wird nicht versucht, ein Menü zu zerstören es keine mehr besitzt. Das Menü selbst wird automatisch zerstört, wenn das Fenster zerstört wird.  
  
 Können Sie die [LoadMenuIndirect](#loadmenuindirect) Memberfunktion versucht, erstellen Sie ein Menü aus einer Vorlage im Arbeitsspeicher, aber ein Menü erstellt aus einer Ressource durch einen Aufruf von [LoadMenu](#loadmenu) leichter verwaltet wird, und die Menüressource selbst erstellt und im Menü-Editor geändert werden können.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 Fügt ein neues Element an das Ende eines Menüs.  
  
```  
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL AppendMenu(
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parameter  
 `nFlags`  
 Gibt Informationen über den Zustand für das neue Menüelement an, wenn sie zum Menü hinzugefügt wird. Er besteht aus mindestens einer der Werte im Abschnitt "Hinweise" aufgeführt.  
  
 `nIDNewItem`  
 Gibt an, entweder die Befehls-ID des neuen Menüelements oder, wenn der `nFlags` auf festgelegt ist **MF_POPUP**, das Menü Handle ( `HMENU`) eines Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` festgelegt ist, um **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. Die `nFlags` Parameter wird verwendet, um interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete verwalten. Dieser 32-Bit-Wert ist für die Anwendung verfügbar, bei der Verarbeitung `WM_MEASUREITEM` und `WM_DRAWITEM` Nachrichten. Der Wert wird gespeichert, der **ItemData** Member der Struktur, die im Lieferumfang dieser Nachrichten.|  
|**MF_STRING**|Enthält einen Zeiger auf eine Null-terminierte Zeichenfolge an. Dies ist die Standardinterpretation.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht benötigt).|  
  
 *pBmp*  
 Verweist auf eine `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung kann den Status des Menüelements angeben, durch Festlegen von Werten in `nFlags`. Wenn `nIDNewItem` ein Popupmenü gibt es Teil der Menüs "" an das sie angefügt wird. Wenn das Menü zerstört wird, wird auch das angefügte Menü zerstört werden. Eine angefügte Menü sollte vom getrennt werden, ein `CMenu` Objekt, um Konflikte zu vermeiden. Beachten Sie, dass **MF_STRING** und `MF_OWNERDRAW` sind nicht gültig für die Bitmap-Version des `AppendMenu`.  
  
 Die folgende Liste beschreibt die Flags, die festgelegt werden können, im `nFlags`:  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der [SetMenuItemBitmaps](#setmenuitembitmaps) Memberfunktion), die Bitmap "Häkchen auf" angezeigt.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch ist nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement aus, sodass ausgewählt werden kann, und vom abgeblendet Zustand wiederhergestellt werden kann.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass er nicht ausgewählt werden, und es Blendet.  
  
- **MF_MENUBARBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in einer neuen Spalte in Popupmenüs. Die neue Popupmenü-Spalte wird durch eine vertikale Trennlinie aus der alten Spalte getrennt werden.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in einer neuen Spalte in Popupmenüs. Es wird keine Trennlinie zwischen den Spalten platziert.  
  
- `MF_OWNERDRAW`Gibt an, dass das Element ein Ownerdrawn-Element. Wenn das Menü zum ersten Mal angezeigt wird, empfängt das Fenster, das Menü besitzt, eine `WM_MEASUREITEM` Nachricht, die die Höhe und Breite des Menüelements abruft. Die `WM_DRAWITEM` Nachricht wird gesendet, wenn der Besitzer die visuelle Darstellung des Menüelements aktualisieren muss. Diese Option gilt nicht für ein Menüelement der obersten Ebene.  
  
- **MF_POPUP** gibt an, dass das Menüelement ein Popupmenü zugeordnet wurde. Die ID-Parameter gibt ein Handle für ein Popupmenü aufrufen, die dem Element zugeordnet werden soll. Dient zum Popupmenü-Elements ein Popup-Menü der obersten Ebene oder eine hierarchische Popupmenü hinzugefügt.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.  
  
- **MF_STRING** gibt an, dass dem Menüelement, das eine Zeichenfolge handelt.  
  
 Jede der folgenden Gruppen Listet die Flags, die sich gegenseitig und können nicht zusammen verwendet werden:  
  
- **MF_DISABLED**, `MF_ENABLED`, und **MF_GRAYED**  
  
- **MF_STRING**, `MF_OWNERDRAW`, **MF_SEPARATOR**, und die Bitmap-Version  
  
- **MF_MENUBARBREAK** und **MF_MENUBREAK**  
  
- **MF_CHECKED** und **MF_UNCHECKED**  
  
 Wenn ein Menü befindet, die in einem Fenster (ob das Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="attach"></a>CMenu::Attach  
 Fügt ein vorhandenes Windows-Menü auf einer `CMenu` Objekt.  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Gibt ein Handle für ein Windows-Menü an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, wenn ein Menü bereits angefügt wurden die `CMenu` Objekt. Das Handle im Menü befindet sich in der `m_hMenu` -Datenmember.  
  
 Wenn das Menü, das Sie bearbeiten möchten, bereits ein Fenster zugeordnet ist, können Sie die [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) Funktion, um ein Handle für das Menü zu erhalten.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 Fügt Häkchen zu oder Häkchen von Menüelementen im Popupmenü entfernt.  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCheckItem`  
 Gibt das Menüelement überprüft werden soll, gemäß `nCheck`.  
  
 `nCheck`  
 Gewusst wie: Überprüfen Sie das Menüelement und zum Feststellen der Position des Elements im Menü angibt. Die `nCheck` Parameter kann eine Kombination von **MF_CHECKED** oder **MF_UNCHECKED** mit **MF_BYPOSITION** oder **MF_BYCOMMAND** Flags. Diese Flags können mit dem bitweisen OR-Operator kombiniert werden. Sie haben folgende Bedeutung:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Status des Elements: **MF_CHECKED** oder **MF_UNCHECKED**, oder 0xFFFFFFFF, wenn das Menüelement nicht vorhanden war.  
  
### <a name="remarks"></a>Hinweise  
 Die `nIDCheckItem` Parameter gibt das Element, das geändert werden.  
  
 Die `nIDCheckItem` Parameter möglicherweise Popupmenü-Elements als auch ein Menüelement zu identifizieren. Keine speziellen Schritte sind erforderlich, um ein Popupmenü-Elements zu überprüfen. Menüelemente auf oberster Ebene können nicht überprüft werden. Ein Popupmenü-Elements muss anhand der Position überprüft werden, da es keinen Menüelement Bezeichner zugeordnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::GetMenuState](#getmenustate).  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 Überprüft ein angegebenes Menüelement und erleichtert ein Optionsfeld-Element.  
  
```  
BOOL CheckMenuRadioItem(
    UINT nIDFirst,  
    UINT nIDLast,  
    UINT nIDItem,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDFirst`  
 Gibt an (als ID oder Offset, abhängig vom Wert der `nFlags`) das erste Menüelement in der Optionsfeldgruppe.  
  
 `nIDLast`  
 Gibt an (als ID oder Offset, abhängig vom Wert des `nFlags`) der letzten Menüelement in der Optionsfeldgruppe.  
  
 `nIDItem`  
 Gibt an (als ID oder Offset, abhängig vom Wert der `nFlags`) das Element in die Gruppe, die mit einem Optionsfeld geprüft wird.  
  
 `nFlags`  
 Gibt die Interpretation der `nIDFirst`, `nIDLast`, und `nIDItem` auf folgende Weise:  
  
|nFlags|Interpretation|  
|------------|--------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Zur gleichen Zeit die Funktion deaktiviert alle Menüelemente in der zugehörigen Gruppe und löscht das Optionsfeld-Item-Typ-Flag für diese Elemente. Aktivierten Elements ist eine Bitmap Häkchen anstelle einer Radio-Schaltfläche (oder Aufzählungszeichen) Bitmap angezeigt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [ON_COMMAND_RANGE](message-map-macros-mfc.md#on_command_range).  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 Erstellt ein leeres Menü und fügt es einer `CMenu` Objekt.  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü wird nicht erstellt werden, bis Sie eine der Memberfunktionen erstellen oder Laden von Aufrufen **CMenu:**  
  
- [CreateMenu](#createmenu)  
  
- [CreatePopupMenu](#createpopupmenu)  
  
- [LoadMenu](#loadmenu)  
  
- [LoadMenuIndirect](#loadmenuindirect)  
  
- [Anfügen](#attach)  
  
##  <a name="createmenu"></a>CMenu::CreateMenu  
 Erstellt ein Menü, und fügt es der `CMenu` Objekt.  
  
```  
BOOL CreateMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Menü erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü ist anfangs leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` Memberfunktion.  
  
 Wenn ein Fenster im Menü zugewiesen wird, wird es automatisch zerstört, wenn das Fenster zerstört wird.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei ein Menü zugeordnet, wenn das Menü nicht in einem Fenster zugewiesen wird. Eine Anwendung gibt ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#22](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 Erstellt ein Popupmenü und fügt es der `CMenu` Objekt.  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Menü das Popupmenü erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü ist anfangs leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` Memberfunktion. Die Anwendung kann im Popupmenü zu einer vorhandenen Menü oder Popupmenü hinzufügen. Die `TrackPopupMenu` Memberfunktion kann verwendet werden, um diesem Menü als unverankerte Popupmenü anzuzeigen und zum Nachverfolgen der Auswahl im Popupmenü.  
  
 Wenn ein Fenster im Menü zugewiesen wird, wird es automatisch zerstört, wenn das Fenster zerstört wird. Wenn Sie im Menü auf einem vorhandenen Menü hinzugefügt wird, wird es automatisch zerstört, wenn das Menü zerstört wird.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei ein Popupmenü zugeordnet, wenn das Menü nicht in einem Fenster zugewiesen wird. Eine Anwendung gibt ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="deletemenu"></a>:: DeleteMenu auf  
 Löscht ein Element aus dem Menü an.  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt an, das Menüelement, das gelöscht werden, gemäß `nFlags`.  
  
 `nFlags`  
 Dient zum Interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das Menüelement besitzt ein zugeordnete Popupmenü `DeleteMenu` zerstört das Handle für das Menü das Popupmenü und gibt den Arbeitsspeicher frei von Popupmenü verwendet.  
  
 Wenn ein Menü befindet, die in einem Fenster (ob das Fenster angezeigt wird) geändert wird, muss die Anwendung aufrufen [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 Wird aufgerufen, automatisch von der `CWinApp` -leerlaufzeithandler, löscht temporäre `CMenu` Objekte erstellt, indem die [FromHandle](#fromhandle) Memberfunktion.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Hinweise  
 `DeleteTempMap`trennt das Windows-Menu-Objekt angefügt, die an einen temporären `CMenu` Objekt vor dem Löschen der `CMenu` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#23](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>CMenu::DestroyMenu  
 Zerstört das Menü und alle Windows-Ressourcen, die verwendet wurden.  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Menü zerstört wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü wird getrennt von den `CMenu` -Objekt, bevor es zerstört wird. Die Windows `DestroyMenu` Funktion wird automatisch aufgerufen, dem `CMenu` Destruktor.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="detach"></a>CMenu::Detach  
 Trennt ein Windows-Menü aus einem `CMenu` -Objekt und gibt das Handle zurück.  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Typs `HMENU`, zu einem Windows-Menü, wenn erfolgreich; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hMenu` -Datenmember festgelegt ist, um **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#21](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 Wird aufgerufen, durch das Framework, wenn sich ein Darstellungsaspekt eines Ownerdrawn-Menü ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der Zeichnung erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für ein Ownerdrawn- `CMenu` Objekt. Die Anwendung muss alle Device Interface (GDI) Grafikobjekten ausgewählt, für der Anzeigekontext in bereitgestellten wiederherstellen `lpDrawItemStruct` vor dem Beenden des diese Memberfunktion.  
  
 Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code stammt aus dem MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#24](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu:: EnableMenuItem  
 Aktiviert, deaktiviert oder ein Menüelement abgeblendet.  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDEnableItem*  
 Gibt das Menüelement aktiviert werden, gemäß `nEnable`. Dieser Parameter kann Popupmenü-Elemente sowie Standardmenüelementen angeben.  
  
 `nEnable`  
 Gibt die zu ergreifende Maßnahme. Es kann eine Kombination von **MF_DISABLED**, `MF_ENABLED`, oder **MF_GRAYED**, mit **MF_BYCOMMAND** oder **MF_BYPOSITION**. Diese Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch ist nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement aus, sodass ausgewählt werden kann, und vom abgeblendet Zustand wiederhergestellt werden kann.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass er nicht ausgewählt werden, und es Blendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Vorherigen Zustand ( **MF_DISABLED**, `MF_ENABLED`, oder **MF_GRAYED**) oder -1, wenn er nicht gültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Die [CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), und [LoadMenuIndirect](#loadmenuindirect) Memberfunktionen können auch den Status (aktiviert, festlegen deaktiviert oder abgeblendet) eines Menüelements.  
  
 Mithilfe der **MF_BYPOSITION** Wert erfordert eine Anwendung mit den richtigen `CMenu`. Wenn die `CMenu` des Menüs Leiste verwendet wird, ein Menüelement der obersten Ebene (ein Element in der Menüleiste) betroffen ist. Um den Status eines Elements in einem Popupmenü oder geschachtelte Popupmenü anhand der Position festgelegt, eine Anwendung angeben muss die `CMenu` des Popupmenüs.  
  
 Wenn eine Anwendung gibt der **MF_BYCOMMAND** Flag Windows überprüft alle Popupmenü-Elemente, die untergeordnet sind die `CMenu`; daher, wenn doppelte Menüeinträge vorhanden sind, mithilfe der `CMenu` des Menüs Leiste ist ausreichend.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#25](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 Gibt einen Zeiger auf eine `CMenu` Objekts, dem ein Windows-Handle zu einem Menü.  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Ein Windows-Handle zu einem Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMenu` , die möglicherweise vorübergehend oder dauerhaft.  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine `CMenu` Objekt noch nicht angefügt, das Windows-Menu-Objekt, ein temporäres `CMenu` Objekt erstellt und angefügt.  
  
 Dieser temporäre `CMenu` Objekt ist nur gültig, bis das nächste Mal die Anwendung im Leerlauf Zeit hat, im zugehörigen Ereignisschleife zu diesem Zeitpunkt werden alle temporären Objekte gelöscht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 Bestimmt das Standardmenüelement auf das angegebene Menü an.  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *gmdiFlags*  
 Wert, der angibt, wie die Funktion für Menüelemente durchsucht. Dieser Parameter kann keiner, einer oder einer Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|Gibt an, ist das Standardelement eines, das ein Untermenü geöffnet wird, wird die Funktion die entsprechenden Untermenü rekursiv durchsucht wird. Wenn das Untermenü die Option keine Standardeintrag verfügt, identifiziert der Rückgabewert das Element, das das Untermenü wird geöffnet.<br /><br /> Standardmäßig gibt die Funktion das erste Standardelement für das angegebene Menü, unabhängig davon, ob es ein Element, das ein Untermenü geöffnet wird.|  
|**GMDI_USEDISABLED**|Gibt an, dass die Funktion wird ein Standardelement zurückgeben, selbst wenn er deaktiviert ist.<br /><br /> Standardmäßig überspringt die Funktion deaktiviert oder abgeblendet.|  
  
 `fByPos`  
 Wert, der angibt, ob das Menüelement Bezeichner oder seine Position abzurufen. Wenn dieser Parameter ist **"false"**, der Bezeichner wird zurückgegeben. Andernfalls wird die Position zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert die Bezeichner oder die Position des Menüelements. Wenn die Funktion fehlschlägt, ist der Rückgabewert - 1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 Ruft die Kontexthilfe-ID zugeordnet `CMenu`.  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Kontexthilfe derzeit ID. zugeordnete `CMenu` , falls vorhanden; andernfalls NULL.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 Ruft Informationen für ein Menü ab.  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpcmi`  
 Ein Zeiger auf eine [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) Struktur, die Informationen für das Menü enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ungleich NULL. Andernfalls ist der Rückgabewert 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Abrufen von Informationen über das Menü.  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 Bestimmt die Anzahl der Elemente in einem Menü Popup bzw. der obersten Ebene an.  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in das Menü, wenn die Funktion erfolgreich ist; andernfalls -1.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 Ruft das Menüelement Bezeichner für ein Menüelement befindet sich an der Position definiert werden, indem Sie `nPos`.  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die Position (nullbasiert) des Menüelements, dessen ID abgerufen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Element-ID für das angegebene Element in einem Popup-Menü, wenn die Funktion erfolgreich ausgeführt wird. Wenn das angegebene Element ein Popupmenü (im Gegensatz zu einem Element im Popup-Menü) ist, ist der Rückgabewert-1 zurück. Wenn `nPos` entspricht einem **TRENNZEICHEN** Menüelement, der Rückgabewert ist 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 Ruft Informationen über ein Menüelement ab.  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Bezeichner oder Position des Menüelements zu dem Informationen abgerufen. Die Bedeutung dieses Parameters hängt vom Wert des `ByPos`.  
  
 `lpMenuItemInfo`  
 Ein Zeiger auf eine [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578), wie in der Windows-SDK beschrieben, die Informationen über das Menü enthält.  
  
 `fByPos`  
 Wert, der die Bedeutung des angibt `nIDItem`. Standardmäßig `ByPos` ist **"false"**, gibt diese uItem an eine Menü-Element-ID ist. Wenn `ByPos` nicht festgelegt ist, um **"false"**, es gibt eine Position eines Elements im Menü an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)gemäß der Beschreibung im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten von dem der Win32-Funktion [GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980)gemäß der Beschreibung im Windows SDK. Beachten Sie, dass in der MFC-Implementierung von `GetMenuItemInfo`, können kein Handle für ein Menü.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#26](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 Gibt den Status des angegebenen Menüelements oder die Anzahl der Elemente in einem Popupmenü zurück.  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt die im Menü-Element-ID gemäß `nFlags`.  
  
 `nFlags`  
 Gibt die Art der `nID`. Die folgenden Werte sind möglich:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert 0xFFFFFFFF, wenn das angegebene Element nicht vorhanden ist. Wenn *nId* ein Popupmenü identifiziert das höherwertige Byte enthält die Anzahl der Elemente im Popupmenü und das niedrige Byte enthält das Menü-Flags, die im Popupmenü zugeordnet. Andernfalls ist der Rückgabewert eine Maske (boolesche OR) der Werte in der folgenden Liste (diese Maske beschreibt den Status des Menüs, die Artikel *nId* bezeichnet):  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen auf" angezeigt.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch ist nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement aus, sodass ausgewählt werden kann, und vom abgeblendet Zustand wiederhergestellt werden kann. Beachten Sie, dass der Wert dieser Konstanten 0; eine Anwendung sollte nicht gegen 0 für Fehler testen, wenn dieser Wert verwendet.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass er nicht ausgewählt werden, und es Blendet.  
  
- **MF_MENUBARBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in einer neuen Spalte in Popupmenüs. Die neue Popupmenü-Spalte wird durch eine vertikale Trennlinie aus der alten Spalte getrennt werden.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in einer neuen Spalte in Popupmenüs. Es wird keine Trennlinie zwischen den Spalten platziert.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt. Beachten Sie, dass der Wert dieser Konstanten 0; eine Anwendung sollte nicht gegen 0 für Fehler testen, wenn dieser Wert verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#27](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 Kopiert die Bezeichnung des Menüelements angegebenen in den angegebenen Puffer.  
  
```  
int GetMenuString(
    UINT nIDItem,  
    LPTSTR lpString,  
    int nMaxCount,  
    UINT nFlags) const;  
  
int GetMenuString(
    UINT nIDItem,  
    CString& rString,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nIDItem`  
 Gibt an, der ganzzahlige Bezeichner der dem Menüelement, das oder der Offset des Menüelements im Menü, abhängig vom Wert des `nFlags`.  
  
 `lpString`  
 Verweist auf den Puffer, der die Bezeichnung erhalten.  
  
 `rString`  
 Ein Verweis auf eine `CString` -Objekt, das das kopierte Menüzeichenfolge empfangen.  
  
 `nMaxCount`  
 Gibt die maximale Länge (in Zeichen) der Bezeichnung kopiert werden soll. Wenn die Bezeichnung im angegebenen maximal `nMaxCount`, die zusätzlichen Zeichen werden abgeschnitten.  
  
 `nFlags`  
 Gibt an, die Interpretation der `nIDItem` Parameter. Die folgenden Werte sind möglich:  
  
|nFlags|Interpretation von nIDItem|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die tatsächliche Anzahl von Zeichen in den Puffer, nicht einschließlich das null-Abschlusszeichen kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Die `nMaxCount` Parameter sollte einer größer als die Anzahl der Zeichen in der Bezeichnung, um das Null-Zeichen zu berücksichtigen, der eine Zeichenfolge beendet werden.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getsafehmenu"></a>CMenu::GetSafeHmenu  
 Gibt die `HMENU` von diesem umschlossenen `CMenu` -Objekt, oder ein **NULL** `CMenu` Zeiger.  
  
```  
HMENU GetSafeHmenu() const;  
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="getsubmenu"></a>CMenu::GetSubMenu  
 Ruft die `CMenu` Objekt von einem Popupmenü.  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die Position des Popupmenüs enthalten sind, klicken Sie im Menü. Positionswerte beginnen bei 0 für das erste Menüelement. Das Popupmenü Bezeichner kann in dieser Funktion verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMenu` Objekt, dessen `m_hMenu` Element enthält ein Handle für das Menü das Popupmenü ggf. ein Popupmenü an der angegebenen Position; andernfalls **NULL**. Wenn ein `CMenu` Objekt ist nicht vorhanden, dann eine temporäre wird erstellt. Die `CMenu` zurückgegebenen Zeiger nicht gespeichert werden sollen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::TrackPopupMenu](#trackpopupmenu).  
  
##  <a name="insertmenu"></a>CMenu::InsertMenu  
 Fügt ein neues Menüelement an der angegebenen Position ein `nPosition` und andere Elemente nach unten im Menü.  
  
```  
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL InsertMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt an, dem Menüelement, das vor dem wird das neue Menüelement eingefügt werden. Die `nFlags` Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0. Wenn `nPosition` ist-1 und das neue Menüelement wird am Ende des Menüs angefügt.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` wird interpretiert, und gibt Informationen über den Zustand für das neue Menüelement an, wenn sie zum Menü hinzugefügt wird. Eine Liste der Flags, die festgelegt werden können, finden Sie unter der [AppendMenu](#appendmenu) Memberfunktion. Um mehr als einen Wert anzugeben, verwenden Sie den bitweisen OR-Operator kombiniert sie mit der **MF_BYCOMMAND** oder **MF_BYPOSITION** Flag.  
  
 `nIDNewItem`  
 Gibt an, entweder die Befehls-ID des neuen Menüelements oder, wenn der `nFlags` auf festgelegt ist **MF_POPUP**, das Menü Handle ( `HMENU`) des Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` festgelegt ist, um **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. `nFlags`kann verwendet werden, um interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete verwalten. Dieser 32-Bit-Wert kann für die Anwendung in der **ItemData** Member der Struktur angegeben werden, indem Sie die [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) und [WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923) Nachrichten. Diese Nachrichten werden gesendet, wenn das Menüelement ursprünglich angezeigt wird oder geändert wird.|  
|**MF_STRING**|Enthält einen long-Zeiger auf eine Null-terminierte Zeichenfolge an. Dies ist die Standardinterpretation.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht benötigt).|  
  
 *pBmp*  
 Verweist auf eine `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung kann den Status des Menüelements angeben, durch Festlegen von Werten in `nFlags`.  
  
 Wenn ein Menü befindet, die in einem Fenster (ob das Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`.  
  
 Wenn `nIDNewItem` gibt ein Popupmenü Teil des Menüs in der er eingefügt wird. Wenn das Menü zerstört wird, wird auch das eingefügte Menü zerstört werden. Eine eingefügte Menü sollte vom getrennt werden, ein `CMenu` Objekt, um Konflikte zu vermeiden.  
  
 Wenn der aktiven untergeordneten Fensters der multiple Document Interface (MDI) wird maximiert und einer Anwendung fügt ein Popupmenü Menü der MDI-Anwendung durch Aufrufen dieser Funktion und Angeben der **MF_BYPOSITION** Flag, das Menü wird eingefügt. eine Position weiter links als erwartet. Dies liegt daran, dass das Systemmenü der aktiven untergeordneten MDI-Fensters in der ersten Position der Menüleiste des MDI-Rahmenfensters eingefügt wird. Um das Menü ordnungsgemäß zu positionieren, muss die Anwendung 1 auf den Positionswert hinzuzufügen, die andernfalls verwendet werden würde. Eine Anwendung kann mithilfe der **WM_MDIGETACTIVE** Nachricht, um zu bestimmen, ob es sich bei das derzeit aktiven untergeordneten Fenster maximiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#28](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 Fügt ein neues Menüelement an der angegebenen Position in einem Menü an.  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Finden Sie in der Beschreibung der `uItem` in [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) im Windows SDK.  
  
 `lpMenuItemInfo`  
 Finden Sie in der Beschreibung der `lpmii` in **InsertMenuItem** im Windows SDK.  
  
 `fByPos`  
 Finden Sie in der Beschreibung der `fByPosition` in **InsertMenuItem** im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient als Wrapper [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988), im Windows SDK beschrieben.  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 Lädt eine Menüressource von ausführbare Datei der Anwendung und fügt es der `CMenu` Objekt.  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der die Menüressource laden enthält.  
  
 `nIDResource`  
 Gibt die im Menü-ID für die Menüressource laden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Menüressource erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei ein Menü zugeordnet, wenn das Menü nicht in einem Fenster zugewiesen wird. Eine Anwendung gibt ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#29](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 Lädt eine Ressource aus einer Menüvorlage im im Arbeitsspeicher und fügt es der `CMenu` Objekt.  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 *lpMenuTemplate*  
 Verweist auf eine Menüvorlage (also in einer einzelnen [MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583) Struktur und eine Auflistung von einem oder mehreren [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) Strukturen). Weitere Informationen zu diesen beiden Strukturen finden Sie im Windows-SDK.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Menüressource erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüvorlage ist eine Kopfzeile gefolgt von einer Auflistung von einem oder mehreren [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) Strukturen, von denen jeder kann eine oder mehrere Menüelemente und Popupmenüs enthalten.  
  
 Die Versionsnummer muss 0 sein.  
  
 Die **MtOption** Flags enthalten sollte **MF_END** für das letzte Element in einer Popup-Liste und das letzte Element in der Hauptliste. Finden Sie unter der `AppendMenu` Memberfunktion für andere Flags. Die **MtId** Member muss ausgelassen werden, aus der **MENUITEMTEMPLATE** Struktur Wenn **MF_POPUP** wird angegeben, **MtOption**.  
  
 Den zugewiesenen Speicherplatz für die **MENUITEMTEMPLATE** Struktur muss groß genug für **MtString** um den Namen des Menüelements als Null-terminierte Zeichenfolge aufzunehmen.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei ein Menü zugeordnet, wenn das Menü nicht in einem Fenster zugewiesen wird. Eine Anwendung gibt ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Memberfunktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#30](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 Gibt an, die `HMENU` -Handle für das Windows-Menü angefügt, um die `CMenu` Objekt.  
  
```  
HMENU m_hMenu;  
```  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::LoadMenu](#loadmenu).  
  
##  <a name="measureitem"></a>CMenu::MeasureItem  
 Wird vom Framework aufgerufen, wenn ein Menü mit den Ownerdrawn-Stil erstellt wird.  
  
```  
virtual void MeasureItem(LPMEASUREITEMSTRUCT lpMeasureItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpMeasureItemStruct`  
 Ein Zeiger auf eine `MEASUREITEMSTRUCT` Struktur.  
  
### <a name="remarks"></a>Hinweise  
 Standardmäßig wird diese Memberfunktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und geben Sie die `MEASUREITEMSTRUCT` Struktur, um Windows im Menü Dimensionen zu informieren.  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code stammt aus dem MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing#31](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 Ändert ein vorhandenes Menüelement an der Position gemäß `nPosition`.  
  
```  
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem = 0,  
    LPCTSTR lpszNewItem = NULL);

 
BOOL ModifyMenu(
    UINT nPosition,  
    UINT nFlags,  
    UINT_PTR nIDNewItem,  
    const CBitmap* pBmp);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt an, dem Menüelement, das geändert werden. Die `nFlags` Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` wird interpretiert, und bietet Informationen zu den Änderungen an das Menüelement vorgenommen werden müssen. Eine Liste von Flags, die festgelegt werden können, finden Sie unter der [AppendMenu](#appendmenu) Memberfunktion.  
  
 `nIDNewItem`  
 Gibt an, entweder die Befehls-ID des geänderten Menüelements oder, wenn der `nFlags` festgelegt ist, um **MF_POPUP**, das Handle im Menü ( `HMENU`) eines Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` festgelegt ist, um **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. Die `nFlags` Parameter kann verwendet werden, um interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete verwalten. Dieser 32-Bit-Wert ist für die Anwendung verfügbar, bei der Verarbeitung **MF_MEASUREITEM** und **MF_DRAWITEM**.|  
|**MF_STRING**|Enthält einen long-Zeiger auf eine Null-terminierte Zeichenfolge oder eine `CString`.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht benötigt).|  
  
 *pBmp*  
 Verweist auf eine `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung gibt den neuen Status des Menüelements durch Festlegen von Werten in `nFlags`. Wenn diese Funktion ein Popupmenü die Menüeelement zugeordneten Webseiteninhalte ersetzt, zerstört das alte Popupmenü und gibt den Arbeitsspeicher frei von Popupmenü verwendet.  
  
 Wenn `nIDNewItem` gibt ein Popupmenü Teil des Menüs in der er eingefügt wird. Wenn das Menü zerstört wird, wird auch das eingefügte Menü zerstört werden. Eine eingefügte Menü sollte vom getrennt werden, ein `CMenu` Objekt, um Konflikte zu vermeiden.  
  
 Wenn ein Menü befindet, die in einem Fenster (ob das Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`. Um die Attribute eines vorhandenen Menüelementen zu ändern, ist es wesentlich schneller, verwenden die `CheckMenuItem` und `EnableMenuItem` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 Verwenden Sie diesen Operator das Handle des abzurufenden der `CMenu` Objekt.  
  
```  
operator HMENU() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Erfolg das Handle für die `CMenu` Objekt; andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können das Handle verwenden, Windows-APIs direkt aufrufen.  
  
##  <a name="operator_neq"></a>CMenu::operator! =  
 Bestimmt, ob zwei Menüs logisch nicht gleich sind.  
  
```  
BOOL operator!=(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `menu`  
 Ein `CMenu` zu vergleichende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob ein Menu-Objekt auf der linken Seite nicht gleich einem Menüobjekt im auf der rechten Seite ist.  
  
##  <a name="operator_eq_eq"></a>CMenu::operator ==  
 Bestimmt, ob zwei Menüs logisch gleich sind.  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `menu`  
 Ein `CMenu` zu vergleichende Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob ein Menüobjekt im auf der linken Seite gleich ist (in Form eines der `HMENU` Wert) mit einem Menüobjekt im auf der rechten Seite.  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 Löscht ein Menüelement mit einer zugeordneten Popupmenü aus dem Menü an.  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt an, dem Menüelement, das entfernt werden soll. Die `nFlags` Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Es wird das Handle für ein Popupmenü nicht zerstört, damit das Menü wiederverwendet werden kann. Vor dem Aufrufen dieser Funktion, die Anwendung aufrufen kann die `GetSubMenu` Memberfunktion abzurufenden Popup `CMenu` -Objekt zur Wiederverwendung.  
  
 Wenn ein Menü befindet, die in einem Fenster (ob das Fenster angezeigt wird) geändert wird, muss die Anwendung aufrufen `CWnd::DrawMenuBar`.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setdefaultitem"></a>CMenu::SetDefaultItem  
 Legt das Standardmenüelement für das angegebene Menü fest.  
  
```  
BOOL SetDefaultItem(
    UINT uItem,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Bezeichner oder Position des neuen Standardmenüelement oder -1 für kein Standardelement. Die Bedeutung dieses Parameters hängt vom Wert des `fByPos`.  
  
 `fByPos`  
 Wert, der die Bedeutung des angibt `uItem`. Wenn dieser Parameter ist **"false"**, `uItem` ist eine Element-ID im Menü. Andernfalls ist es eine Position eines Elements im Menü aus.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)gemäß der Beschreibung im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996)gemäß der Beschreibung im Windows SDK.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 Ordnet eine Kontext-Hilfe-ID mit `CMenu`.  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Parameter  
 `dwContextHelpId`  
 Hilfe-Kontext-ID zugeordnet werden soll `CMenu`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente im Menü Freigeben dieser Bezeichner – es ist nicht möglich, die einzelne Menüelemente ein Hilfekontextbezeichner zuordnen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 Legt Informationen für ein Menü an.  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcmi`  
 Ein Zeiger auf eine [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) Struktur, die Informationen für das Menü enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ausgeführt wird, ist der Rückgabewert ungleich NULL. Andernfalls ist der Rückgabewert 0 (null).  
  
### <a name="remarks"></a>Hinweise  
 Mit dieser Funktion wird zum Festlegen der spezifische Informationen über das Menü.  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 Ordnet die angegebene Bitmaps eines Menüelements.  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt an, dem Menüelement, das geändert werden. Die `nFlags` Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des Menüelements vorhandenen enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position des Menüelements vorhandenen enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert wird.  
  
 `pBmpUnchecked`  
 Gibt die Bitmap für Menüelemente verwenden, die nicht mehr überprüft werden.  
  
 `pBmpChecked`  
 Gibt die Bitmap für Menüelemente verwenden, die überprüft werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Ob das Menüelement aktiviert oder deaktiviert ist, wird die entsprechende Bitmap neben dem Menüelement angezeigt.  
  
 Wenn entweder `pBmpUnchecked` oder `pBmpChecked` ist **NULL**, und klicken Sie dann Windows nichts neben dem Menüelement, das für das entsprechende Attribut angezeigt wird. Wenn beide Parameter **NULL**, Windows verwendet das Standard-Häkchen aus, wenn das Element aktiviert ist und Sie auf das Häkchen entfernt, wenn das Element deaktiviert ist.  
  
 Wenn Sie im Menü zerstört wird, werden diese Bitmaps nicht zerstört; die Anwendung muss diese zerstört.  
  
 Die Windows **GetMenuCheckMarkDimensions** Funktion ruft die Dimensionen des Häkchens Standard für Menüelemente verwendet. Die Anwendung verwendet diese Werte bestimmen die geeignete Größe für die Bitmaps angegeben, die mit dieser Funktion. Abrufen der Größe, die Bitmaps erstellen und diese dann festlegen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#32](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing#33](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 Ändert die Informationen über ein Menüelement.  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Finden Sie in der Beschreibung der `uItem` in [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) im Windows SDK.  
  
 `lpMenuItemInfo`  
 Finden Sie in der Beschreibung der `lpmii` in **SetMenuItemInfo** im Windows SDK.  
  
 `fByPos`  
 Finden Sie in der Beschreibung der `fByPosition` in **SetMenuItemInfo** im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion dient als Wrapper [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001), im Windows SDK beschrieben.  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 Ein unverankertes Popupmenü anzeigt, an der angegebenen Position und verfolgt die Auswahl von Elementen im Popupmenü.  
  
```  
BOOL TrackPopupMenu(
    UINT nFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPCRECT lpRect = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `nFlags`  
 Gibt Flags an Bildschirmposition und die Position des Mauszeigers. Finden Sie unter [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) eine Liste der verfügbaren Flags.  
  
 *w*  
 Gibt die horizontale Position in Bildschirmkoordinaten des Popupmenüs an. Abhängig vom Wert der `nFlags` Parameter, klicken Sie im Menü kann sein, linksbündig, rechtsbündig oder zentriert relativ zu dieser Position.  
  
 *y*  
 Gibt die vertikale Position in Bildschirmkoordinaten des oberen Rands des Menüs auf dem Bildschirm an.  
  
 `pWnd`  
 Identifiziert das Fenster, das Menü das Popupmenü besitzt. Dieser Parameter darf nicht sein **NULL**, selbst wenn die **TPM_NONOTIFY** -Flag angegeben ist. In diesem Fenster empfängt alle **WM_COMMAND** Nachrichten aus dem Menü. In Windows-Versionen 3.1 und höher, wird das Fenster nicht empfangen **WM_COMMAND** Nachrichten bis `TrackPopupMenu` zurückgibt. Windows 3.0 wird das Fenster empfängt **WM_COMMAND** Nachrichten vor dem `TrackPopupMenu` zurückgibt.  
  
 `lpRect`  
 Ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt das Ergebnis des Aufrufs [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) im Windows SDK.  
  
### <a name="remarks"></a>Hinweise  
 Eine floating Popupmenü kann an einer beliebigen Stelle auf dem Bildschirm angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing#34](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 Ein unverankertes Popupmenü anzeigt, an der angegebenen Position und verfolgt die Auswahl von Elementen im Popupmenü.  
  
```  
BOOL TrackPopupMenuEx(
    UINT fuFlags,  
    int x,  
    int y,  
    CWnd* pWnd,  
    LPTPMPARAMS lptpm);
```  
  
### <a name="parameters"></a>Parameter  
 `fuFlags`  
 Gibt verschiedene Funktionen für das erweiterte Menü. Eine Liste aller Werte und deren Bedeutung finden Sie unter [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
 *w*  
 Gibt die horizontale Position in Bildschirmkoordinaten des Popupmenüs an.  
  
 *y*  
 Gibt die vertikale Position in Bildschirmkoordinaten des oberen Rands des Menüs auf dem Bildschirm an.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster Popupmenü besitzt und der Empfang der Nachrichten aus dem erstellten Menü. Dieses Fenster kann einem beliebigen Fenster aus der aktuellen Anwendung jedoch nicht mit **NULL**. Bei Angabe von **TPM_NONOTIFY** in der `fuFlags` -Parameter die Funktion sendet keine Nachrichten an `pWnd`. Die Funktion zurück, für das Fenster verweist `pWnd` zum Empfangen der **WM_COMMAND** Nachricht.  
  
 *lptpm*  
 Zeiger auf eine [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586) -Struktur, die einen Bereich des Bildschirms im Menü gibt sollten sich nicht überschneiden. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Angabe von **TPM_RETURNCMD** in der `fuFlags` Parameter, der Rückgabewert ist der Menü-Element-ID des Elements, das der Benutzer ausgewählt. Wenn der Benutzer über das Menü abbricht, ohne eine Auswahl getroffen, oder wenn ein Fehler auftritt, ist der Rückgabewert 0.  
  
 Wenn Sie keinen angeben **TPM_RETURNCMD** in der `fuFlags` Parameter, der zurückgegebene Wert ist ungleich NULL, wenn die Funktion erfolgreich ausgeführt wird und 0, wenn ein Fehler auftritt. Um erweiterte Fehlerinformationen abzurufen, rufen [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Eine floating Popupmenü kann an einer beliebigen Stelle auf dem Bildschirm angezeigt. Weitere Informationen zum Behandeln von Fehlern beim Erstellen der Popupmenüs finden Sie unter [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)   
 [MFC-Beispiel DYNAMENU](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)
