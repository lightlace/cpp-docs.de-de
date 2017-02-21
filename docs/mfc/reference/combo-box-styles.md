---
title: "Kombinationsfeldstile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBS_LOWERCASE"
  - "CBS_SORT"
  - "CBS_OWNERDRAWVARIABLE"
  - "CBS_OEMCONVERT"
  - "CBS_AUTOHSCROLL"
  - "CBS_NOINTEGRALHEIGHT"
  - "CBS_SIMPLE"
  - "CBS_DROPDOWNLIST"
  - "CBS_DROPDOWN"
  - "CBS_UPPERCASE"
  - "CBS_HASSTRINGS"
  - "CBS_DISABLENOSCROLL"
  - "CBS_OWNERDRAWFIXED"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBS_OWNERDRAWVARIABLE-Konstante"
  - "CBS_NOINTEGRALHEIGHT-Konstante"
  - "CBS_SIMPLE-Konstante"
  - "CBS_AUTOHSCROLL-Konstante"
  - "CBS_OEMCONVERT-Konstante"
  - "CBS_DISABLENOSCROLL-Konstante"
  - "CBS_HASSTRINGS-Konstante"
  - "CBS_LOWERCASE-Konstante"
  - "CBS_SORT-Konstante"
  - "CBS_DROPDOWN-Konstante"
  - "CBS_OWNERDRAWFIXED-Konstante"
  - "Kombinationsfelder, Stile"
  - "CBS_UPPERCASE-Konstante"
  - "CBS_DROPDOWNLIST-Konstante"
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# Kombinationsfeldstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In MFC sind die folgenden Stile für Kombinationsfelder verfügbar.  
  
-   **CBS\_AUTOHSCROLL** Scrollt den Text im Bearbeitungssteuerelement automatisch nach rechts, wenn der Benutzer am Zeilenende ein Zeichen eingibt. Wenn dieser Stil nicht festgelegt ist, ist nur Text zulässig, der in die rechteckige Begrenzung passt.  
  
-   **CBS\_DISABLENOSCROLL** Das Listenfeld zeigt eine deaktivierte vertikale Scrollleiste an, wenn es nicht genügend Elemente enthält, um zu scrollen. Ohne diesen Stil wird die Scrollleiste ausgeblendet, wenn das Listenfeld nicht genügend Elemente enthält.  
  
-   **CBS\_DROPDOWN** Ähnlich wie **CBS\_SIMPLE**, außer dass das Listenfeld erst angezeigt wird, wenn der Benutzer ein Symbol neben dem Bearbeitungssteuerelement auswählt.  
  
-   **CBS\_DROPDOWNLIST** Ähnlich wie **CBS\_DROPDOWN**, außer dass das Bearbeitungssteuerelement durch ein Element mit statischem Text ersetzt wird, das die aktuelle Auswahl im Listenfeld anzeigt.  
  
-   **CBS\_HASSTRINGS** Ein Ownerdrawn\-Kombinationsfeld enthält Elemente, die aus Zeichenfolgen bestehen. Das Kombinationsfeld verwaltet den Arbeitsspeicher und die Zeiger für die Zeichenfolgen, sodass die Anwendung die `GetText`\-Memberfunktion verwenden kann, um den Text für ein bestimmtes Element abzurufen.  
  
-   **CBS\_LOWERCASE** Wandelt den gesamten Text sowohl im Auswahlfeld als auch in der Liste in Kleinbuchstaben um.  
  
-   **CBS\_NOINTEGRALHEIGHT** Gibt an, dass die Größe des Kombinationsfelds genau der Größe entspricht, die von der Anwendung beim Erstellen des Kombinationsfelds angegeben wurde. Üblicherweise passt Windows die Größen von Kombinationsfeldern an, damit Elemente nicht nur teilweise angezeigt werden.  
  
-   **CBS\_OEMCONVERT** In das Bearbeitungssteuerelement des Kombinationsfelds eingegebener Text wird vom ANSI\-Zeichensatz in den OEM\-Zeichensatz und wieder zurück zu ANSI konvertiert. Dies stellt eine ordnungsgemäße Zeichenkonvertierung sicher, wenn die Anwendung die Windows\-Funktion `AnsiToOem` aufruft, um eine ANSI\-Zeichenfolge im Kombinationsfeld in OEM\-Zeichen zu konvertieren. Dieser Stil ist sehr nützlich für Kombinationsfelder, die Dateinamen enthalten, und kann nur auf Kombinationsfelder angewendet werden, die mit den Stilen **CBS\_SIMPLE** oder **CBS\_DROPDOWN** erstellt wurden.  
  
-   **CBS\_OWNERDRAWFIXED** Der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich. Alle Elemente im Listenfeld weisen die gleiche Höhe auf.  
  
-   **CBS\_OWNERDRAWVARIABLE** Der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich. Die Höhe der Elemente im Listenfeld ist variabel.  
  
-   **CBS\_SIMPLE** Das Listenfeld wird immer angezeigt. Die aktuelle Auswahl im Listenfeld wird im Bearbeitungssteuerelement angezeigt.  
  
-   **CBS\_SORT** Sortiert in das Listenfeld eingegebene Zeichenfolgen automatisch.  
  
-   **CBS\_UPPERCASE** Wandelt den gesamten Text sowohl im Auswahlfeld als auch in der Liste in Großbuchstaben um.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create](../Topic/CComboBox::Create.md)   
 [Combo Box Styles](_win32_combo_box_styles)