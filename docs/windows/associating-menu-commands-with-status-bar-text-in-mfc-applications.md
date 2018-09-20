---
title: Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- status bars [C++], associating menu items
- menus [C++], status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 718766a8fc475f20bcbcc328973b38e486769d9c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389076"
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