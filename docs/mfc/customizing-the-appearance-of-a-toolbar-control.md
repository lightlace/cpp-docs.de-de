---
title: Anpassen der Darstellung eines Symbolleisten-Steuerelements | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- TBSTYLE_
dev_langs:
- C++
helpviewer_keywords:
- flat toolbars
- CToolBar class [MFC], styles
- transparent toolbars
- TBSTYLE_ styles [MFC]
- CToolBarCtrl class [MFC], object styles
- toolbar controls [MFC], style
ms.assetid: fd0a73db-7ad1-4fe4-889b-02c3980f49e8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 48825a264b7d82152f47e70c5911bea400c313db
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36932116"
---
# <a name="customizing-the-appearance-of-a-toolbar-control"></a>Anpassen der Darstellung eines Symbolleisten-Steuerelements
Klasse `CToolBarCtrl` bietet viele Formate, die die Darstellung (und in einigen Fällen Verhalten) des Symbolleistenobjekts beeinflussen. Ändern Sie die Symbolleistenobjekt durch Festlegen der `dwCtrlStyle` Parameter von der `CToolBarCtrl::Create` (oder `CToolBar::CreateEx`) Memberfunktion, die bei der Erstellung von Toolbar-Steuerelement.  
  
 Die folgenden Stile wirken sich auf die Schaltflächen der Symbolleiste der Aspekt "3D" und die Platzierung des Schaltflächentexts:  
  
-   **TBSTYLE_FLAT** erstellt eine flache Symbolleiste, in dem die Symbolleiste und die Schaltflächen transparent sind. Als Schaltflächentext wird unter der Schaltfläche Bitmaps angezeigt. Wenn dieses Format verwendet wird, wird die Schaltfläche "" unterhalb der Cursor automatisch hervorgehoben.  
  
-   **TBSTYLE_TRANSPARENT** erstellt eine transparente Symbolleiste. Bei einer transparenten Symbolleiste die Symbolleiste wird transparent die Schaltflächen sind jedoch nicht. Als Schaltflächentext wird unter der Schaltfläche Bitmaps angezeigt.  
  
-   **TBSTYLE_LIST** stellen Schaltfläche Text rechts neben der Schaltfläche Bitmaps.  
  
> [!NOTE]
>  Repaint Probleme verhindern das **TBSTYLE_FLAT** und **TBSTYLE_TRANSPARENT** Stile sollte festgelegt werden, bevor das Symbolleistenobjekt sichtbar ist.  
  
 Die folgenden Stile bestimmen, ob die Symbolleiste einen Benutzer ermöglicht zu positionieren von einzelnen Schaltflächen in einem Symbolleistenobjekt, das mithilfe von Drag & drop:  
  
-   **TBSTYLE_ALTDRAG** ermöglicht es Benutzern, eine Symbolleisten-Schaltfläche Position ändern, indem Sie ALT gedrückt, ziehen. Wenn dieser Stil nicht angegeben wird, muss der Benutzer eine Schaltfläche zu ziehen gedrückter UMSCHALTTASTE.  
  
    > [!NOTE]
    >  Die **CCS_ADJUSTABLE** Stil muss angegeben werden, zum Aktivieren des Symbolleistenschaltflächen gezogen wird.  
  
-   **TBSTYLE_REGISTERDROP** generiert **TBN_GETOBJECT** Benachrichtigung Nachrichten anfordern Zielobjekte löschen, wenn der Mauszeiger über die Schaltflächen der Symbolleiste bewegt.  
  
 Die übrigen Formate beeinflussen visuelle und nicht sichtbare Aspekte des Symbolleistenobjekts:  
  
-   **TBSTYLE_WRAPABLE** erstellt eine Symbolleiste, die mehrere Zeilen mit Schaltflächen aufweisen können. Schaltflächen der Symbolleiste können zur nächsten Zeile "umschließen" werden, wenn die Symbolleiste nicht breit genug ist, alle Schaltflächen in der gleichen Zeile eingeschlossen wird. Einbindung erfolgt nach Trennung und nongroup Grenzen.  
  
-   **TBSTYLE_CUSTOMERASE** generiert **NM_CUSTOMDRAW** Benachrichtigung bei der Verarbeitung von Nachrichten **WM_ERASEBKGND** Nachrichten.  
  
-   **TBSTYLE_TOOLTIPS** erstellt ein QuickInfo-Steuerelement, mit dem eine Anwendung beschreibenden Text für die Schaltflächen auf der Symbolleiste angezeigt.  
  
 Eine vollständige Liste der Symbolleiste Formatvorlagen und erweiterte Formate, finden Sie unter [Toolbar-Steuerelement und Schaltflächenstile](http://msdn.microsoft.com/library/windows/desktop/bb760439) und [erweiterten Stile, die Symbolleiste](http://msdn.microsoft.com/library/windows/desktop/bb760430) im Windows SDK.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

