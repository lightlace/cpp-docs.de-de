---
title: Kombinationsfeldstile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CBS_LOWERCASE
- CBS_SORT
- CBS_OWNERDRAWVARIABLE
- CBS_OEMCONVERT
- CBS_AUTOHSCROLL
- CBS_NOINTEGRALHEIGHT
- CBS_SIMPLE
- CBS_DROPDOWNLIST
- CBS_DROPDOWN
- CBS_UPPERCASE
- CBS_HASSTRINGS
- CBS_DISABLENOSCROLL
- CBS_OWNERDRAWFIXED
dev_langs: C++
helpviewer_keywords:
- CBS_OWNERDRAWVARIABLE constant [MFC]
- CBS_NOINTEGRALHEIGHT constant [MFC]
- CBS_SIMPLE constant [MFC]
- CBS_AUTOHSCROLL constant [MFC]
- CBS_OEMCONVERT constant [MFC]
- CBS_DISABLENOSCROLL constant [MFC]
- CBS_HASSTRINGS constant [MFC]
- CBS_LOWERCASE constant [MFC]
- CBS_SORT constant [MFC]
- CBS_DROPDOWN constant [MFC]
- CBS_OWNERDRAWFIXED constant [MFC]
- combo boxes [MFC], styles
- CBS_UPPERCASE constant [MFC]
- CBS_DROPDOWNLIST constant
ms.assetid: d21a5023-e6a2-495b-a6bd-010a515cbc63
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 52cfd21df2f0f72da10589745fb3a8be3e0b24e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="combo-box-styles"></a>Kombinationsfeldstile
In MFC sind die folgenden Stile für Kombinationsfelder verfügbar.  
  
-   **CBS_AUTOHSCROLL** Scrollt den Text im Bearbeitungssteuerelement automatisch nach rechts, wenn der Benutzer am Zeilenende ein Zeichen eingibt. Wenn dieser Stil nicht festgelegt ist, ist nur Text zulässig, der in die rechteckige Begrenzung passt.  
  
-   **CBS_DISABLENOSCROLL** Das Listenfeld zeigt eine deaktivierte vertikale Scrollleiste an, wenn es nicht genügend Elemente enthält, um zu scrollen. Ohne diesen Stil wird die Scrollleiste ausgeblendet, wenn das Listenfeld nicht genügend Elemente enthält.  
  
-   **CBS_DROPDOWN** Ähnlich wie **CBS_SIMPLE**, außer dass das Listenfeld erst angezeigt wird, wenn der Benutzer ein Symbol neben dem Bearbeitungssteuerelement auswählt.  
  
-   **CBS_DROPDOWNLIST** Ähnlich wie **CBS_DROPDOWN**, außer dass das Bearbeitungssteuerelement durch ein Element mit statischem Text ersetzt wird, das die aktuelle Auswahl im Listenfeld anzeigt.  
  
-   **CBS_HASSTRINGS** Ein Ownerdrawn-Kombinationsfeld enthält Elemente, die aus Zeichenfolgen bestehen. Das Kombinationsfeld verwaltet den Arbeitsspeicher und die Zeiger für die Zeichenfolgen, sodass die Anwendung die `GetText` -Memberfunktion verwenden kann, um den Text für ein bestimmtes Element abzurufen.  
  
-   **CBS_LOWERCASE** Wandelt den gesamten Text sowohl im Auswahlfeld als auch in der Liste in Kleinbuchstaben um.  
  
-   **CBS_NOINTEGRALHEIGHT** Gibt an, dass die Größe des Kombinationsfelds genau der Größe entspricht, die von der Anwendung beim Erstellen des Kombinationsfelds angegeben wurde. Üblicherweise passt Windows die Größen von Kombinationsfeldern an, damit Elemente nicht nur teilweise angezeigt werden.  
  
-   **CBS_OEMCONVERT** In das Bearbeitungssteuerelement des Kombinationsfelds eingegebener Text wird vom ANSI-Zeichensatz in den OEM-Zeichensatz und wieder zurück zu ANSI konvertiert. Dies stellt eine ordnungsgemäße Zeichenkonvertierung sicher, wenn die Anwendung die Windows-Funktion `AnsiToOem` aufruft, um eine ANSI-Zeichenfolge im Kombinationsfeld in OEM-Zeichen zu konvertieren. Dieser Stil ist sehr nützlich für Kombinationsfelder, die Dateinamen enthalten, und kann nur auf Kombinationsfelder angewendet werden, die mit den Stilen **CBS_SIMPLE** oder **CBS_DROPDOWN** erstellt wurden.  
  
-   **CBS_OWNERDRAWFIXED** Der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich. Alle Elemente im Listenfeld weisen die gleiche Höhe auf.  
  
-   **CBS_OWNERDRAWVARIABLE** Der Besitzer des Listenfelds ist für das Zeichnen der Inhalte verantwortlich. Die Höhe der Elemente im Listenfeld ist variabel.  
  
-   **CBS_SIMPLE** Das Listenfeld wird immer angezeigt. Die aktuelle Auswahl im Listenfeld wird im Bearbeitungssteuerelement angezeigt.  
  
-   **CBS_SORT** Sortiert in das Listenfeld eingegebene Zeichenfolgen automatisch.  
  
-   **CBS_UPPERCASE** Wandelt den gesamten Text sowohl im Auswahlfeld als auch in der Liste in Großbuchstaben um.  
  
## <a name="see-also"></a>Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [CComboBox::Create] (Ccombobox class.md #ccombobox__create   



