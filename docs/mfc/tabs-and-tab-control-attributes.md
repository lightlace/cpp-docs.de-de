---
title: Registerkarten und Registerkarte steuern Attribute | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- attributes [MFC], reference topics
- tab controls [MFC], attributes
- tabs [MFC]
- tabs [MFC], attributes
- CTabCtrl class [MFC], tab control attributes
ms.assetid: ecf190cb-f323-4751-bfdb-766dbe6bb553
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd2129ad4b2dc075893a730c0ba75de96dbebea0
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36952858"
---
# <a name="tabs-and-tab-control-attributes"></a>Registerkarten und Attribute von Registerkarten-Steuerelementen
Sie haben erhebliche Kontrolle über das Aussehen und Verhalten der Registerkarten, aus denen ein Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Jede Registerkarte kann es sich um eine Bezeichnung, ein Symbol, ein Elementstatus und eine anwendungsdefinierte 32-Bit-Wert zugeordnet werden. Für jede Registerkarte können Sie das Symbol ", die Bezeichnung oder beides anzeigen.  
  
 Darüber hinaus kann jedes Registerkartenelement haben drei mögliche Zustände: gedrückt bzw. nicht gedrückt hoveraktiviert hervorgehoben. Dieser Status kann nur durch Ändern eines vorhandenen Registerkartenelements festgelegt werden. Zum Ändern eines vorhandenen Registerkartenelements abrufen, mit einem Aufruf von [GetItem](../mfc/reference/ctabctrl-class.md#getitem), Ändern der `TCITEM` Struktur (insbesondere die *dwState-Datenmember* und *den DwStateMask* -Datenmember ), und klicken Sie dann das geänderte zurückgeben `TCITEM` Struktur mit einem Aufruf von [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Wenn Sie die Zustände aller Elemente der Registerkarte im deaktivieren müssen eine `CTabCtrl` Objekt, rufen Sie [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Diese Funktion setzt den Zustand aller Registerkartenelemente oder alle Elemente mit Ausnahme des derzeit ausgewählten.  
  
 Der folgende Code löscht den Zustand aller Elemente der Registerkarte "und ändert dann den Status des dritten Elements:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 Weitere Informationen über Attribute von Registerkarten finden Sie unter [Registerkarten und Attribute von Registerkarten](http://msdn.microsoft.com/library/windows/desktop/bb760550) im Windows SDK. Weitere Informationen zum Hinzufügen von Registerkarten zum Registersteuerelement finden Sie unter [Hinzufügen von Registerkarten zum Registersteuerelement](../mfc/adding-tabs-to-a-tab-control.md) weiter unten in diesem Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

