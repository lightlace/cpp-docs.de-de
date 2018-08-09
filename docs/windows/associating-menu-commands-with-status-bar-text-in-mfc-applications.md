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
- status bars, associating menu items
- menus, status bar text
ms.assetid: 757c0e02-bc97-493f-bccd-6cc6887ebc64
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d868c9270e23e2ee1fa0dcdc1845d9762cefb16c
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649400"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen
Die Anwendung kann für die vom Benutzer auszuwählenden Menübefehle beschreibenden Text anzeigen. Zu diesem Zweck eine Textzeichenfolge zuweisen, um jedem Menübefehl mit der **Eingabeaufforderung** -Eigenschaft in der **Eigenschaften** Fenster. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../windows/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>So ordnen Sie einer Statusleisten-Zeichenfolge ein Menübefehl zu  
  
1.  Wählen Sie im **Menü** -Editor den Menübefehl aus.  
  
2.  Geben Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)den zugeordneten Statusleistentext im Feld **Eingabeaufforderung** ein.  
  
## <a name="requirements"></a>Anforderungen  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)   
 [Menü-Editor](../windows/menu-editor.md)