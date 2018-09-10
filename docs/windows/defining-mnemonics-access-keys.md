---
title: Definieren von mnemonischen Zeichen (Zugriffstasten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls [C++], mnemonics
- access keys [C++], checking
- mnemonics [C++], checking for duplicate
- mnemonics
- mnemonics [C++], dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ab44d406d71eb1cc23c803f1074636e9e5cc38a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316236"
---
# <a name="defining-mnemonics-access-keys"></a>Definieren von Tastenkombinationen

In der Regel Benutzer über die Tastatur verschieben den Eingabefokus von einem Steuerelement zu einem anderen in einem Dialogfeld mit den **Registerkarte** und **Pfeil** Schlüssel. Allerdings können Sie eine Zugriffstaste (ein mnemonisches oder einfach zu merkenden-Name) definieren, die Benutzern ermöglicht, ein Steuerelement auswählen, indem Sie eine Taste zu drücken.

### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement mit einem sichtbaren Titel (Schaltflächen, Kontrollkästchen und Optionsfelder)

1. Wählen Sie das Steuerelement im Dialogfeld ein.

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in die **Beschriftung** -Eigenschaft, geben Sie einen neuen Namen für das Steuerelement, ein kaufmännisches (`&`) vor den Buchstaben als Zugriffstaste für dieses Steuerelement werden soll. Beispielsweise `&Radio1`.

3. Drücken Sie die **EINGABETASTE**.

   Ein Unterstrich angezeigt, die angezeigte Beschriftung an den Zugriffsschlüssel, z. B. **R**adio1.

### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement ohne sichtbare Beschriftung

1. Erstellen Sie eine Beschriftung für das Steuerelement mit einem **statischen Text** steuern, der [Toolbox](/visualstudio/ide/reference/toolbox).

2. Geben Sie in der Beschriftung des statischen Text, ein kaufmännisches und-Zeichen (`&`) vor dem Buchstaben als Zugriffstaste verwendet werden sollen.

3. Stellen Sie sicher, dass das Steuerelement statischer Text unmittelbar vor dem Steuerelement befindet, die, das Sie in der Aktivierreihenfolge "Bezeichnungen".

Alle Zugriffstasten in einem Dialogfeld sollte eindeutig sein.

### <a name="to-check-for-duplicate-access-keys"></a>Zu prüfen, doppelte Zugriffstasten

1. Auf der **Format** Menü klicken Sie auf **Mnemonik**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)  
[Steuerelemente](../mfc/controls-mfc.md)