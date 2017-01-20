---
title: "CMenu Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "CMenu"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMenu class"
  - "HMENU"
  - "Menüs, Basisklasse"
  - "Menüs, Klasse"
  - "Menüs, Erstellen"
  - "Menüs, Verwalten"
ms.assetid: 40cacfdc-d45c-4ec7-bf28-991c72812499
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CMenu Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine Kapselung Windows `HMENU`.  
  
## Syntax  
  
```  
class CMenu : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMenu::CMenu](../Topic/CMenu::CMenu.md)|Erstellt ein `CMenu`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)|Fügt ein neues Element am Ende dieses Menüs an.|  
|[CMenu::Attach](../Topic/CMenu::Attach.md)|Fügt ein Menü Fenster\-Handle zu einem `CMenu`\-Objekt.|  
|[CMenu::CheckMenuItem](../Topic/CMenu::CheckMenuItem.md)|Setzt ein Häkchen neben oder entfernt ein Häkchen von einem Menüelement im Popupmenü.|  
|[CMenu::CheckMenuRadioItem](../Topic/CMenu::CheckMenuRadioItem.md)|Setzt ein Optionsfeld neben einem Menüelement und entfernt das Optionsfeld aus allen anderen Menüelemente in der Gruppe.|  
|[CMenu::CreateMenu](../Topic/CMenu::CreateMenu.md)|Erstellt ein leeres Menü und fügt es zu einem `CMenu`\-Objekt.|  
|[CMenu::CreatePopupMenu](../Topic/CMenu::CreatePopupMenu.md)|Erstellt ein leeres Popupmenü und fügt es zu einem `CMenu`\-Objekt.|  
|[CMenu::DeleteMenu](../Topic/CMenu::DeleteMenu.md)|Löscht ein angegebenes Element aus dem Menü.  Wenn das Menüelement ein zugeordnetes Popupmenü verfügt, zerstört das Handle für das Popupmenü und gibt den Speicher frei, der von diesen verwendet wird.|  
|[CMenu::DeleteTempMap](../Topic/CMenu::DeleteTempMap.md)|Löscht alle temporären `CMenu`\-Objekte, die von der `FromHandle`\-Memberfunktion erstellt werden.|  
|[CMenu::DestroyMenu](../Topic/CMenu::DestroyMenu.md)|Zerstört das Menü, das einem Objekt `CMenu` angefügt wird und jeden Speicherplatz, den das Menü gefüllte.|  
|[CMenu::Detach](../Topic/CMenu::Detach.md)|Trennt ein Menü Fenster\-Handle von einem `CMenu`\-Objekt und gibt das Handle zurück.|  
|[CMenu::DrawItem](../Topic/CMenu::DrawItem.md)|Aufgerufen vom Framework ausgelöst, wenn ein visueller Aspekt eines Ownerdrawnmenüs ändert.|  
|[CMenu::EnableMenuItem](../Topic/CMenu::EnableMenuItem.md)|Aktiviert, deaktiviert oder blendet \(grau\) ein Menüelement ab.|  
|[CMenu::FromHandle](../Topic/CMenu::FromHandle.md)|Gibt einen Zeiger auf einen `CMenu`\-Objekt zurück, das ein Menü Fenster\-Handle angegeben ist.|  
|[CMenu::GetDefaultItem](../Topic/CMenu::GetDefaultItem.md)|Bestimmt das standardmäßige Menüelement auf dem angegebenen Menü.|  
|[CMenu::GetMenuContextHelpId](../Topic/CMenu::GetMenuContextHelpId.md)|Ruft die Hilfekontext\-id ab, die dem Menü zugeordnet ist.|  
|[CMenu::GetMenuInfo](../Topic/CMenu::GetMenuInfo.md)|Ruft Informationen über ein bestimmtes Menü ab.|  
|[CMenu::GetMenuItemCount](../Topic/CMenu::GetMenuItemCount.md)|Bestimmt die Anzahl der Elemente in einem Popup oder in einem Menü der obersten Ebene.|  
|[CMenu::GetMenuItemID](../Topic/CMenu::GetMenuItemID.md)|Erhält der Menüelementbezeichner für ein Menüelement, das an der angegebenen Position und wird.|  
|[CMenu::GetMenuItemInfo](../Topic/CMenu::GetMenuItemInfo.md)|Ruft Informationen über ein Menüelement ab.|  
|[CMenu::GetMenuState](../Topic/CMenu::GetMenuState.md)|Gibt den Status des angegebenen Menüelements oder die Anzahl der Elemente in einem Popupmenü zurück.|  
|[CMenu::GetMenuString](../Topic/CMenu::GetMenuString.md)|Ruft die Bezeichnung des angegebenen Menüelements ab.|  
|[CMenu::GetSafeHmenu](../Topic/CMenu::GetSafeHmenu.md)|Gibt `m_hMenu` zurück, das von diesem Objekt `CMenu` umschlossen wird.|  
|[CMenu::GetSubMenu](../Topic/CMenu::GetSubMenu.md)|Ruft einen Zeiger auf ein Popupmenü ab.|  
|[CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)|Fügt ein neues Menüelement an der angegebenen Position ein verschiebt und andere Elemente in das Menü.|  
|[CMenu::InsertMenuItem](../Topic/CMenu::InsertMenuItem.md)|Fügt ein neues Menüelement an der angegebenen Position in einem Menü ein.|  
|[CMenu::LoadMenu](../Topic/CMenu::LoadMenu.md)|Lädt eine Menüressource der ausführbaren Datei und fügt sie zu einem `CMenu`\-Objekt.|  
|[CMenu::LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)|Lädt ein Menü mit einer Menüvorlage im Arbeitsspeicher und fügt es zu einem `CMenu`\-Objekt.|  
|[CMenu::MeasureItem](../Topic/CMenu::MeasureItem.md)|Aufgerufen durch das Framework, um Menüdimensionen zu bestimmen, ob ein Ownerdrawnmenü erstellt wird.|  
|[CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)|Ändert ein vorhandenes Menüelement an der angegebenen Position.|  
|[CMenu::RemoveMenu](../Topic/CMenu::RemoveMenu.md)|Löscht ein Menüelement einem zugeordneten Popupmenü aus dem angegebenen Menü.|  
|[CMenu::SetDefaultItem](../Topic/CMenu::SetDefaultItem.md)|Legt das standardmäßige Menüelement für das angegebene Menü fest.|  
|[CMenu::SetMenuContextHelpId](../Topic/CMenu::SetMenuContextHelpId.md)|Legt die dem Menü fest zugeordnet werden Hilfekontext\-id.|  
|[CMenu::SetMenuInfo](../Topic/CMenu::SetMenuInfo.md)|Enthält Informationen über ein bestimmtes Menü fest.|  
|[CMenu::SetMenuItemBitmaps](../Topic/CMenu::SetMenuItemBitmaps.md)|Ordnet die angegebenen Prüfzeichenbitmaps mit einem Menüelement zu.|  
|[CMenu::SetMenuItemInfo](../Topic/CMenu::SetMenuItemInfo.md)|Ändert Informationen über ein Menüelement.|  
|[CMenu::TrackPopupMenu](../Topic/CMenu::TrackPopupMenu.md)|Zeigt ein unverankertes Popupmenü an der angegebenen Position an und verfolgt die Auswahl von Elementen im Popupmenü.|  
|[CMenu::TrackPopupMenuEx](../Topic/CMenu::TrackPopupMenuEx.md)|Zeigt ein unverankertes Popupmenü an der angegebenen Position an und verfolgt die Auswahl von Elementen im Popupmenü.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMenu::operator HMENU](../Topic/CMenu::operator%20HMENU.md)|Ruft das Handle des Menüobjekts ab.|  
|[CMenu::operator \!\=](../Topic/CMenu::operator%20!=.md)|Bestimmt, ob zwei Menüobjekte nicht gleich sind.|  
|[CMenu::operator \=\=](../Topic/CMenu::operator%20==.md)|Bestimmt, ob zwei Menüobjekte gleich sind.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CMenu::m\_hMenu](../Topic/CMenu::m_hMenu.md)|Gibt das Handle für das Menü Fenster an, das dem Objekt `CMenu` angefügt wird.|  
  
## Hinweise  
 Es enthält Memberfunktionen für das Erstellen, Nachverfolgen, Aktualisieren und das Löschen eines Menüs bereit.  
  
 Erstellen Sie ein `CMenu`\-Objekt im Stapelrahmen als lokale Variable, und rufen Sie dann die Memberfunktionen von `CMenu` auf, um das neue Menü nach Bedarf zu bearbeiten.  Als Nächstes Aufruf [CWnd::SetMenu](../Topic/CWnd::SetMenu.md), damit das Menü zu einem Fenster festzulegen, direkt gefolgt von einem Aufruf der Memberfunktion des `CMenu`[Trennen Sie sich](../Topic/CMenu::Detach.md)\-Objekts.  Die `CWnd::SetMenu`\-Memberfunktion legt das Menü des Fensters in das neue Menü fest, wird das Fenster neu gezeichnet werden, um die Menüänderung wiederzugeben und führt auch den Besitzer des Menüs in das Fenster.  Der Aufruf **Detach** trennt `HMENU` vom `CMenu`\-Objekt, damit, wenn die lokalen `CMenu`\-Variablenübergaben außerhalb des Bereichs, der `CMenu`\-Objektdestruktor nicht versucht, ein Menü zu zerstören, er nicht mehr besitzt.  Das Menü selbst wird automatisch zerstört, wenn das Fenster zerstört wird.  
  
 Sie können die [LoadMenuIndirect](../Topic/CMenu::LoadMenuIndirect.md)\-Memberfunktion verwenden, um ein Menü mit einer Vorlage im Arbeitsspeicher erstellen, aber ein Menü, das von einer Ressource durch einen Aufruf [LoadMenu](../Topic/CMenu::LoadMenu.md) erstellt wird, kann einfach verwaltet, und die Menüressource selbst kann im Menü\-Editor erstellt und geändert werden.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMenu`  
  
## Anforderungen  
 **Header:** afxwin.h  
  
## Siehe auch  
 [MFC\-Beispiel CTRLTEST](../../top/visual-cpp-samples.md)   
 [MFC\-Beispiel DYNAMENU](../../top/visual-cpp-samples.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)