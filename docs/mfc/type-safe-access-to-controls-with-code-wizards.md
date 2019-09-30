---
title: Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten
ms.date: 11/04/2016
helpviewer_keywords:
- DDX (dialog data exchange), access to controls
- code wizards
- dialog boxes [MFC], access to controls
- dialog box controls [MFC], accessing
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
ms.openlocfilehash: fefa722209d37e2612201c4471e5764f9d71f27a
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685039"
---
# <a name="type-safe-access-to-controls-with-code-wizards"></a>Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten

Wenn Sie mit DDX-Funktionen vertraut sind, können Sie die Control-Eigenschaft im [Assistenten zum Hinzufügen](../ide/add-member-variable-wizard.md) von Element Variablen verwenden, um typsicheren Zugriff zu erstellen. Diese Vorgehensweise ist einfacher als das Erstellen von Steuerelementen ohne Code-Assistenten.

Wenn Sie einfach auf den Wert eines Steuer Elements zugreifen möchten, stellt DDX es bereit. Wenn Sie mehr als auf den Wert eines Steuer Elements zugreifen möchten, verwenden Sie den Assistenten zum Hinzufügen von Element Variablen, um der Dialogfeld Klasse eine Member-Variable der entsprechenden Klasse hinzuzufügen. Fügen Sie diese Element Variable an die Steuerelement Eigenschaft an.

Element Variablen können eine Steuerelement Eigenschaft anstelle einer Value-Eigenschaft aufweisen. Die Value-Eigenschaft bezieht sich auf den Datentyp, der vom Steuerelement zurückgegeben wird, z. b. `CString` oder **int**. Die Control-Eigenschaft ermöglicht den direkten Zugriff auf das Steuerelement über einen Datenmember, dessen Typ eine der Steuerelement Klassen in MFC ist, z. b. `CButton` oder `CEdit`.

> [!NOTE]
>  Für ein bestimmtes Steuerelement können Sie, wenn gewünscht, über mehrere Element Variablen mit der Value-Eigenschaft und höchstens eine Element Variable mit der Control-Eigenschaft verfügen. Einem Steuerelement kann nur ein MFC-Objekt zugeordnet werden, da mehrere Objekte, die an ein Steuerelement angefügt sind, oder ein beliebiges anderes Fenster in der Meldungs Zuordnung zu einer Mehrdeutigkeit führen würde.

Mit diesem Objekt können Sie beliebige Element Funktionen für das Steuerelement Objekt aufzurufen. Solche Aufrufe wirken sich auf das Steuerelement im Dialogfeld aus. Beispielsweise könnten Sie für ein Kontrollkästchen-Steuerelement, das durch eine Variable *m_Checkbox*vom Typ `CButton` dargestellt wird, Folgendes aufzurufen:

[!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/cpp/type-safe-access-to-controls-with-code-wizards_1.cpp)]

Hier erfüllt die Member-Variable *m_Checkbox* denselben Zweck wie die Element Funktion `GetMyCheckbox` unter [typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md). Wenn das Kontrollkästchen kein automatisches Kontrollkästchen ist, benötigen Sie für die BN_CLICKED-Steuerelement-Benachrichtigungs Meldung, wenn auf die Schaltfläche geklickt wird, trotzdem einen Handler in der Dialogfeld Klasse.

Weitere Informationen zu-Steuerelementen finden Sie unter Steuer [Elemente](../mfc/controls-mfc.md).

## <a name="see-also"></a>Siehe auch

[Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Arbeiten mit Dialog Feldern in MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Typsicherer Zugriff auf Steuerelemente ohne Code-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)
