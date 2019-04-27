---
title: Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: bf3ecf3016fcc15bd4ada7a15208acd9a04ca0a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180862"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten

Wenn Sie mit DDX-Funktionen vertraut sind, können Sie die Eigenschaft des Steuerelements in der [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) Typsicherer Zugriff zu erstellen. Dieser Ansatz ist einfacher als das Erstellen von Steuerelementen ohne Code-Assistenten.

Wenn Sie einfach den Zugriff auf den Wert eines Steuerelements möchten, bietet DDX es. Wenn Sie mehr als den Wert eines Steuerelements zugreifen möchten, verwenden Sie den Assistent zum Hinzufügen von Membervariablen eigener Dialogfeldklassen eine Membervariable der entsprechenden Klasse hinzu. Fügen Sie diese Membervariable, an der Eigenschaft des Steuerelements.

Membervariablen haben eine Steuerelementeigenschaft, anstatt eine Value-Eigenschaft. Die Value-Eigenschaft bezieht sich auf den Typ der Daten, die aus dem Steuerelement, zurückgegeben werden, z. B. `CString` oder **Int**. Die Eigenschaft des Steuerelements ermöglicht den direkten Zugriff auf das Steuerelement über ein Datenelement, dessen Typ eine der Steuerelementklassen in MFC, z. B. ist `CButton` oder `CEdit`.

> [!NOTE]
>  Für ein bestimmtes Steuerelement an können, Sie Wenn Sie möchten, mehrere Membervariablen mit dem Value-Eigenschaft und höchstens eine Membervariable mit der Eigenschaft des Steuerelements verwenden. Sie haben nur eine MFC-Objekt zu einem Steuerelement zugeordnet werden, da mehrere Objekte, die angefügt werden, ein Steuerelement oder einem anderen Fenster zu einer Mehrdeutigkeit in der meldungszuordnung führen würde.

Sie können dieses Objekt verwenden, um einen beliebigen Member-Funktionen für das Steuerelementobjekt aufrufen. Solche Aufrufe wirken sich auf das Steuerelement im Dialogfeld. Zum Beispiel für ein Kontrollkästchen-Steuerelement dargestellt, durch eine Variable *M_Checkbox*, des Typs `CButton`, rufen Sie:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Hier die Membervariable *M_Checkbox* dient demselben Zweck wie die Member-Funktion `GetMyCheckbox` Siehe [Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md). Ist dieses Kontrollkästchen nicht das Kontrollkästchen für eine automatische, immer noch müssten Sie einen Handler in der Dialogfeldklasse für den BN_CLICKED Steuerelement-Benachrichtigung, wenn die Schaltfläche geklickt wird.

Weitere Informationen zu Steuerelementen, finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).

## <a name="see-also"></a>Siehe auch

[Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)
