---
title: "Behandeln von Anpassungsbenachrichtigungen"
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
  - "TBN_CUSTHELP"
  - "TBN_QUERYINSERT"
  - "TBNOTIFY"
  - "NMHDR"
  - "TBN_TOOLBARCHANGE"
  - "TBN_ENDDRAG"
  - "NM_SETFOCUS"
  - "TBN_RESET"
  - "NM_RETURN"
  - "NM_ENDWAIT"
  - "NM_STARTWAIT"
  - "TBN_BEGINDRAG"
  - "NM_OUTOFMEMORY"
  - "TBN_QUERYDELETE"
  - "NM_DBLCLK"
  - "TBN_ENDADJUST"
  - "NM_KILLFOCUS"
  - "NM_RCLICK"
  - "TBN_BEGINADJUST"
  - "NM_CLICK"
  - "NM_RDBLCLK::"
  - "TBN_GETBUTTONINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TBN_ENDADJUST-Benachrichtigung"
  - "TBNOTIFY-Benachrichtigung"
  - "TBN_BEGINDRAG-Benachrichtigung"
  - "TBN_TOOLBARCHANGE-Benachrichtigung"
  - "NM_CLICK-Benachrichtigung"
  - "NM_RETURN-Benachrichtigung"
  - "NM_RCLICK-Benachrichtigung"
  - "TBN_ENDDRAG-Benachrichtigung"
  - "TBN_BEGINADJUST-Benachrichtigung"
  - "NM_ENDWAIT-Benachrichtigung"
  - "NM_KILLFOCUS-Benachrichtigung"
  - "NM_SETFOCUS-Benachrichtigung"
  - "NM_OUTOFMEMORY-Benachrichtigung"
  - "TBN_QUERYINSERT-Benachrichtigung"
  - "NMHDR"
  - "NM_STARTWAIT-Benachrichtigung"
  - "CToolBarCtrl-Klasse, Behandeln von Benachrichtigungen"
  - "TBN_CUSTHELP-Benachrichtigung"
  - "TBN_RESET-Benachrichtigung"
  - "NM_DBLCLK-Benachrichtigung"
  - "TBN_QUERYDELETE-Benachrichtigung"
  - "NM_RDBLCLK-Benachrichtigung"
  - "TBN_GETBUTTONINFO-Benachrichtigung"
ms.assetid: 219ea08e-7515-4b98-85cb-47120f08c0a2
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Behandeln von Anpassungsbenachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein allgemeine Windows\-Symbolleisten\-Steuerelement verfügt über integrierte Funktionen zur Anpassung, einschließlich eines vom System definierten Anpassungsdialogfelds, das dem Benutzer das Einfügen, Löschen oder erneute Anordnen von Schaltflächen auf der Symbolleiste ermöglicht. Die Anwendung bestimmt, ob die Anpassungsfunktionen verfügbar sind und steuert das Ausmaß, bis zu dem der Benutzer die Symbolleiste anpassen kann.  
  
 Sie können dem Benutzer diese Anpassungsfunktionen zugänglich machen, indem Sie der Symbolleiste die Formatvorlage `CCS_ADJUSTABLE` zuweisen. Die Anpassungsfunktionen ermöglichen es dem Benutzer, eine Schaltfläche an eine neue Position zu ziehen oder eine Schaltfläche zu entfernen, indem er sie von der Symbolleiste zieht. Darüber hinaus kann der Benutzer auf die Symbolleiste doppelklicken, um das Dialogfeld **Symbolleiste anpassen** anzuzeigen, in dem der Benutzer Symbolleistenschaltflächen hinzufügen, löschen und neu anordnen kann. Die Anwendung kann das Dialogfeld mithilfe der Memberfunktion [Customize](../Topic/CToolBarCtrl::Customize.md) anzeigen.  
  
 Das Symbolleistensteuerelement sendet bei jedem Schritt im Anpassungsvorgang Benachrichtigungsmeldungen an das übergeordnete Fenster. Wenn der Benutzer die UMSCHALT\-Taste gedrückt hält und beginnt, eine Schaltfläche zu ziehen, übernimmt die Symbolleiste automatisch die Verarbeitung des Ziehvorgangs. Die Symbolleiste sendet die Benachrichtigungsmeldung **TBN\_QUERYDELETE** an das übergeordnete Fenster, um zu bestimmen, ob die Schaltfläche gelöscht werden darf. Der Ziehvorgang endet, wenn das übergeordnete Fenster **FALSE** zurückgibt. Andernfalls erfasst die Symbolleiste die Mauseingabe und wartet darauf, dass der Benutzer die Maustaste freigibt.  
  
 Wenn der Benutzer die Maustaste freigibt, bestimmt die Symbolleiste die Position des Mauszeigers. Wenn der Zeiger sich außerhalb der Symbolleiste befindet, wird die Schaltfläche gelöscht. Wenn der Cursor sich auf einer anderen Symbolleistenschaltfläche befindet, sendet die Symbolleiste die Benachrichtigungsmeldung **TBN\_QUERYINSERT** an das übergeordnete Fenster, um zu bestimmen, ob links neben der angegebenen Schaltfläche eine Schaltfläche eingefügt werden darf. Die Schaltfläche wird eingefügt, wenn das übergeordnete Fenster **TRUE** zurückgibt, andernfalls nicht. Die Symbolleiste sendet die Benachrichtigungsmeldung **TBN\_TOOLBARCHANGE**, um das Ende des Ziehvorgangs anzuzeigen.  
  
 Wenn der Benutzer einen Ziehvorgang beginnt, ohne die UMSCHALT\-Taste gedrückt zu halten, sendet das Symbolleistensteuerelement die Benachrichtigungsmeldung **TBN\_BEGINDRAG** an das besitzende Fenster. Eine Anwendung, die eigenen Code zum Ziehen von Schaltflächen implementiert, kann diese Nachricht als Signal zum Einleiten eines Ziehvorgangs verwenden. Die Symbolleiste sendet die Benachrichtigungsmeldung **TBN\_ENDDRAG**, um das Ende des Ziehvorgangs anzuzeigen.  
  
 Ein Symbolleistensteuerelement sendet Benachrichtigungsmeldungen, wenn der Benutzer eine Symbolleiste mithilfe des Dialogfelds **Symbolleiste anpassen** konfiguriert. Die Symbolleiste sendet die Benachrichtigungsmeldung **TBN\_BEGINADJUST**, nachdem der Benutzer auf die Symbolleiste doppelgeklickt hat, aber bevor das Dialogfeld erstellt wird. Als Nächstes beginnt die Symbolleiste, eine Reihe von **TBN\_QUERYINSERT**\-Benachrichtigungsmeldungen zu senden, um zu bestimmen, ob die Symbolleiste das Einfügen von Schaltflächen zulässt. Wenn das übergeordnete Fenster **TRUE** zurückgibt, hört die Symbolleiste mit dem Senden von **TBN\_QUERYINSERT**\-Benachrichtigungsmeldungen auf. Wenn das übergeordnete Fenster für keine der Schaltflächen **TRUE** zurückgibt, zerstört die Symbolleiste das Dialogfeld.  
  
 Als Nächstes bestimmt das Symbolleistensteuerelement, ob Schaltflächen von der Symbolleiste gelöscht werden können, indem es eine **TBN\_QUERYDELETE**\-Benachrichtigungsmeldung für jede Schaltfläche auf der Symbolleiste sendet. Das übergeordnete Fenster gibt **TRUE** zurück, um anzuzeigen, dass eine Schaltfläche gelöscht werden kann; andernfalls gibt es **FALSE** zurück. Die Symbolleiste fügt dem Dialogfeld alle Symbolleistenschaltflächen hinzu, stellt aber die nicht löschbaren grau dar.  
  
 Immer, wenn die Symbolleiste Informationen über eine Schaltfläche im Dialogfeld „Symbolleiste anpassen“ benötigt, sendet sie die **TBN\_GETBUTTONINFO**\-Benachrichtigungsmeldung und gibt dabei den Index der Schaltfläche, für die sie Informationen benötigt, sowie die Adresse einer **TBNOTIFY**\-Struktur an. Das übergeordnete Fenster muss die Struktur mit den relevanten Informationen füllen.  
  
 Das Dialogfeld **Symbolleiste anpassen** enthält eine Schaltfläche „Hilfe“ und eine Schaltfläche „Zurücksetzen“. Wenn der Benutzer die Schaltfläche „Hilfe“ auswählt, sendet das Symbolleistensteuerelement die Benachrichtigungsmeldung **TBN\_CUSTHELP**. Das übergeordnete Fenster sollte darauf mit dem Anzeigen von Hilfeinformationen reagieren. Das Dialogfeld sendet die Benachrichtigungsmeldung **TBN\_RESET**, wenn der Benutzer die Schaltfläche „Zurücksetzen“ auswählt. Diese Nachricht zeigt an, dass die Symbolleiste unmittelbar davor steht, das Dialogfeld erneut zu initialisieren.  
  
 Alle diese Nachrichten sind **WM\_NOTIFY**\-Nachrichten, und sie können in Ihrem Besitzerfenster durch das Hinzufügen von Meldungszuordnungseinträgen der folgenden Form zur Meldungszuordnung Ihres Besitzerfensters verarbeitet werden:  
  
 `ON_NOTIFY( wNotifyCode, idControl, memberFxn )`  
  
 `wNotifyCode`  
 ID\-Code der Benachrichtigungsmeldung, wie etwa **TBN\_BEGINADJUST**.  
  
 `idControl`  
 Der Bezeichner des Steuerelements, das die Benachrichtigung gesendet.  
  
 `memberFxn`  
 Die Memberfunktion die aufgerufen werden soll, wenn diese Benachrichtigung empfangen wird.  
  
 Ihre Memberfunktion sollte mit dem folgenden Prototyp deklariert sein:  
  
 `afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );`  
  
 Wenn der Benachrichtigungsmeldungshandler einen Wert zurückgibt, sollte er ihn in das **LRESULT** einfügen, auf das *result* verweist.  
  
 Für jede Meldung verweist `pNotifyStruct` entweder auf eine **NMHDR**\- oder auf eine **TBNOTIFY**\-Struktur. Diese Strukturen sind unten beschrieben:  
  
 Die **NMHDR**\-Struktur enthält die folgenden Member:  
  
 `typedef struct tagNMHDR {`  
  
 `HWND hwndFrom;  // handle of control sending message`  
  
 `UINT idFrom;// identifier of control sending message`  
  
 `UINT code;  // notification code; see below`  
  
 `} NMHDR;`  
  
 **hwndFrom**  
 Das Fensterhandle des Steuerelements, das die Benachrichtigung sendet. Um dieses Handle in einen `CWnd`\-Zeiger zu konvertieren, verwenden Sie [CWnd::FromHandle](../Topic/CWnd::FromHandle.md).  
  
 **idFrom**  
 ID des Steuerelements, das die Benachrichtigung sendet.  
  
 **Code**  
 Benachrichtigungscode. Dieser Member kann ein für einen Steuerelementtyp spezifischer Wert sein, wie etwa **TBN\_BEGINADJUST** oder **TTN\_NEEDTEXT**, oder es kann einer der allgemeinen Benachrichtigungswerte sein, die unten aufgelistet sind:  
  
-   **NM\_CLICK** Der Benutzer hat innerhalb des Steuerelements mit der linken Maustaste geklickt.  
  
-   **NM\_DBLCLK** Der Benutzer hat innerhalb des Steuerelements mit der linken Maustaste doppelgeklickt.  
  
-   **NM\_KILLFOCUS** Das Steuerelement hat den Eingabefokus verloren.  
  
-   **NM\_OUTOFMEMORY** Das Steuerelement konnte einen Vorgang nicht abschließen, weil nicht genügend Arbeitsspeicher verfügbar ist.  
  
-   **NM\_RCLICK** Der Benutzer hat innerhalb des Steuerelements mit der rechten Maustaste geklickt.  
  
-   **NM\_RDBLCLK** Der Benutzer hat innerhalb des Steuerelement mit der rechten Maustaste doppelgeklickt.  
  
-   **NM\_RETURN** Das Steuerelement hat den Eingabefokus, und der Benutzer hat die EINGABETASTE gedrückt.  
  
-   **NM\_SETFOCUS** Das Steuerelement hat den Eingabefokus erhalten.  
  
 Die **TBNOTIFY**\-Struktur enthält die folgenden Member:  
  
 `typedef struct {`  
  
 `NMHDR hdr; // information common to all WM_NOTIFY messages`  
  
 `int iItem; // index of button associated with notification`  
  
 `TBBUTTON tbButton; // info about button associated withnotification`  
  
 `int cchText;   // count of characters in button text`  
  
 `LPSTR lpszText;// address of button text`  
  
 `} TBNOTIFY, FAR* LPTBNOTIFY;`  
  
## Hinweise  
 **hdr**  
 Gemeinsame Informationen für alle **WM\_NOTIFY**\-Nachrichten.  
  
 **iItem**  
 Index der Schaltfläche, die der Benachrichtigung zugeordnet ist.  
  
 **tbButton**  
 `TBBUTTON`\-Struktur, die Informationen über die Symbolleistenschaltfläche enthält, die der Benachrichtigung zugeordnet ist.  
  
 **cchText**  
 Anzahl der Zeichen im Schaltflächentext.  
  
 **lpszText**  
 Zeiger auf den Schaltflächentext.  
  
 Die Benachrichtigungen, die die Symbolleiste sendet, sind wie folgt:  
  
-   **TBN\_BEGINADJUST** Wird gesendet, wenn der Benutzer mit dem Anpassen eines Symbolleistensteuerelements beginnt. Der Zeiger verweist auf eine **NMHDR**\-Struktur, die Informationen zur Benachrichtigung enthält. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_BEGINDRAG** Wird gesendet, wenn der Benutzer beginnt, eine Schaltfläche in einem Symbolleistensteuerelement zu ziehen. Der Zeiger verweist auf eine **TBNOTIFY**\-Struktur. Das **iItem**\-Member enthält den nullbasierten Index der gezogenen Schaltfläche. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_CUSTHELP** Wird gesendet, wenn der Benutzer die Schaltfläche „Hilfe“ im Dialogfeld „Symbolleiste anpassen“ auswählt. Kein Rückgabewert. Der Zeiger verweist auf eine **NMHDR**\-Struktur, die Informationen über die Benachrichtigungsmeldung enthält. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_BEGINADJUST** Wird gesendet, wenn der Benutzer mit dem Anpassen eines Symbolleistensteuerelements beginnt. Der Zeiger verweist auf eine **NMHDR**\-Struktur, die Informationen über die Benachrichtigungsmeldung enthält. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_ENDDRAG** Wird gesendet, wenn der Benutzer damit aufhört, eine Schaltfläche in einem Symbolleistensteuerelement zu ziehen. Der Zeiger verweist auf eine **TBNOTIFY**\-Struktur. Das **iItem**\-Member enthält den nullbasierten Index der gezogenen Schaltfläche. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_GETBUTTONINFO** Wird gesendet, wenn der Benutzer ein Symbolleistensteuerelement anpasst. Die Symbolleiste verwendet diese Benachrichtigungsmeldung zum Abrufen von Informationen, die vom Dialogfeld „Symbolleiste anpassen“ benötigt werden. Der Zeiger verweist auf eine **TBNOTIFY**\-Struktur. Das **iItem**\-Member gibt den nullbasierten Index einer Schaltfläche an. Die Member **pszText** und **cchText** geben die Adresse und die Länge des aktuellen Schaltflächentexts in Zeichen an. Eine Anwendung sollte die Struktur mit Informationen über die Schaltfläche auffüllen. Gibt **TRUE** zurück, wenn Schaltflächeninformationen in die Struktur kopiert wurden, andernfalls **FALSE** .  
  
-   **TBN\_QUERYDELETE** Wird gesendet, während der Benutzer eine Symbolleiste anpasst, um zu bestimmen, ob eine Schaltfläche aus einem Symbolleistensteuerelement gelöscht werden kann. Der Zeiger verweist auf eine **TBNOTIFY**\-Struktur. Das **iItem**\-Member enthält den nullbasierten Index der zu löschenden Schaltfläche. Gibt **TRUE** zurück, um das Löschen der Schaltfläche zu erlauben oder **FALSE**, um das Löschen der Schaltfläche zu verhindern.  
  
-   **TBN\_QUERYINSERT** Wird gesendet, während der Benutzer ein Symbolleistensteuerelement anpasst, um zu bestimmen, ob links von der vorhandenen Schaltfläche eine Schaltfläche eingefügt werden darf. Der Zeiger verweist auf eine **TBNOTIFY**\-Struktur. Das **iItem**\-Member enthält den nullbasierten Index der einzufügenden Schaltfläche. Gibt **TRUE** zurück, um das Einfügen einer Schaltfläche vor der vorhandenen Schaltfläche zu erlauben oder **FALSE**, um das Einfügen der Schaltfläche zu verhindern.  
  
-   **TBN\_RESET** Wird gesendet, wenn der Benutzer den Inhalt des Dialogfelds „Symbolleiste anpassen“ zurücksetzt. Der Zeiger verweist auf eine **NMHDR**\-Struktur, die Informationen über die Benachrichtigungsmeldung enthält. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
-   **TBN\_TOOLBARCHANGE** Wird gesendet, nachdem der Benutzer ein Symbolleistensteuerelement angepasst hat. Der Zeiger verweist auf eine **NMHDR**\-Struktur, die Informationen über die Benachrichtigungsmeldung enthält. Der Handler muss keinen bestimmten Wert zurückgeben.  
  
## Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)