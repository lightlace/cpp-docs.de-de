---
title: Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen | Microsoft Docs
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
ms.openlocfilehash: 17326bdb8fe01c9ad329db0a6c7e8178fdbb25e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864241"
---
# <a name="associating-menu-commands-with-status-bar-text-in-mfc-applications"></a>Verknüpfen von Menübefehlen mit Statusleistentext in MFC-Anwendungen
Die Anwendung kann für die vom Benutzer auszuwählenden Menübefehle beschreibenden Text anzeigen. Dazu müssen Sie im Eigenschaftenfenster jedem Menübefehl mit der **Eingabeaufforderung** -Eigenschaft eine Textzeichenfolge zuweisen. Wenn eine Zeichenfolge in der [Zeichenfolgentabelle](../windows/string-editor.md) die gleiche ID wie der Befehl aufweist, zeigt eine MFC-Anwendung automatisch diese Zeichenfolgenressource in der Statusleiste der ausgeführten Anwendung an, wenn ein Benutzer auf ein Menüelement zeigt.  
  
### <a name="to-associate-a-menu-command-with-a-status-bar-text-string"></a>So ordnen Sie einer Statusleisten-Zeichenfolge ein Menübefehl zu  
  
1.  Wählen Sie im **Menü** -Editor den Menübefehl aus.  
  
2.  Geben Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)den zugeordneten Statusleistentext im Feld **Eingabeaufforderung** ein.  
  

  
 **Anforderungen**  
  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)   
 [Menü-Editor](../windows/menu-editor.md)