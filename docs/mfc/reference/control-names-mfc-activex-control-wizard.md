---
title: Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.ctl.names
helpviewer_keywords:
- MFC ActiveX Control Wizard, control names
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
ms.openlocfilehash: a1b310de8cd8fcab1d880738faa7bd8b5b7cef32
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814097"
---
# <a name="control-names-mfc-activex-control-wizard"></a>Steuerelementnamen, MFC-ActiveX-Steuerelement-Assistent

Geben Sie die Namen für die Control-Klasse und die Page-Klasse, die Typnamen, und geben Sie die Bezeichner für das Steuerelement. Mit Ausnahme von **Kurznamen**, alle anderen Felder können unabhängig voneinander bearbeitet werden. Wenn Sie den Text für ändern **Kurznamen**, in den Namen der alle anderen Felder auf dieser Seite wird die Änderung übernommen. Diese Namenssystem ist so ausgelegt, alle Namen leicht identifizierbaren für Sie, wie Sie das Steuerelement entwickeln.

- **Kurzname**

   Geben Sie einen abgekürzten Namen für das Steuerelement. Dieser Name basiert standardmäßig auf den Projektnamen, die Sie angegeben haben, in der **neues Projekt** Dialogfeld. Der Namen, die, den Sie bereitstellen, bestimmt die Klassennamen, die Typnamen und die Typ-IDs, es sei denn, Sie diese Felder einzeln ändern.

- **Steuerelementklassenname**

   Standardmäßig der Namen der Steuerelementklasse basierend auf den kurzen Namen, mit `C` als Präfix und `Ctrl` als Suffix. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Name der Steuerelementklasse `CPriceCtrl`.

- **Steuerelement-h-Datei**

   Der Name der Headerdatei basiert standardmäßig auf den kurzen Namen, mit `Ctrl` als Suffix und `.h` als Dateierweiterung. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Headerdateiname `PriceCtrl.h`. Der Namen in dieses Feld sollte den Namen der Steuerelementklasse übereinstimmen.

- **Cpp-Steuerdatei**

   Der Name der Headerdatei basiert standardmäßig auf den kurzen Namen, mit `Ctrl` als Suffix und `.cpp` als Dateierweiterung. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Headerdateiname `PriceCtrl.cpp`. Der Name in dieses Feld sollte den Headernamen an übereinstimmen.

- **Steuerelement-Typname**

   Standardmäßig basiert auf den kurzen Namen, gefolgt von der Namen des Steuerelementtyps `Control`. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Typ-Klassennamen des Steuerelements `Price Control`. Wenn Sie den Wert in diesem Feld ändern, stellen Sie sicher, dass der Name eine Vererbung angibt.

- **Steuerelementtyp-ID**

   Legt fest, der Steuerelementtyp-ID der Steuerelement-Klasse. Das Steuerelement wird diese Zeichenfolge in die Registrierung geschrieben, wenn es zu einem Projekt hinzugefügt wird. Containeranwendungen verwenden diese Zeichenfolge zum Erstellen einer Instanz des Steuerelements.

   Standardmäßig basiert die Typ-ID des Steuerelements auf den Projektnamen, den Sie angegeben haben, in der **neues Projekt** (Dialogfeld), und der kurze Name. Dieser Name sollte den Namen übereinstimmen.

   Standardmäßig wird der Steuerelementtyp-ID wie folgt angezeigt:

   *ProjectName.ShortName*Ctrl.1

   Wenn Sie den kurzen Namen in diesem Dialogfeld ändern, wird der Steuerelementtyp-ID wie folgt angezeigt:

   *ProjectName.NewShortName*Ctrl.1

- **PropPage-Klassenname**

   Der Name der Eigenschaftenseitenklasse basiert standardmäßig auf den kurzen Namen, mit `C` als Präfix und `PropPage` als Suffix. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist die Klasse den Namen `CPricePropPage`. Dieser Name sollte den Klassennamen des Steuerelements angefügtem übereinstimmen `PropPage`.

- **PropPage-h-Datei**

   Standardmäßig der Namen der die Header-Datei basiert auf den kurzen Namen, mit als ein `PropPage` als Suffix und `.h` als Dateierweiterung. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Eigenschaftenseiten-Datei den Namen `PricePropPage.h`. Dieser Name sollte den Namen der Klasse übereinstimmen.

- **PropPage-cpp-Datei**

   Standardmäßig der Namen der Eigenschaft Auslagerungsdatei Implementierung basiert auf den kurzen Namen, mit als ein `PropPage` als Suffix und `.cpp` als Dateierweiterung. Z. B. wenn das Steuerelement der kurze Name ist `Price`, ist der Eigenschaftenseiten-Datei den Namen `PricePropPage.cpp`. Dieser Name sollte den Headerdateinamen übereinstimmen.

- **PropPage-Typname**

   Standardmäßig basiert auf den kurzen Namen, gefolgt von der Eigenschaftennamen für Seite Art `Property Page`. Z. B. wenn das Steuerelement der kurze Name ist `Price`, der Eigenschaftsname für Seite Art ist `Price Property Page`. Wenn Sie den Wert in diesem Feld ändern, stellen Sie sicher, dass die Namen die Steuerelementklasse angibt.

- **PropPage-Typ-ID**

   Wird die ID der Eigenschaft Page-Klasse. Das Steuerelement schreibt diese Zeichenfolge in der Registrierung, wenn es zu einem Projekt angewendet wird. Eine containeranwendung verwendet diese Zeichenfolge zum Erstellen einer Instanz der Eigenschaftenseite des Steuerelements.

   Standardmäßig basiert die Eigenschaftenseiten Typ-ID auf den Projektnamen, den Sie angegeben haben, in der **neues Projekt** (Dialogfeld), und der kurze Name. Dieser Name sollte den Namen übereinstimmen.

   Standardmäßig wird die Eigenschaftenseiten Typ-ID wie folgt angezeigt:

   *ProjectName.ShortName*PropPage.1

   Wenn Sie den kurzen Namen in diesem Dialogfeld ändern, wird die Eigenschaftenseiten Typ-ID wie folgt angezeigt:

   *ProjectName.NewShortName*PropPage.1

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/mfc-activex-control-wizard.md)<br/>
[Anwendungseinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)<br/>
[Steuerelementeinstellungen, MFC-ActiveX-Steuerelement-Assistent](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)<br/>
[Für Visual C++-Projekte erstellte Dateitypen](../../build/reference/file-types-created-for-visual-cpp-projects.md)

