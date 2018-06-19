---
title: Übergeordnete und untergeordnete Elemente Struktursteuerelement | Microsoft Docs
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
ms.openlocfilehash: 260cbf640f6c57e4b145d01e8f883025a4dc6507
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382514"
---
# <a name="tree-control-parent-and-child-items"></a>Übergeordnete und untergeordnete Elemente in einem Struktursteuerelement
Jedes Element in einem Strukturansicht-Steuerelement ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) können Sie eine Liste von Unterelementen, die mit ihm verknüpften untergeordneten Elemente aufgerufen werden. Ein Element, das eine oder mehrere untergeordnete Elemente verfügt, wird ein übergeordnetes Element aufgerufen. Ein untergeordnetes Element wird unter seinem übergeordneten Element und eingezogen wird, um anzugeben, dass es zum übergeordneten Element untergeordnet ist. Ein Element, das kein übergeordnetes Element besitzt, wird am oberen Rand der Hierarchie und ein Stammelement aufgerufen.  
  
 Einem bestimmten Zeitpunkt kann der Status von einem übergeordneten Element der Liste der untergeordneten Elemente erweitert oder reduziert werden. Wenn der Status erweitert ist, werden die untergeordneten Elemente unterhalb des übergeordneten Elements angezeigt. Wenn es reduziert ist, werden die untergeordneten Elemente nicht angezeigt. Die Liste wird automatisch zwischen dem erweiterten und reduzierten Zustand wechselt, wenn der Benutzer das übergeordnete Element doppelklickt oder, wenn das übergeordnete Element verfügt über die **TVS_HASBUTTONS** Stil, klickt der Benutzer die Schaltfläche mit dem übergeordneten Element verknüpft sind. Eine Anwendung kann erweitern oder reduzieren Sie die untergeordneten Elemente mithilfe der [erweitern](../mfc/reference/ctreectrl-class.md#expand) Memberfunktion.  
  
 Ein Element wird einem Strukturansicht-Steuerelement hinzufügen, durch Aufrufen der [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) Memberfunktion. Diese Funktion gibt ein Handle für die **HTREEITEM** Typ, der das Element eindeutig identifiziert. Wenn Sie ein Element hinzufügen möchten, müssen Sie das Handle für das neue Element übergeordneten Elements angeben. Bei Angabe von **NULL** oder **TVI_ROOT** Wert anstelle von einem übergeordneten Element Handle in die [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) Struktur oder `hParent` Parameter, das Element wird als Stamm hinzugefügt Element.  
  
 Sendet ein Strukturansicht-Steuerelement eine [TVN_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) Benachrichtigung bei einem übergeordneten Element der Liste der untergeordneten Elemente erweitert oder reduziert werden. Die Benachrichtigung bietet Ihnen die Gelegenheit, um zu verhindern, dass die Änderung oder die Attribute des übergeordneten Elements festzulegen, die den Status der Liste von untergeordneten Elementen abhängig sind. Nach dem Ändern des Zustands der Liste, das Strukturansicht-Steuerelement sendet eine [TVN_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533) benachrichtigungsmeldung.  
  
 Wenn eine Liste von untergeordneten Elementen erweitert wird, ist er relativ zum übergeordneten Element eingerückt. Sie können die Größe des Einzugs festlegen, mit der [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) Memberfunktion oder rufen Sie die aktuelle Menge mithilfe der [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) Memberfunktion.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTreeCtrl](../mfc/using-ctreectrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

