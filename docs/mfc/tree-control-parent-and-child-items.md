---
title: Übergeordnete und untergeordnete Elemente Struktursteuerelement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1c56885300b05cfb038dd1a8484ae57648bf9357
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208431"
---
# <a name="tree-control-parent-and-child-items"></a>Übergeordnete und untergeordnete Elemente in einem Struktursteuerelement
Ein Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) haben eine Liste von Unterelementen, die zugeordneten untergeordneten Elemente aufgerufen werden. Ein Element, das eine oder mehrere untergeordnete Elemente verfügt, wird ein übergeordnetes Element aufgerufen. Ein untergeordnetes Element unter seinem übergeordneten Element angezeigt, und es wird eingerückt, um anzugeben, dass es zum übergeordneten Element untergeordnet ist. Ein Element, das kein übergeordnetes Element besitzt, wird am Anfang der Hierarchie und ein Stammelement aufgerufen.  
  
 Zu jedem Zeitpunkt der Status eines übergeordneten Elements der Liste der untergeordneten Elemente entweder erweitert oder reduziert. Wenn der Status erweitert ist, werden die untergeordneten Elemente unterhalb des übergeordneten Elements angezeigt. Wenn es ausgeblendet ist, werden die untergeordneten Elemente nicht angezeigt. Die Liste wird automatisch zwischen dem erweiterten und reduzierten Zustand wechselt, wenn der Benutzer das übergeordnete Element doppelklickt, oder, wenn das übergeordnete Element verfügt über die **TVS_HASBUTTONS** Stil, klickt der Benutzer die Schaltfläche mit dem übergeordneten Element verknüpft ist. Eine Anwendung kann erweitert oder reduziert die untergeordneten Elemente mithilfe der [erweitern](../mfc/reference/ctreectrl-class.md#expand) Member-Funktion.  
  
 Ein Element hinzufügen ein Strukturansicht-Steuerelement durch Aufrufen der [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Member-Funktion. Diese Funktion gibt ein Handle zurück. die **HTREEITEM** Typ, der das Element eindeutig identifiziert. Wenn Sie ein Element hinzufügen möchten, müssen Sie das Handle für das neue Element übergeordneten Elements angeben. Bei Angabe von **NULL** oder **TVI_ROOT** Wert anstelle eines übergeordneten Elements Handles in der [TVINSERTSTRUCT](/windows/desktop/api/commctrl/ns-commctrl-tagtvinsertstructa) Struktur oder *hParent* Parameter, das Element wird als ein Stammelement hinzugefügt.  
  
 Sendet ein Strukturansicht-Steuerelement eine [TVN_ITEMEXPANDING](/windows/desktop/Controls/tvn-itemexpanding) Benachrichtigung, wenn ein übergeordnetes Element der Liste der untergeordneten Elemente gerade erweitert oder reduziert werden. Die Benachrichtigung bietet Ihnen die Möglichkeit zu verhindern, dass die Änderung oder alle Attribute des übergeordneten Elements fest, die auf den Zustand der Liste der untergeordneten Elemente abhängig sind. Nach dem Ändern des Status der Liste, die Strukturansicht-Steuerelement sendet eine [TVN_ITEMEXPANDED](/windows/desktop/Controls/tvn-itemexpanded) Benachrichtigung.  
  
 Wenn eine Liste der untergeordneten Elemente erweitert wird, wird diese relativ zum übergeordneten Element eingezogen. Sie können die Größe des Einzugs festlegen, mit der [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) Memberfunktion oder rufen Sie die aktuelle Menge an, mit der [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) Member-Funktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

