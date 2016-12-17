---
title: "DRAWITEMSTRUCT-Struktur"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "DRAWITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DRAWITEMSTRUCT-Struktur"
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# DRAWITEMSTRUCT-Struktur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die `DRAWITEMSTRUCT`\-Struktur stellt Informationen zur Verfügung, über die das besitzende Fenster verfügen muss, um zu bestimmen, wie ein vom Besitzer gezeichnetes Steuerelement oder Menüelement gezeichnet werden muss.  
  
## Syntax  
  
```  
  
typedef struct tagDRAWITEMSTRUCT {  
   UINT   
CtlType  
;  
   UINT   
CtlID  
;  
   UINT   
itemID  
;  
   UINT   
itemAction  
;  
   UINT   
itemState  
;  
   HWND   
hwndItem  
;  
   HDC   
hDC  
;  
   RECT   
rcItem  
;  
   DWORD   
itemData  
;  
} DRAWITEMSTRUCT;  
  
```  
  
#### Parameter  
 `CtlType`  
 Der Steuerelementtyp. Folgende Werte sind für Steuerelementtypen gültig:  
  
-   **ODT\_BUTTON** Vom Besitzer gezeichnete Schaltfläche  
  
-   **ODT\_COMBOBOX** Vom Besitzer gezeichnetes Kombinationsfeld  
  
-   **ODT\_COMBOBOX** Vom Besitzer gezeichnetes Listenfeld  
  
-   **ODT\_MENU** Vom Besitzer gezeichnetes Menü  
  
-   **ODT\_LISTVIEW** Listenansicht\-Steuerelement  
  
-   **ODT\_STATIC** Vom Besitzer gezeichnetes statisches Steuerelement  
  
-   **ODT\_TAB** Registerkarten\-Steuerelement  
  
 `CtlID`  
 Die Steuerelement\-ID für ein Kombinationsfeld, ein Listenfeld oder eine Schaltfläche. Dieser Member wird nicht für ein Menü verwendet.  
  
 `itemID`  
 Die Menüelement\-ID für ein Menü oder der Index des Elements in einem Listenfeld oder Kombinationsfeld. Bei einem leeren Listenfeld oder Kombinationsfeld hat dieser Member einen negativen Wert, was es der Anwendung ermöglicht, nur das Fokusrechteck an den im Member **rcItem** angegebenen Koordinaten zu zeichnen, obwohl das Steuerelement keine Elemente enthält. Dem Benutzer kann auf diese Weise angezeigt werden, ob das Listenfeld oder Kombinationsfeld den Eingabefokus besitzt. Die Einstellung der Bits im Member **itemAction** bestimmt, ob das Rechteck so gezeichnet wird, als ob das Listenfeld oder Kombinationsfeld den Eingabefokus hat.  
  
 `itemAction`  
 Definiert die erforderliche Zeichenaktion. Dabei handelt es sich um mindestens eins der folgenden Bits:  
  
-   **ODA\_DRAWENTIRE** Dieses Bit ist gesetzt, wenn das gesamte Steuerelement gezeichnet werden muss.  
  
-   **ODA\_FOCUS** Dieses Bit ist gesetzt, wenn das Steuerelement den Eingabefokus erhält oder abgibt. Der Member **itemState** sollte aktiviert sein, um zu bestimmen, ob das Steuerelement den Fokus hat.  
  
-   **ODA\_SELECT** Dieses Bit wird gesetzt, wenn sich nur der Auswahlstatus geändert hat. Der Member **itemState** sollte aktiviert sein, um zu bestimmen, ob die neue Auswahl den Fokus hat.  
  
 *itemState*  
 Gibt den visuellen Status des Elements nach dem Abschluss der aktuellen Zeichenaktion an. Das heißt, wenn ein Menüelement ausgegraut dargestellt werden soll, ist das Statusflag **ODS\_GRAYED** gesetzt. Diese Statusflags sind verfügbar:  
  
-   **ODS\_CHECKED** Dieses Bit ist gesetzt, wenn das Menüelement aktiviert werden muss. Dieses Bit wird nur in Menüs verwendet.  
  
-   **ODS\_DISABLED** Dieses Bit ist gesetzt, wenn das Element als deaktiviert gezeichnet werden muss.  
  
-   **ODS\_FOCUS** Dieses Bit ist gesetzt, wenn das Element den Eingabefokus aufweist.  
  
-   **ODS\_GRAYED** Dieses Bit ist gesetzt, wenn das Element ausgegraut dargestellt werden muss. Dieses Bit wird nur in Menüs verwendet.  
  
-   **ODS\_SELECTED** Dieses Bit ist gesetzt, wenn der Status des Elements „aktiviert“ ist.  
  
-   **ODS\_COMBOBOXEDIT** Das Zeichnen findet im Auswahlfeld \(Bearbeiten\-Steuerelement\) eines von einem Besitzer gezeichneten Kombinationsfelds statt.  
  
-   **ODS\_DEFAULT** Das Element ist das Standardelement.  
  
 `hwndItem`  
 Gibt das Fensterhandle des Steuerelements für Kombinationsfelder, Listenfelder und Schaltflächen an. Gibt das Handle des Menüs \(`HMENU`\) an, das das Element für Menüs enthält.  
  
 `hDC`  
 Bezeichnet einen Gerätekontext. Dieser Gerätekontext muss beim Ausführen von Zeichenvorgängen im Steuerelement verwendet werden.  
  
 *rcItem*  
 Ein Rechteck in dem vom `hDC`\-Member angegebenen Gerätekontext, das die Grenzen des zu zeichnenden Steuerelements definiert. Windows beschneidet automatisch alles, was der Besitzer im Gerätekontext für Kombinationsfelder, Listenfelder und Schaltflächen zeichnet, Menüelemente werden jedoch nicht beschnitten. Beim Zeichnen von Menüelementen darf der Besitzer nicht außerhalb der Grenzen des vom Member **rcItem** definierten Rechtecks zeichnen.  
  
 `itemData`  
 Für ein Kombinationsfeld oder Listenfeld enthält dieser Member den Wert, der dem Listenfeld von einer der folgenden Methoden übergeben wurde:  
  
-   [CComboBox:: AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 Für ein Menü enthält dieser Member den Wert, der dem Menü durch eine der folgenden Methoden übergeben wurde:  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
## Hinweise  
 Das besitzende Fenster des vom Besitzer gezeichneten Steuerelements oder Menüelements erhält einen Zeiger auf diese Struktur als `lParam`\-Parameter der `WM_DRAWITEM`\-Nachricht.  
  
## Anforderungen  
 **Header:** winuser.h  
  
## Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)