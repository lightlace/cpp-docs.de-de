---
title: Registerkarten und Registerkarte steuern Attribute | Microsoft-Dokumentation
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
ms.openlocfilehash: c02f939c9f9314f3e24921879836c2743ae7d5ea
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223281"
---
# <a name="tabs-and-tab-control-attributes"></a>Registerkarten und Attribute von Registerkarten-Steuerelementen
Sie haben viel Kontrolle über das Aussehen und Verhalten von Registerkarten, aus denen ein Registerkarten-Steuerelement ([CTabCtrl](../mfc/reference/ctabctrl-class.md)). Jede Registerkarte kann es sich um eine Bezeichnung, ein Symbol, ein Zustand und eine anwendungsdefinierte 32-Bit-Wert zugeordnet werden. Für jede Registerkarte können Sie das Symbol, die Bezeichnung oder beides anzeigen.  
  
 Darüber hinaus kann jedes Registerelement haben drei mögliche Zustände: gedrückt oder nicht gedrückt hoveraktiviert hervorgehoben. Dieser Zustand kann nur festgelegt werden, durch Ändern eines vorhandenen Registerkartenelements. Zum Ändern eines vorhandenen Registerkartenelements Abrufen mit einem Aufruf von [GetItem](../mfc/reference/ctabctrl-class.md#getitem), Ändern der `TCITEM` Struktur (insbesondere die *dwState-Datenmember* und *den DwStateMask* -Datenmember ), und klicken Sie dann die geänderte zurückgeben `TCITEM` Struktur mit einem Aufruf von [SetItem](../mfc/reference/ctabctrl-class.md#setitem). Wenn Sie die Element-Zustände aller Elemente der Registerkarte in löschen müssen eine `CTabCtrl` Objekt, rufen Sie [DeselectAll](../mfc/reference/ctabctrl-class.md#deselectall). Diese Funktion setzt den Status aller Registerkartenelemente "oder" alle Elemente mit Ausnahme des derzeit ausgewählten zurück.  
  
 Der folgende Code löscht den Zustand aller Elemente der Registerkarte und anschließend wird den Status des dritten Elements geändert:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#32](../mfc/codesnippet/cpp/tabs-and-tab-control-attributes_1.cpp)]  
  
 Weitere Informationen über Attribute von Registerkarten finden Sie unter [Registerkarten und Attribute von Registerkarten](/windows/desktop/Controls/tab-controls) im Windows SDK. Weitere Informationen zum Hinzufügen von Registerkarten zum Registerkarten-Steuerelement finden Sie unter [Hinzufügen von Registerkarten zum Registersteuerelement](../mfc/adding-tabs-to-a-tab-control.md) weiter unten in diesem Thema.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

