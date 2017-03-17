---
title: CMenu-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
- HMENU
- menus, class
- menus, base class
- menus, creating
- menus, managing
- CMenu class
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
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
ms.openlocfilehash: dcd353bf0be5d23c1782347f54b16a875ed190ed
ms.lasthandoff: 02/24/2017

---
# <a name="cmenu-class"></a>CMenu-Klasse
Eine Kapselung von Windows- `HMENU`.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CMenu : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::CMenu](#cmenu)|Erstellt ein `CMenu`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::AppendMenu](#appendmenu)|Fügt ein neues Element am Ende des Menüs.|  
|[CMenu::Attach](#attach)|Fügt eine Windows-Menü-Handle für ein `CMenu` Objekt.|  
|[CMenu::CheckMenuItem](#checkmenuitem)|Setzt ein Häkchen neben oder entfernt ein Menüelement im Popup-Menü ein Häkchen.|  
|[CMenu::CheckMenuRadioItem](#checkmenuradioitem)|Fügt ein Optionsfeld neben einem Menüelement, und das Optionsfeld aus allen anderen Menüelemente in der Gruppe entfernt.|  
|[CMenu::CreateMenu](#createmenu)|Erstellt ein leeres Menü und fügt es ein `CMenu` Objekt.|  
|[CMenu::CreatePopupMenu](#createpopupmenu)|Erstellt ein leeres Popup-Menü und fügt es ein `CMenu` Objekt.|  
|[:: DeleteMenu auf](#deletemenu)|Löscht ein angegebenes Element aus dem Menü. Weist das Menüelement über ein zugeordnetes Popupmenü, zerstört das Handle zu dem Popup-Menü und den von ihm verwendeten Arbeitsspeicher freigibt.|  
|[CMenu::DeleteTempMap](#deletetempmap)|Löscht alle temporären `CMenu` Objekte erstellt, indem die `FromHandle` -Memberfunktion.|  
|[CMenu::DestroyMenu](#destroymenu)|Zerstört das Menü an der ein `CMenu` -Objekt und, die im Menü belegten Speicher frei.|  
|[CMenu::Detach](#detach)|Ein Windows-Menü-Handle aus trennt eine `CMenu` -Objekt und gibt das Handle zurück.|  
|[CMenu::DrawItem](#drawitem)|Aufgerufen, wenn sich ein Darstellungsaspekt eines ownerdrawn-Menüs ändert.|  
|[CMenu:: EnableMenuItem](#enablemenuitem)|Aktiviert, deaktiviert oder abgeblendet (grau) eines Elements.|  
|[CMenu::FromHandle](#fromhandle)|Gibt einen Zeiger auf eine `CMenu` ein Windows-Menü-Handle-Objekt.|  
|[CMenu::GetDefaultItem](#getdefaultitem)|Bestimmt das Standardmenüelement auf das angegebene Menü.|  
|[CMenu::GetMenuContextHelpId](#getmenucontexthelpid)|Ruft die Hilfekontext-ID mit dem Menü verknüpft ist.|  
|[CMenu::GetMenuInfo](#getmenuinfo)|Ruft Informationen zu einem bestimmten Menü.|  
|[CMenu::GetMenuItemCount](#getmenuitemcount)|Bestimmt die Anzahl der Elemente in einem Menü Popup bzw. der obersten Ebene.|  
|[CMenu::GetMenuItemID](#getmenuitemid)|Ruft den Menüelement Bezeichner für ein Menüelement, das sich an der angegebenen Position befindet.|  
|[CMenu::GetMenuItemInfo](#getmenuiteminfo)|Ruft Informationen über ein Menüelement.|  
|[CMenu::GetMenuState](#getmenustate)|Gibt den Status des angegebenen Elements oder die Anzahl der Elemente in einem Popupmenü zurück.|  
|[CMenu::GetMenuString](#getmenustring)|Ruft die Bezeichnung des angegebenen Elements ab.|  
|[CMenu::GetSafeHmenu](#getsafehmenu)|Gibt die `m_hMenu` von diesem umschlossenen `CMenu` Objekt.|  
|[CMenu::GetSubMenu](#getsubmenu)|Ruft einen Zeiger auf ein Popup-Menü.|  
|[CMenu::InsertMenu](#insertmenu)|Fügt ein neues Menüelement an der angegebenen Position, andere Elemente im Menü verschieben.|  
|[CMenu::InsertMenuItem](#insertmenuitem)|Fügt ein neues Menüelement an der angegebenen Position in einem Menü.|  
|[CMenu::LoadMenu](#loadmenu)|Lädt eine Ressource aus der ausführbaren Datei und fügt es ein `CMenu` Objekt.|  
|[CMenu::LoadMenuIndirect](#loadmenuindirect)|Lädt ein Menü aus einer Menüvorlage im im Arbeitsspeicher und fügt es ein `CMenu` Objekt.|  
|[CMenu::MeasureItem](#measureitem)|Vom Framework aufgerufen wird im Menü Dimensionen zu ermitteln, wann ein Ownerdrawn-Menü erstellt wird.|  
|[CMenu::ModifyMenu](#modifymenu)|Ändert ein vorhandenes Menüelement an der angegebenen Position.|  
|[CMenu::RemoveMenu](#removemenu)|Löscht ein Menüelement mit einer zugeordneten Popupmenü angegebenen aus.|  
|[CMenu::SetDefaultItem](#setdefaultitem)|Legt das Standardmenüelement für das angegebene Menü fest.|  
|[CMenu::SetMenuContextHelpId](#setmenucontexthelpid)|Legt die Hilfekontext-ID im Menü zugeordnet werden.|  
|[CMenu::SetMenuInfo](#setmenuinfo)|Legt die Informationen in einem bestimmten Menü fest.|  
|[CMenu::SetMenuItemBitmaps](#setmenuitembitmaps)|Ordnet die angegebenen Häkchen Bitmaps mit einem Menüelement.|  
|[CMenu::SetMenuItemInfo](#setmenuiteminfo)|Ändern die Informationen zu einem Menüelement.|  
|[CMenu::TrackPopupMenu](#trackpopupmenu)|Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü auf.|  
|[CMenu::TrackPopupMenuEx](#trackpopupmenuex)|Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü auf.|  
  
### <a name="public-operators"></a>Öffentliche Operatoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::operator HMENU](#operator_hmenu)|Ruft das Handle des Menüobjekts im ab.|  
|[CMenu::operator! =](#operator_neq)|Bestimmt, ob zwei Menüobjekte nicht gleich sind.|  
|[CMenu::operator ==](#operator_eq_eq)|Bestimmt, ob zwei Menüobjekte gleich sind.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CMenu::m_hMenu](#m_hmenu)|Gibt das Handle für das Windows-Menü an der der `CMenu` Objekt.|  
  
## <a name="remarks"></a>Hinweise  
 Es stellt Memberfunktionen zum Erstellen, überwachen, aktualisieren und löschen ein Menü bereit.  
  
 Erstellen einer `CMenu` Objekt auf dem Stapelrahmen als lokales, rufen Sie dann `CMenu`Memberfunktionen auf das neue Menü ändern nach Bedarf. Anschließend rufen Sie [CWnd::SetMenu](../../mfc/reference/cwnd-class.md#setmenu) für ein Fenster im Menü festzulegen, unmittelbar gefolgt von einem Aufruf der `CMenu` des Objekts [trennen](#detach) Member-Funktion. Der `CWnd::SetMenu` Member-Funktion legt das Menü des Fensters auf "Neu", wird das Fenster neu gezeichnet werden, um die Änderung im Menü und gibt den Besitz des Menüs an das Fenster. Der Aufruf von **trennen** trennt die `HMENU` aus der `CMenu` Objekt, so bei der lokalen `CMenu` Variable übergibt außerhalb des gültigen Bereichs, der `CMenu` Objektdestruktor versucht nicht, ein Menü zu zerstören, er nicht mehr besitzt. Klicken Sie im Menü selbst automatisch zerstört, wenn das Fenster zerstört wird.  
  
 Können Sie die [LoadMenuIndirect](#loadmenuindirect) Memberfunktion, erstellen Sie ein Menü aus einer Vorlage im Arbeitsspeicher, aber ein Menü erstellt aus einer Ressource durch einen Aufruf von [LoadMenu](#loadmenu) leichter verwaltet wird, und die Ressource selbst erstellt und im Menü-Editor geändert werden.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxwin.h  
  
##  <a name="appendmenu"></a>CMenu::AppendMenu  
 Fügt ein neues Element an das Ende eines Menüs an.  
  
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
 Gibt Informationen über den Status des neuen Menüelements an, wenn sie das Menü hinzugefügt wird. Es besteht aus mindestens einem der Werte im Abschnitt "Hinweise".  
  
 `nIDNewItem`  
 Gibt entweder die Befehls-ID des neuen Menüelements oder, wenn `nFlags` Wert **MF_POPUP**, das Menü Handle ( `HMENU`) eines Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` Wert **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. Die `nFlags` Parameter wird verwendet, interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete zu verwalten. Diese 32-Bit-Wert für die Anwendung verfügbar ist, bei der Verarbeitung `WM_MEASUREITEM` und `WM_DRAWITEM` Nachrichten. Der Wert befindet sich in der **ItemData** Member der Struktur, die mit diesen Nachrichten angegeben.|  
|**MF_STRING**|Enthält einen Zeiger auf eine auf Null endende Zeichenfolge. Dies ist die Standardinterpretation.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht erforderlich).|  
  
 *pBmp*  
 Verweist auf ein `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung kann durch Festlegen von Werten in den Zustand des Menüelements angeben `nFlags`. Wenn `nIDNewItem` gibt ein Popupmenü Teil des Menüs an die es angefügt ist. Wenn das Menü zerstört wird, wird das angefügte Menü ebenfalls gelöscht. Eine angefügte Menü aus getrennt werden soll ein `CMenu` Objekt, um Konflikte zu vermeiden. Beachten Sie, dass **MF_STRING** und `MF_OWNERDRAW` gelten nicht für die Bitmap-Version des `AppendMenu`.  
  
 Die folgende Liste beschreibt die Flags, die festgelegt werden können, in `nFlags`:  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der [SetMenuItemBitmaps](#setmenuitembitmaps) Member-Funktion), die Bitmap "Kontrollkästchen" angezeigt.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch wird nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement, damit es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass es ausgewählt werden kann, und es werden abgeblendet.  
  
- **MF_MENUBARBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in eine neue Spalte in der Popup-Menüs. Die neue Popupmenü-Spalte wird durch eine vertikale Trennlinie von der alten Spalte getrennt werden.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in eine neue Spalte in der Popup-Menüs. Keine Trennlinie wird zwischen den Spalten platziert.  
  
- `MF_OWNERDRAW`Gibt an, dass das Element ein Ownerdrawn-Element. Wenn das Menü zum ersten Mal angezeigt wird, empfängt das Fenster, klicken Sie im Menü besitzt, eine `WM_MEASUREITEM` Nachricht, die die Höhe und Breite des Menüelements abruft. Die `WM_DRAWITEM` Nachricht wird gesendet, wenn der Besitzer das Aussehen des Menüelements aktualisieren muss. Diese Option gilt nicht für ein Menüelement der obersten Ebene.  
  
- **MF_POPUP** gibt an, dass das Menüelement ein Popupmenü zugeordnet wurde. Der ID-Parameter gibt ein Handle für ein Popup-Menü, das dem Element zugeordnet werden soll. Hiermit wird ein Popupmenü-Elements ein Popup-Menü der obersten Ebene oder eine hierarchische Popupmenü hinzugefügt.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.  
  
- **MF_STRING** gibt an, dass das Menüelement eine Zeichenfolge ist.  
  
 Jeder der folgenden Gruppen enthält Flags, die sich gegenseitig und können nicht zusammen verwendet werden:  
  
- **MF_DISABLED**, `MF_ENABLED`, und **MF_GRAYED**  
  
- **MF_STRING**, `MF_OWNERDRAW`, **MF_SEPARATOR**, und die Bitmap-Version  
  
- **MF_MENUBARBREAK** und **MF_MENUBREAK**  
  
- **MF_CHECKED** und **MF_UNCHECKED**  
  
 Wenn ein Menü befindet, die in ein Fenster (oder nicht im Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen, [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="attach"></a>CMenu::Attach  
 Fügt ein vorhandenes Windows-Menü, um ein `CMenu` Objekt.  
  
```  
BOOL Attach(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Gibt ein Handle für ein Windows-Menü an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Vorgang erfolgreich war; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion sollte nicht aufgerufen werden, wenn ein Menü bereits, um angefügt ist die `CMenu` Objekt. Das Menü Handle befindet sich in der `m_hMenu` -Datenmember.  
  
 Wenn das Menü, das Sie bearbeiten möchten bereits mit einem Fenster verbunden ist, können Sie die [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu) Funktion, um ein Handle für das Menü abzurufen.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="checkmenuitem"></a>CMenu::CheckMenuItem  
 Fügt ein Kontrollkästchen, um oder Häkchen von Menüelementen im Popup-Menü entfernt.  
  
```  
UINT CheckMenuItem(
    UINT nIDCheckItem,  
    UINT nCheck);
```  
  
### <a name="parameters"></a>Parameter  
 `nIDCheckItem`  
 Gibt das Menüelement aktiviert, laut `nCheck`.  
  
 `nCheck`  
 Gibt an, wie Sie das Menüelement und zum Feststellen der Position des Elements im Menü. Die `nCheck` Parameter kann eine Kombination von **MF_CHECKED** oder **MF_UNCHECKED** mit **MF_BYPOSITION** oder **MF_BYCOMMAND** Flags. Diese Flags können mit dem bitweisen OR-Operator kombiniert werden. Sie haben folgende Bedeutung:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen.  
  
### <a name="return-value"></a>Rückgabewert  
 Der vorherige Status des Elements: **MF_CHECKED** oder **MF_UNCHECKED**, oder 0xFFFFFFFF, wenn das Menüelement nicht vorhanden war.  
  
### <a name="remarks"></a>Hinweise  
 Die `nIDCheckItem` Parameter gibt die zu ändernden Elements.  
  
 Die `nIDCheckItem` Parameter kann ein Popup-Menü-Element als auch ein Menüelement identifizieren. Keine besonderen Schritte sind erforderlich, um ein Popupmenü-Elements zu überprüfen. Menüelemente der obersten Ebene können nicht überprüft werden. Ein Popup-Menü-Element muss nach Position überprüft werden, da es keinen Menüelement Bezeichner zugeordnet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::GetMenuState](#getmenustate).  
  
##  <a name="checkmenuradioitem"></a>CMenu::CheckMenuRadioItem  
 Überprüft ein angegebenes Menüelement, und macht sie ein Optionsfeld-Element.  
  
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
 Gibt an (als ID oder Offset, abhängig vom Wert der `nFlags`) das letzte Menüelement in der Optionsfeldgruppe.  
  
 `nIDItem`  
 Gibt an (als ID oder Offset, abhängig vom Wert der `nFlags`) das Element in die Gruppe, die mit einem Optionsfeld überprüft werden.  
  
 `nFlags`  
 Gibt die Interpretation der `nIDFirst`, `nIDLast`, und `nIDItem` auf folgende Weise:  
  
|nFlags|Interpretation|  
|------------|--------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; Andernfalls wird 0  
  
### <a name="remarks"></a>Hinweise  
 Zur gleichen Zeit die Funktion deaktiviert alle anderen Menüelemente in der zugehörigen Gruppe und löscht das Radio-Item-Typ-Flag für diese Elemente. Der Eintrag wird mithilfe von Radio Schaltfläche (oder Aufzählungszeichen) Bitmap anstelle einer Bitmap Häkchen angezeigt.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [ON_COMMAND_RANGE](http://msdn.microsoft.com/library/c52719fc-dd6e-48c9-af79-383f48d608e0).  
  
##  <a name="cmenu"></a>CMenu::CMenu  
 Erstellt ein leeres Menü und fügt es ein `CMenu` Objekt.  
  
```  
CMenu();
```  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü wird erst dann erstellt Sie eine der Memberfunktionen erstellen oder Laden von Aufrufen **CMenu:**  
  
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
 Klicken Sie im Menü ist zunächst leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` -Memberfunktion.  
  
 Wenn ein Fenster im Menü zugewiesen wird, wird es automatisch zerstört, wenn das Fenster zerstört wird.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei mit einem Menü verknüpft ist, wenn das Menü eines Fensters nicht zugewiesen ist. Eine Anwendung freigegeben ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#22;](../../mfc/reference/codesnippet/cpp/cmenu-class_2.cpp)]  
  
##  <a name="createpopupmenu"></a>CMenu::CreatePopupMenu  
 Erstellt ein Popup-Menü und fügt es der `CMenu` Objekt.  
  
```  
BOOL CreatePopupMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie im Popupmenü erfolgreich erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü ist zunächst leer. Menüelemente können hinzugefügt werden, mithilfe der `AppendMenu` oder `InsertMenu` -Memberfunktion. Die Anwendung kann zu einer vorhandenen Menüs oder das Popup-Menü im Popupmenü hinzufügen. Der `TrackPopupMenu` Member-Funktion kann verwendet werden, um dieses Menü als Gleitkommazahl Popupmenü anzuzeigen und die Auswahl im Popupmenü nachverfolgen.  
  
 Wenn ein Fenster im Menü zugewiesen wird, wird es automatisch zerstört, wenn das Fenster zerstört wird. Wenn das Menü eines vorhandenen Menüs hinzugefügt wird, wird es automatisch zerstört, wenn das Menü zerstört wird.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei ein Popup-Menü zugeordnet ist, wenn das Menü eines Fensters nicht zugewiesen ist. Eine Anwendung freigegeben ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="deletemenu"></a>:: DeleteMenu auf  
 Löscht ein Element aus dem Menü.  
  
```  
BOOL DeleteMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt das Menüelement, das gelöscht werden, laut `nFlags`.  
  
 `nFlags`  
 Wird verwendet, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Das Menüelement besitzt ein zugeordnetes Popupmenü `DeleteMenu` zerstört das Handle zu dem Popup-Menü und gibt den Arbeitsspeicher frei von Popup-Menü verwendet.  
  
 Wenn ein Menü befindet, die in ein Fenster (oder nicht im Fenster angezeigt wird) geändert wird, muss die Anwendung aufrufen [CWnd::DrawMenuBar](../../mfc/reference/cwnd-class.md#drawmenubar).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="deletetempmap"></a>CMenu::DeleteTempMap  
 Automatisch aufgerufen, der `CWinApp` Zeit im Leerlauf Ereignishandler, löscht alle temporären `CMenu` Objekte erstellt, indem der [FromHandle](#fromhandle) Member-Funktion.  
  
```  
static void PASCAL DeleteTempMap();
```  
  
### <a name="remarks"></a>Hinweise  
 `DeleteTempMap`trennt das Windows-Menü-Objekt angefügt an einen temporären `CMenu` Objekt vor dem Löschen der `CMenu` Objekt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&23;](../../mfc/reference/codesnippet/cpp/cmenu-class_3.cpp)]  
  
##  <a name="destroymenu"></a>CMenu::DestroyMenu  
 Zerstört das Menü und alle Windows-Ressourcen, die verwendet wurden.  
  
```  
BOOL DestroyMenu();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Menü zerstört wird; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Klicken Sie im Menü wird getrennt von den `CMenu` -Objekt, bevor es zerstört wird. Windows `DestroyMenu` Funktion wird automatisch aufgerufen, dem `CMenu` Destruktor.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="detach"></a>CMenu::Detach  
 Trennt eine Windows-Menü ein `CMenu` -Objekt und gibt das Handle zurück.  
  
```  
HMENU Detach();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle des Typs `HMENU`, einem Windows-Menü, wenn erfolgreich, andernfalls **NULL**.  
  
### <a name="remarks"></a>Hinweise  
 Die `m_hMenu` -Datenmember festgelegt ist, um **NULL**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&21;](../../mfc/reference/codesnippet/cpp/cmenu-class_1.cpp)]  
  
##  <a name="drawitem"></a>CMenu::DrawItem  
 Aufgerufen, wenn sich ein Darstellungsaspekt eines ownerdrawn-Menüs ändert.  
  
```  
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```  
  
### <a name="parameters"></a>Parameter  
 `lpDrawItemStruct`  
 Ein Zeiger auf eine [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) -Struktur, die Informationen über den Typ der erforderlichen Zeichnung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Die `itemAction` Mitglied der `DRAWITEMSTRUCT` Struktur definiert die Zeichnen-Aktion, die ausgeführt werden soll. Überschreiben Sie diese Memberfunktion zum Implementieren der Zeichnung für eine Ownerdrawn- `CMenu` Objekt. Die Anwendung sollte alle Grafiken Device Interface (GDI) Objekte ausgewählt, für der Anzeigekontext im angegebenen wiederherstellen `lpDrawItemStruct` vor dem Beenden von dieser Memberfunktion.  
  
 Finden Sie unter [CWnd::OnDrawItem](../../mfc/reference/cwnd-class.md#ondrawitem) eine Beschreibung der `DRAWITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code stammt aus der MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#24;](../../mfc/reference/codesnippet/cpp/cmenu-class_4.cpp)]  
  
##  <a name="enablemenuitem"></a>CMenu:: EnableMenuItem  
 Aktiviert, deaktiviert oder ein Menüelement abgeblendet.  
  
```  
UINT EnableMenuItem(
    UINT nIDEnableItem,  
    UINT nEnable);
```  
  
### <a name="parameters"></a>Parameter  
 *nIDEnableItem*  
 Gibt das Menüelement aktiviert ist, wird `nEnable`. Dieser Parameter kann Popup-Menü-Elemente sowie Standardmenüelementen angeben.  
  
 `nEnable`  
 Gibt die auszuführende Aktion an. Es kann eine Kombination von **MF_DISABLED**, `MF_ENABLED`, oder **MF_GRAYED**, mit **MF_BYCOMMAND** oder **MF_BYPOSITION**. Diese Werte können mit dem bitweisen OR-Operator kombiniert werden. Diese Werte haben folgende Bedeutung:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch wird nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement, damit es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass es ausgewählt werden kann, und es werden abgeblendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Vorherigen Status ( **MF_DISABLED**, `MF_ENABLED`, oder **MF_GRAYED**) oder -1, wenn er nicht gültig ist.  
  
### <a name="remarks"></a>Hinweise  
 Die [CreateMenu](#createmenu), [InsertMenu](#insertmenu), [ModifyMenu](#modifymenu), und [LoadMenuIndirect](#loadmenuindirect) Memberfunktionen können auch den Status (aktiviert, deaktiviert oder abgeblendet) eines Menüelements festlegen.  
  
 Mithilfe der **MF_BYPOSITION** Wert erfordert, dass eine Anwendung den richtigen `CMenu`. Wenn die `CMenu` des Menüs Leiste verwendet wird, ein Menüelement der obersten Ebene (ein Element in der Menüleiste) betroffen ist. Um den Status eines Elements in einem Popupmenü oder geschachtelte Popupmenü Position festzulegen, muss eine Anwendung angeben der `CMenu` des Popupmenüs.  
  
 Wenn eine Anwendung gibt der **MF_BYCOMMAND** Flag Windows überprüft alle Popup-Menü-Elemente, die untergeordnet sind die `CMenu`, daher, wenn doppelte Elemente vorhanden sind, verwenden die `CMenu` des Menüs Leiste ausreichend ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#25;](../../mfc/reference/codesnippet/cpp/cmenu-class_5.cpp)]  
  
##  <a name="fromhandle"></a>CMenu::FromHandle  
 Gibt einen Zeiger auf ein `CMenu` Objekt, das ein Windows-Handle zu einem Menü erhalten.  
  
```  
static CMenu* PASCAL FromHandle(HMENU hMenu);
```  
  
### <a name="parameters"></a>Parameter  
 `hMenu`  
 Ein Windows-Handle zu einem Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMenu` temporär oder permanent sein können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein `CMenu` Objekt noch nicht angefügt, das Windows-Menü-Objekt, ein temporäres `CMenu` Objekt erstellt und angefügt wird.  
  
 Dieser temporäre `CMenu` Objekt ist nur gültig, bis das nächste Mal die Anwendung hat Leerlaufzeit in die Ereignisschleife zu diesem Zeitpunkt werden alle temporären Objekte gelöscht.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::CreateMenu](#createmenu).  
  
##  <a name="getdefaultitem"></a>CMenu::GetDefaultItem  
 Bestimmt das Standardmenüelement auf das angegebene Menü.  
  
```  
UINT GetDefaultItem(
    UINT gmdiFlags,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 *gmdiFlags*  
 Wert, der angibt, wie die Funktion für Menüelemente durchsucht. Dieser Parameter kann keine, eine oder eine Kombination der folgenden Werte sein:  
  
|Wert|Bedeutung|  
|-----------|-------------|  
|**GMDI_GOINTOPOPUPS**|Gibt an, ist das Standardelement eines, das ein Untermenü geöffnet wird, die Funktion wird die entsprechenden Untermenü rekursiv durchsucht. Wenn im Untermenü kein Standardelement besitzt, identifiziert der Rückgabewert das Element, das das Untermenü wird geöffnet.<br /><br /> Standardmäßig gibt die Funktion das erste Standardelement im angegebenen Menü, unabhängig davon, ob es ein Element, das ein Untermenü geöffnet wird.|  
|**GMDI_USEDISABLED**|Gibt an, dass die Funktion ein Standardelement zurückgeben, auch wenn er deaktiviert ist.<br /><br /> Standardmäßig überspringt die Funktion deaktiviert oder abgeblendet.|  
  
 `fByPos`  
 Wert, der angibt, ob das Menüelement Bezeichner oder die Position abgerufen. Wenn dieser Parameter **FALSE**, der Bezeichner wird zurückgegeben. Andernfalls wird die Position zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert die ID oder die Position des Menüelements. Wenn die Funktion fehlschlägt, ist der zurückgegebene Wert - 1.  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [GetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647976), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenucontexthelpid"></a>CMenu::GetMenuContextHelpId  
 Ruft die ID des Kontexthilfe `CMenu`.  
  
```  
DWORD GetMenuContextHelpId() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Kontexthilfe aktuell ID. zugeordnete `CMenu` , wenn vorhanden, andernfalls&0;.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuinfo"></a>CMenu::GetMenuInfo  
 Ruft Informationen für ein Menü ab.  
  
```  
BOOL GetMenuInfo(LPMENUINFO lpcmi) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `lpcmi`  
 Ein Zeiger auf eine [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) -Struktur, die Informationen für das Menü enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Andernfalls ist der Rückgabewert&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion zum Abrufen von Informationen über das Menü.  
  
##  <a name="getmenuitemcount"></a>CMenu::GetMenuItemCount  
 Bestimmt die Anzahl der Elemente in einem Menü Popup bzw. der obersten Ebene.  
  
```  
UINT GetMenuItemCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Elemente in das Menü, wenn die Funktion erfolgreich ist; andernfalls-1.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CWnd::GetMenu](../../mfc/reference/cwnd-class.md#getmenu).  
  
##  <a name="getmenuitemid"></a>CMenu::GetMenuItemID  
 Der Menüelemente Bezeichner für ein Menüelement, der durch definierten Position am `nPos`.  
  
```  
UINT GetMenuItemID(int nPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die Position (nullbasiert) des Menüelements, dessen ID abgerufen wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Die Element-ID für das angegebene Element in einem Popup-Menü, wenn die Funktion erfolgreich ist. Wenn das angegebene Element ein Popupmenü (im Gegensatz zu einem Element im Popup-Menü) ist, ist der Rückgabewert –&1;. Wenn `nPos` entspricht einer **TRENNZEICHEN** Menüelement, der Rückgabewert ist 0.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="getmenuiteminfo"></a>CMenu::GetMenuItemInfo  
 Ruft Informationen über ein Menüelement.  
  
```  
BOOL GetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Bezeichner oder Position des Menüelements zu dem Informationen abgerufen. Die Bedeutung dieses Parameters hängt vom Wert der `ByPos`.  
  
 `lpMenuItemInfo`  
 Ein Zeiger auf eine [MENUITEMINFO](http://msdn.microsoft.com/library/windows/desktop/ms647578), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], Informationen über das Menü enthält.  
  
 `fByPos`  
 Wert festlegen die Bedeutung der `nIDItem`. In der Standardeinstellung `ByPos` ist **FALSE**, gibt an, uItem ein Menübezeichner ist. Wenn `ByPos` nicht festgelegt ist, um **FALSE**, es gibt eine Position eines Elements im Menü an.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion, die das Verhalten der von der Win32-Funktion [GetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms647980), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Beachten Sie, dass in der MFC-Implementierung von `GetMenuItemInfo`, verwenden Sie ein Handle zu einem Menü.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#26;](../../mfc/reference/codesnippet/cpp/cmenu-class_6.cpp)]  
  
##  <a name="getmenustate"></a>CMenu::GetMenuState  
 Gibt den Status des angegebenen Elements oder die Anzahl der Elemente in einem Popupmenü zurück.  
  
```  
UINT GetMenuState(
    UINT nID,  
    UINT nFlags) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nID`  
 Gibt die Element-ID, laut `nFlags`.  
  
 `nFlags`  
 Gibt die Art der `nID`. Die folgenden Werte sind möglich:  
  
- **MF_BYCOMMAND** gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung.  
  
- **MF_BYPOSITION** gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert 0xFFFFFFFF, wenn das angegebene Element nicht vorhanden ist. Wenn *nId* identifiziert ein Popup-Menü, das höherwertige Byte enthält die Anzahl der Elemente im Popup-Menü und das niedrige Byte der Menü-Flags, die im Popupmenü zugeordnet. Andernfalls ist der Rückgabewert einer Maske (boolesche oder) der Werte aus der folgenden Liste (diese Maske beschreibt den Status des Menüs, die Artikel *nId* bezeichnet):  
  
- **MF_CHECKED** fungiert als eine Umschaltfläche mit **MF_UNCHECKED** das Standard-Häkchen neben dem Element platzieren. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Kontrollkästchen" angezeigt.  
  
- **MF_DISABLED** wird das Menüelement deaktiviert, sodass es nicht ausgewählt werden, jedoch wird nicht abgeblendet.  
  
- `MF_ENABLED`Können das Menüelement, damit es ausgewählt werden kann und vom abgeblendet Zustand wiederhergestellt. Beachten Sie, dass der Wert dieser Konstanten 0 ist. eine Anwendung sollte gegen 0 für Fehler nicht testen, wenn dieser Wert verwendet.  
  
- **MF_GRAYED** wird das Menüelement deaktiviert, sodass es ausgewählt werden kann, und es werden abgeblendet.  
  
- **MF_MENUBARBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in eine neue Spalte in der Popup-Menüs. Die neue Popupmenü-Spalte wird durch eine vertikale Trennlinie von der alten Spalte getrennt werden.  
  
- **MF_MENUBREAK** platziert das Element in einer neuen Zeile in statischen Menüs oder in eine neue Spalte in der Popup-Menüs. Keine Trennlinie wird zwischen den Spalten platziert.  
  
- **MF_SEPARATOR** zeichnet eine horizontale Trennlinie. Kann nur in einem Popupmenü verwendet werden. Diese Zeile kann nicht abgeblendet, deaktiviert oder hervorgehoben werden. Andere Parameter werden ignoriert.  
  
- **MF_UNCHECKED** fungiert als eine Umschaltfläche mit **MF_CHECKED** ein Häkchen neben dem Element zu entfernen. Wenn die Anwendung Häkchen Bitmaps bereitstellt (finden Sie unter der `SetMenuItemBitmaps` Member-Funktion), die Bitmap "Häkchen deaktiviert" angezeigt. Beachten Sie, dass der Wert dieser Konstanten 0 ist. eine Anwendung sollte gegen 0 für Fehler nicht testen, wenn dieser Wert verwendet.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#27;](../../mfc/reference/codesnippet/cpp/cmenu-class_7.cpp)]  
  
##  <a name="getmenustring"></a>CMenu::GetMenuString  
 Kopiert die Bezeichnung des angegebenen Elements in den angegebenen Puffer.  
  
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
 Gibt den ganzzahligen Bezeichner des Menüelements oder der Offset des Menüelements im Menü abhängig vom Wert `nFlags`.  
  
 `lpString`  
 Verweist auf den Puffer, der die Bezeichnung erhalten.  
  
 `rString`  
 Ein Verweis auf ein `CString` -Objekt, das die kopierte Menüzeichenfolge zu erhalten.  
  
 `nMaxCount`  
 Gibt die maximale Länge (in Zeichen) der Bezeichnung kopiert werden soll. Wenn die Bezeichnung den Höchstwert überschreitet `nMaxCount`, die zusätzlichen Zeichen werden abgeschnitten.  
  
 `nFlags`  
 Gibt die Interpretation der `nIDItem` Parameter. Die folgenden Werte sind möglich:  
  
|nFlags|Interpretation von nIDItem|  
|------------|-------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die tatsächliche Anzahl der Zeichen, die in den Puffer, nicht einschließlich des null-Abschlusszeichens kopiert.  
  
### <a name="remarks"></a>Hinweise  
 Die `nMaxCount` Parameter sollte einer größer als die Anzahl der Zeichen in einem Feld, das Null-Zeichen zu ermöglichen, die eine Zeichenfolge beendet werden.  
  
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
 Ruft die `CMenu` Objekt ein Popup-Menü.  
  
```  
CMenu* GetSubMenu(int nPos) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `nPos`  
 Gibt die Position des Popupmenüs im Menü enthalten. Positionswerte beginnen bei 0 für das erste Menüelement. In dieser Funktion kann das Popupmenü Bezeichner verwendet werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Zeiger auf eine `CMenu` -Objekt, dessen `m_hMenu` Element enthält ein Handle für das Popupmenü ggf. ein Popup-Menü an der angegebenen Position; andernfalls **NULL**. Wenn ein `CMenu` Objekt nicht vorhanden, wird eine temporäre Datei wird erstellt. Die `CMenu` zurückgegebenen Zeiger sollten nicht gespeichert werden.  
  
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
 Gibt das Menüelement vor dem wird das neue Menüelement eingefügt werden. Die `nFlags` -Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0. Wenn `nPosition` –&1; ist, wird das neue Menüelement wird am Ende des Menüs angefügt.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert, und gibt Informationen über den Zustand des neuen Menüelements, wenn es im Menü hinzugefügt wird. Eine Liste der Flags, die festgelegt werden können, finden Sie unter der [AppendMenu](#appendmenu) Member-Funktion. Um mehr als einen Wert angeben, mit der bitweisen OR-Operator kombiniert werden, mit der **MF_BYCOMMAND** oder **MF_BYPOSITION** Flag.  
  
 `nIDNewItem`  
 Gibt entweder die Befehls-ID des neuen Menüelements oder, wenn `nFlags` Wert **MF_POPUP**, das Menü Handle ( `HMENU`) des Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` Wert **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. `nFlags`kann zum Interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete zu verwalten. Diese 32-Bit-Wert steht für die Anwendung in der **ItemData** Member der Struktur vom der [WM_MEASUREITEM](http://msdn.microsoft.com/library/windows/desktop/bb775925) und [WM_DRAWITEM](http://msdn.microsoft.com/library/windows/desktop/bb775923) Nachrichten. Diese Nachrichten werden gesendet, wenn das Menüelement zunächst angezeigt wird oder geändert wird.|  
|**MF_STRING**|Enthält einen long-Zeiger auf eine auf Null endende Zeichenfolge. Dies ist die Standardinterpretation.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht erforderlich).|  
  
 *pBmp*  
 Verweist auf ein `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung kann durch Festlegen von Werten in den Zustand des Menüelements angeben `nFlags`.  
  
 Wenn ein Menü befindet, die in ein Fenster (oder nicht im Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`.  
  
 Wenn `nIDNewItem` gibt ein Popupmenü Teil des Menüs in der er eingefügt wird. Wenn das Menü zerstört wird, werden die eingefügte Menü auch zerstört. Ein eingefügten Menü sollte vom getrennt werden, ein `CMenu` Objekt, um Konflikte zu vermeiden.  
  
 Wenn der aktiven untergeordneten Fenster der multiple Document Interface (MDI) wird maximiert und einer Anwendung fügt ein Popupmenü Menü der MDI-Anwendung durch Aufrufen dieser Funktion und Angeben der **MF_BYPOSITION** -Flag, das Menü ist eine Position weiter nach links als erwartet eingefügt. Dies liegt daran, dass das Systemmenü des aktiven untergeordneten MDI-Fenster in der ersten Position der Menüleiste des MDI-Rahmenfensters eingefügt wird. Um das Menü ordnungsgemäß zu positionieren, muss die Anwendung 1 auf den Positionswert hinzuzufügen, die ansonsten verwendet würden. Eine Anwendung kann mithilfe der **WM_MDIGETACTIVE** Nachricht zu bestimmen, ob es sich bei das derzeit aktiven untergeordneten Fenster maximiert ist.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#28;](../../mfc/reference/codesnippet/cpp/cmenu-class_8.cpp)]  
  
##  <a name="insertmenuitem"></a>CMenu::InsertMenuItem  
 Fügt ein neues Menüelement an der angegebenen Position in einem Menü.  
  
```  
BOOL InsertMenuItem(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Finden Sie in der Beschreibung der `uItem` in [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpMenuItemInfo`  
 Finden Sie in der Beschreibung der `lpmii` in **InsertMenuItem** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `fByPos`  
 Finden Sie in der Beschreibung der `fByPosition` in **InsertMenuItem** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion umfasst [InsertMenuItem](http://msdn.microsoft.com/library/windows/desktop/ms647988), beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="loadmenu"></a>CMenu::LoadMenu  
 Lädt eine Ressource aus der ausführbaren Datei der Anwendung und fügt es der `CMenu` Objekt.  
  
```  
BOOL LoadMenu(LPCTSTR lpszResourceName);  
BOOL LoadMenu(UINT nIDResource);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszResourceName`  
 Zeigt auf eine auf Null endende Zeichenfolge, die den Namen der Menüressource laden enthält.  
  
 `nIDResource`  
 Gibt die ID der Menüressource im geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Ressource erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei mit einem Menü verknüpft ist, wenn das Menü eines Fensters nicht zugewiesen ist. Eine Anwendung freigegeben ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#29;](../../mfc/reference/codesnippet/cpp/cmenu-class_9.cpp)]  
  
##  <a name="loadmenuindirect"></a>CMenu::LoadMenuIndirect  
 Lädt eine Ressource aus einer Menüvorlage im im Arbeitsspeicher und fügt es der `CMenu` Objekt.  
  
```  
BOOL LoadMenuIndirect(const void* lpMenuTemplate);
```  
  
### <a name="parameters"></a>Parameter  
 *lpMenuTemplate*  
 Verweist auf eine Menüvorlage im (Dies ist eine einzelne [MENUITEMTEMPLATEHEADER](http://msdn.microsoft.com/library/windows/desktop/ms647583) Struktur und eine Auflistung von einem oder mehreren [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) Strukturen). Weitere Informationen zu diesen beiden Strukturen, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Ressource erfolgreich geladen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Menüvorlage im wird ein Header, gefolgt von einer Auflistung von einem oder mehreren [MENUITEMTEMPLATE](http://msdn.microsoft.com/library/windows/desktop/ms647581) -Strukturen kann jeweils eine oder mehrere Menüelemente und Popupmenüs enthalten.  
  
 Die Versionsnummer muss 0 sein.  
  
 Die **MtOption** Flags sollen **MF_END** für das letzte Element in einer Popup-Liste und das letzte Element in der Hauptliste aus. Finden Sie unter der `AppendMenu` Member-Funktion für andere Flags. Die **MtId** Member muss weggelassen werden, aus der **MENUITEMTEMPLATE** Struktur bei **MF_POPUP** angegeben ist, **MtOption**.  
  
 Der Speicherplatz für die **MENUITEMTEMPLATE** Struktur muss groß genug sein **MtString** den Namen des Menüelements als Null-terminierte Zeichenfolge enthalten.  
  
 Vor dem Beenden, muss eine Anwendung geben Sie Systemressourcen frei mit einem Menü verknüpft ist, wenn das Menü eines Fensters nicht zugewiesen ist. Eine Anwendung freigegeben ein Menü durch Aufrufen der [DestroyMenu](#destroymenu) Member-Funktion.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#30;](../../mfc/reference/codesnippet/cpp/cmenu-class_10.cpp)]  
  
##  <a name="m_hmenu"></a>CMenu::m_hMenu  
 Gibt die `HMENU` an der Handle für das Windows-Menü die `CMenu` Objekt.  
  
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
 Standardmäßig wird dieser Member-Funktion keine Aktion ausgeführt. Überschreiben Sie diese Memberfunktion auf, und füllen Sie die `MEASUREITEMSTRUCT` Struktur, um Windows im Menü Dimensionen zu informieren.  
  
 Finden Sie unter [CWnd::OnMeasureItem](../../mfc/reference/cwnd-class.md#onmeasureitem) eine Beschreibung der `MEASUREITEMSTRUCT` Struktur.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code stammt aus der MFC [CTRLTEST](../../visual-cpp-samples.md) Beispiel:  
  
 [!code-cpp[NVC_MFCWindowing&#31;](../../mfc/reference/codesnippet/cpp/cmenu-class_11.cpp)]  
  
##  <a name="modifymenu"></a>CMenu::ModifyMenu  
 Ändert ein vorhandenes Menüelement an der angegebenen Position `nPosition`.  
  
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
 Gibt das Menüelement geändert werden. Die `nFlags` -Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert, und erhalten Sie Informationen zu den Änderungen des Menüelements vorgenommen werden. Eine Liste mit Flags, die festgelegt werden können, finden Sie unter der [AppendMenu](#appendmenu) Member-Funktion.  
  
 `nIDNewItem`  
 Gibt entweder die Befehls-ID des Menüelements geänderte oder, wenn `nFlags` Wert **MF_POPUP**, das Handle im Menü ( `HMENU`) eines Popupmenüs. Die `nIDNewItem` Parameter wird ignoriert (nicht erforderlich), wenn `nFlags` Wert **MF_SEPARATOR**.  
  
 `lpszNewItem`  
 Gibt den Inhalt des neuen Menüelements. Die `nFlags` -Parameter kann verwendet werden, um interpretieren `lpszNewItem` auf folgende Weise:  
  
|nFlags|Interpretation von lpszNewItem|  
|------------|-----------------------------------|  
|`MF_OWNERDRAW`|Enthält einen von der Anwendung bereitgestellten 32-Bit-Wert, den die Anwendung verwenden kann, um zusätzliche Daten, die dem Menüelement zugeordnete zu verwalten. Diese 32-Bit-Wert für die Anwendung verfügbar ist, bei der Verarbeitung **MF_MEASUREITEM** und **MF_DRAWITEM**.|  
|**MF_STRING**|Enthält einen long-Zeiger auf eine auf Null endende Zeichenfolge oder eine `CString`.|  
|**MF_SEPARATOR**|Die `lpszNewItem` Parameter wird ignoriert (nicht erforderlich).|  
  
 *pBmp*  
 Verweist auf ein `CBitmap` -Objekt, das als das Menüelement verwendet wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Die Anwendung gibt den neuen Status des Menüelements durch Festlegen von Werten in `nFlags`. Wenn diese Funktion ein Popupmenü mit dem Menüelement zugeordnete ersetzt, löscht die alten Popupmenü und den Speicher frei, von dem Popup-Menü verwendet.  
  
 Wenn `nIDNewItem` gibt ein Popupmenü Teil des Menüs in der er eingefügt wird. Wenn das Menü zerstört wird, werden die eingefügte Menü auch zerstört. Ein eingefügten Menü sollte vom getrennt werden, ein `CMenu` Objekt, um Konflikte zu vermeiden.  
  
 Wenn ein Menü befindet, die in ein Fenster (oder nicht im Fenster angezeigt wird) geändert wird, sollte die Anwendung aufrufen `CWnd::DrawMenuBar`. Um die Attribute eines vorhandenen Menüelementen zu ändern, es ist viel schneller, die `CheckMenuItem` und `EnableMenuItem` Memberfunktionen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="operator_hmenu"></a>CMenu::operator HMENU  
 Verwenden Sie diesen Operator, um das Handle des dem `CMenu` Objekt.  
  
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
 Ein `CMenu` Objekt für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob ein Menüobjekt im auf der linken Seite nicht gleich einem Menüobjekt im auf der rechten Seite ist.  
  
##  <a name="operator_eq_eq"></a>CMenu::operator ==  
 Bestimmt, ob zwei Menüs logisch gleich sind.  
  
```  
BOOL operator==(const CMenu& menu) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `menu`  
 Ein `CMenu` Objekt für den Vergleich.  
  
### <a name="remarks"></a>Hinweise  
 Testet, ob ein Menüobjekt im auf der linken Seite gleich ist (im Sinne von der `HMENU` Wert) auf ein Menüobjekt im auf der rechten Seite.  
  
##  <a name="removemenu"></a>CMenu::RemoveMenu  
 Löscht ein Menüelement mit einer zugeordneten Popup-Menü aus dem Menü.  
  
```  
BOOL RemoveMenu(
    UINT nPosition,  
    UINT nFlags);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt das Menüelement entfernt werden soll. Die `nFlags` -Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert wird.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Es wird das Handle für ein Popup-Menü nicht zerstört, damit das Menü wiederverwendet werden kann. Vor dem Aufrufen dieser Funktion kann die Anwendung Aufrufen der `GetSubMenu` Member-Funktion zum Abrufen des Popups `CMenu` -Objekt zur Wiederverwendung.  
  
 Wenn ein Menü befindet, die in einem Fenster (oder nicht im Fenster angezeigt wird) geändert wird, muss die Anwendung aufrufen `CWnd::DrawMenuBar`.  
  
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
 Bezeichner oder Position des neuen Standardmenüelement oder -1 für kein Standardelement. Die Bedeutung dieses Parameters hängt vom Wert der `fByPos`.  
  
 `fByPos`  
 Wert festlegen die Bedeutung der `uItem`. Wenn dieser Parameter **FALSE**, `uItem` ist ein Bezeichner im Menü. Andernfalls ist es eine Position eines Elements im Menü.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Wenn die Funktion fehlerhaft ist, ist der Rückgabewert null. Um erweiterte Fehlerinformationen abzurufen, verwenden Sie die Win32-Funktion [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Memberfunktion implementiert das Verhalten der Win32-Funktion [SetMenuDefaultItem](http://msdn.microsoft.com/library/windows/desktop/ms647996), wie in beschrieben die [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenucontexthelpid"></a>CMenu::SetMenuContextHelpId  
 Ordnet eine Kontext-Hilfe-ID mit `CMenu`.  
  
```  
BOOL SetMenuContextHelpId(DWORD dwContextHelpId);
```  
  
### <a name="parameters"></a>Parameter  
 `dwContextHelpId`  
 Kontext-Hilfe-ID zugeordnet `CMenu`.  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL bei Erfolg; Andernfalls wird 0  
  
### <a name="remarks"></a>Hinweise  
 Alle Elemente im Menü Freigeben dieser Bezeichner – es ist nicht möglich, eine Hilfekontextbezeichner an die einzelnen Elemente anfügen.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [CMenu::InsertMenu](#insertmenu).  
  
##  <a name="setmenuinfo"></a>CMenu::SetMenuInfo  
 Legt Informationen für ein Menü fest.  
  
```  
BOOL SetMenuInfo(LPCMENUINFO lpcmi);
```  
  
### <a name="parameters"></a>Parameter  
 `lpcmi`  
 Ein Zeiger auf eine [MENUINFO](http://msdn.microsoft.com/library/windows/desktop/ms647575) -Struktur, die Informationen für das Menü enthält.  
  
### <a name="return-value"></a>Rückgabewert  
 Wenn die Funktion erfolgreich ist, ist der Rückgabewert ungleich NULL. Andernfalls ist der Rückgabewert&0; (null).  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion, um spezifische Informationen über das Menü festlegen.  
  
##  <a name="setmenuitembitmaps"></a>CMenu::SetMenuItemBitmaps  
 Ordnet die angegebenen Bitmaps mit einem Menüelement.  
  
```  
BOOL SetMenuItemBitmaps(
    UINT nPosition,  
    UINT nFlags,  
    const CBitmap* pBmpUnchecked,  
    const CBitmap* pBmpChecked);
```  
  
### <a name="parameters"></a>Parameter  
 `nPosition`  
 Gibt das Menüelement geändert werden. Die `nFlags` -Parameter kann verwendet werden, um interpretieren `nPosition` auf folgende Weise:  
  
|nFlags|Interpretation von nPosition|  
|------------|---------------------------------|  
|**MF_BYCOMMAND**|Gibt an, dass der Parameter die Befehls-ID des vorhandenen Menüelements enthält. Dies ist die Standardeinstellung, wenn weder **MF_BYCOMMAND** noch **MF_BYPOSITION** festgelegt ist.|  
|**MF_BYPOSITION**|Gibt an, dass der Parameter die Position von vorhandenen Eintrag enthält. Das erste Element ist an Position 0.|  
  
 `nFlags`  
 Gibt an, wie `nPosition` interpretiert wird.  
  
 `pBmpUnchecked`  
 Gibt die Bitmap für Menüelemente verwendet, die nicht ausgecheckt sind.  
  
 `pBmpChecked`  
 Gibt die Bitmap für Menüelemente verwendet, die eingecheckt werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ist ungleich null (0), wenn die Funktion erfolgreich ausgeführt wird, andernfalls null (0).  
  
### <a name="remarks"></a>Hinweise  
 Ob das Menüelement aktiviert oder deaktiviert ist, wird die entsprechende Bitmap neben dem Menüelement angezeigt.  
  
 Wenn entweder `pBmpUnchecked` oder `pBmpChecked` ist **NULL**, und klicken Sie dann Windows nichts neben dem Menüelement für das entsprechende Attribut angezeigt wird. Wenn beide Parameter **NULL**, Windows verwendet das Standard-Kontrollkästchen, wenn das Element aktiviert ist, und entfernt das Häkchen aus, wenn das Element nicht aktiviert ist.  
  
 Wenn Sie im Menü zerstört wird, werden diese Bitmaps nicht zerstört; die Anwendung muss diese gelöscht.  
  
 Windows **GetMenuCheckMarkDimensions** Funktion ruft die Dimensionen des Häkchens Standardwert verwendet. Die Anwendung verwendet diese Werte bestimmen die geeignete Größe für die Bitmaps, die mit dieser Funktion bereitgestellt. Rufen Sie die Größe und stellen erstellen Sie die Bitmaps.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#32;](../../mfc/reference/codesnippet/cpp/cmenu-class_12.cpp)]  
  
 [!code-cpp[NVC_MFCWindowing&33;](../../mfc/reference/codesnippet/cpp/cmenu-class_13.cpp)]  
  
##  <a name="setmenuiteminfo"></a>CMenu::SetMenuItemInfo  
 Ändern die Informationen zu einem Menüelement.  
  
```  
BOOL SetMenuItemInfo(
    UINT uItem,  
    LPMENUITEMINFO lpMenuItemInfo,  
    BOOL fByPos = FALSE);
```  
  
### <a name="parameters"></a>Parameter  
 `uItem`  
 Finden Sie in der Beschreibung der `uItem` in [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `lpMenuItemInfo`  
 Finden Sie in der Beschreibung der `lpmii` in **SetMenuItemInfo** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `fByPos`  
 Finden Sie in der Beschreibung der `fByPosition` in **SetMenuItemInfo** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion umfasst [SetMenuItemInfo](http://msdn.microsoft.com/library/windows/desktop/ms648001), beschrieben in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="trackpopupmenu"></a>CMenu::TrackPopupMenu  
 Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü auf.  
  
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
  
 *x*  
 Gibt die horizontale Position in Bildschirmkoordinaten des Popupmenüs. Abhängig vom Wert der `nFlags` -Parameter im Menü kann linksbündig, rechtsbündig oder zentriert relativ zu dieser Position sein.  
  
 *y*  
 Gibt die vertikale Position in Bildschirmkoordinaten der oberen Rand des Menüs auf dem Bildschirm an.  
  
 `pWnd`  
 Identifiziert das Fenster, das Popupmenü besitzt. Dieser Parameter darf nicht **NULL**, selbst wenn die **TPM_NONOTIFY** -Flag angegeben ist. In diesem Fenster empfängt alle **WM_COMMAND** Nachrichten aus dem Menü. In Windows-Versionen 3.1 und höher, empfängt das Fenster keine **WM_COMMAND** Nachrichten bis `TrackPopupMenu` zurückgegeben. Windows 3.0 wird das Fenster empfängt **WM_COMMAND** Nachrichten vor dem `TrackPopupMenu` zurückgibt.  
  
 `lpRect`  
 Ignoriert.  
  
### <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt das Ergebnis des Aufrufs [TrackPopupMenu](http://msdn.microsoft.com/library/windows/desktop/ms648002) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Hinweise  
 Ein Gleitkomma-Popup-Menü kann eine beliebige Stelle auf dem Bildschirm angezeigt.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCWindowing&#34;](../../mfc/reference/codesnippet/cpp/cmenu-class_14.cpp)]  
  
##  <a name="trackpopupmenuex"></a>CMenu::TrackPopupMenuEx  
 Zeigt ein Gleitkomma-Popup-Menü an der angegebenen Position und verfolgt die Auswahl der Elemente im Popupmenü auf.  
  
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
 Gibt verschiedene Funktionen für das erweiterte Menü. Eine Auflistung aller Werte und ihre Bedeutung finden Sie unter [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
 *x*  
 Gibt die horizontale Position in Bildschirmkoordinaten des Popupmenüs.  
  
 *y*  
 Gibt die vertikale Position in Bildschirmkoordinaten der oberen Rand des Menüs auf dem Bildschirm an.  
  
 `pWnd`  
 Ein Zeiger auf das Fenster im Popupmenü besitzt und Empfangen von Nachrichten erstellte Menü. Dieses Fenster kann einem beliebigen Fenster aus der aktuellen Anwendung aber nicht **NULL**. Bei Angabe von **TPM_NONOTIFY** in der `fuFlags` -Parameter die Funktion sendet keine Nachrichten an `pWnd`. Die Funktion zurück, für das Fenster auf den `pWnd` zum Empfangen der **WM_COMMAND** Nachricht.  
  
 *lptpm*  
 Zeiger auf eine [TPMPARAMS](http://msdn.microsoft.com/library/windows/desktop/ms647586) -Struktur, die einen Bereich des Fensters im Menü gibt sollten sich nicht überschneiden. Dieser Parameter kann **NULL**.  
  
### <a name="return-value"></a>Rückgabewert  
 Bei Angabe von **TPM_RETURNCMD** in der `fuFlags` -Parameter, der Rückgabewert ist im Menü-Element-ID des Elements, das der Benutzer ausgewählt hat. Wenn der Benutzer im Menü abbricht, ohne eine Auswahl treffen oder ein Fehler auftritt, ist der Rückgabewert 0.  
  
 Wenn Sie nicht angeben **TPM_RETURNCMD** in der `fuFlags` -Parameter, der Rückgabewert ist ungleich NULL, wenn die Funktion erfolgreich ausgeführt wird und 0, wenn ein Fehler auftritt. Um erweiterte Fehlerinformationen abzurufen, rufen Sie [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360).  
  
### <a name="remarks"></a>Hinweise  
 Ein Gleitkomma-Popup-Menü kann eine beliebige Stelle auf dem Bildschirm angezeigt. Weitere Informationen zum Behandeln von Fehlern beim Erstellen des Popup-Menüs finden Sie unter [TrackPopupMenuEx](http://msdn.microsoft.com/library/windows/desktop/ms648003).  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-Beispiel CTRLTEST](../../visual-cpp-samples.md)   
 [MFC-Beispiel DYNAMENU](../../visual-cpp-samples.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject-Klasse](../../mfc/reference/cobject-class.md)

