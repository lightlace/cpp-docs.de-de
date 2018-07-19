---
title: Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88f86a8f22bae990261be5150755a26d50d4bef8
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950460"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten
Wenn Sie mit DDX-Funktionen vertraut sind, können Sie die Steuerelementeigenschaft in der [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) Typsicherer Zugriff erstellen. Dieser Ansatz ist einfacher als das Erstellen von Steuerelementen ohne Code-Assistenten.  
  
 Wenn Sie einfach auf den Wert eines Steuerelements zugreifen möchten, stellt er DDX bereit. Wenn Sie mehr als den Wert eines Steuerelements zugreifen möchten, verwenden Sie mit dem Assistenten zum Hinzufügen von Member eigener Dialogfeldklassen eine Membervariable der entsprechenden Klasse hinzu. Fügen Sie diese Membervariable an die Steuerelementeigenschaft.  
  
 Membervariablen können eine Steuerelementeigenschaft statt einer Objekteigenschaft Wert haben. Die Value-Eigenschaft bezieht sich auf den Typ der Daten aus dem Steuerelement zurückgegeben werden, z. B. `CString` oder **Int**. Die Steuerelementeigenschaft ermöglicht den direkten Zugriff auf das Steuerelement über einen Datenmember, dessen Typ der Steuerelementklassen in MFC, z. B. ist `CButton` oder `CEdit`.  
  
> [!NOTE]
>  Für ein bestimmtes Steuerelement Sie, falls gewünscht, mehrere Membervariablen mit der Value-Eigenschaft und darf höchstens eine Membervariable mit der Steuerelementeigenschaft möglich. Sie können nur eine MFC-Objekt an ein Steuerelement zugeordnet werden, da mehrere Objekte, die angefügt werden, ein Steuerelement oder ein anderes Fenster, zu einer Mehrdeutigkeit in der meldungszuordnung führen würde.  
  
 Dieses Objekt können Memberfunktionen für das Steuerelementobjekt aufgerufen werden. Solche Aufrufe wirken sich auf das Steuerelement im Dialogfeld. Beispiel für ein Kontrollkästchen-Steuerelement dargestellt durch eine Variable *M_Checkbox*, vom Typ `CButton`, rufen Sie:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 Hier die Membervariable *M_Checkbox* dient den gleichen Zweck wie die Memberfunktion `GetMyCheckbox` in angezeigten [als Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md). Ist dieses Kontrollkästchen nicht das Kontrollkästchen für eine automatische, weiterhin, benötigen Sie einen Handler in eigener Dialogfeldklassen für BN_CLICKED Steuerelement-Benachrichtigung auf die Schaltfläche geklickt wird.  
  
 Weitere Informationen zu Steuerelementen finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Typsicherer Zugriff auf Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)

