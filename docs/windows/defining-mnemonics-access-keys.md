---
title: Definieren von Zugriffstasten (Zugriffsschlüssel) | Microsoft Docs
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
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
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
ms.openlocfilehash: a60cf597a88fcf7038848be6c9e2d31269f6a906
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873692"
---
# <a name="defining-mnemonics-access-keys"></a>Definieren von Tastenkombinationen
In der Regel verschieben Tastaturbenutzer den Eingabefokus von einem Steuerelement in einem Dialogfeld mit der TAB-Taste oder Schlüsseln. Allerdings können Sie eine Zugriffstaste (einen mnemonischen oder leicht zu merkenden Namen) definieren, die Benutzern ermöglicht, ein Steuerelement auswählen, eine einzelne-Taste drücken.  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement mit einer sichtbaren Beschriftung (Schaltflächen, Kontrollkästchen und Optionsfelder)  
  
1.  Wählen Sie das Steuerelement im Dialogfeld.  
  
2.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in der **Beschriftung** -Eigenschaft, geben Sie einen neuen Namen für das Steuerelement, ein kaufmännisches (**&**) vor den Buchstaben als soll der der Zugriffsschlüssel für dieses Steuerelement. Beispielsweise `&Radio1`.  
  
3.  Drücken Sie die **EINGABETASTE**.  
  
     Ein Unterstrich angezeigt, die angezeigte Beschriftung an, z. B. die Zugriffstaste **R**adio1.  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Definieren Sie eine Zugriffstaste für ein Steuerelement ohne sichtbare Beschriftung  
  
1.  Stellen Sie eine Beschriftung für das Steuerelement mit einer **statischer Text** steuern, der [Toolbox](/visualstudio/ide/reference/toolbox).  
  
2.  Geben Sie in der Beschriftung statischen Text, ein kaufmännisches und-Zeichen (**&**) vor dem Buchstaben, die Sie als Zugriffstaste verwenden möchten.  
  
3.  Stellen Sie sicher, dass das Steuerelement statischer Text vorausgeht sofort das Steuerelement, das sie in der Aktivierreihenfolge "Bezeichnungen".  
  
 Alle Zugriffstasten in einem Dialogfeld sollte eindeutig sein.  
  
#### <a name="to-check-for-duplicate-access-keys"></a>Um die Prüfung auf doppelte Zugriffstasten  
  
1.  Auf der **Format** Menü klicken Sie auf **Mnemonik**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

