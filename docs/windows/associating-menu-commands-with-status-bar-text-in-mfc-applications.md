---
title: Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen
ms.date: 11/04/2016
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
ms.openlocfilehash: fc39695358a9c1f2f62878487a5e4fedf5db2b82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468886"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen

Die MFC-Anwendung kann beschreibenden Text für jeden der Menübefehle im angezeigt, die ein Benutzer auswählen kann. Zu diesem Zweck eine Textzeichenfolge zuweisen, um jedem Menübefehl mit der **Eingabeaufforderung** -Eigenschaft in der **Eigenschaften** Fenster. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../windows/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.

### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>So ordnen Sie einer Statusleisten-Zeichenfolge ein Menübefehl zu

1. Wählen Sie im **Menü** -Editor den Menübefehl aus.

2. Geben Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)den zugeordneten Statusleistentext im Feld **Eingabeaufforderung** ein.

## <a name="requirements"></a>Anforderungen

MFC

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)<br/>
[Menü-Editor](../windows/menu-editor.md)