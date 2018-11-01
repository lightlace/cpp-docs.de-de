---
title: Zuordnen von Tastenkombinationen zu Menübefehlen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- access keys [C++], checking
- menus [C++], shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics [C++], adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics [C++], uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
ms.openlocfilehash: 7a3302f7744bf5c3a0cbaac96de04d9f649fac10
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587329"
---
# <a name="assigning-access-keys-to-menu-commands-c"></a>Zuordnen von Tastenkombinationen zu Menübefehlen (C++)

In einem C++-Projekt können Sie eine Zugriffstaste (ein mnemonisches Zeichen, die dem Benutzer ermöglicht, wählen Sie im Menü mit der Tastatur) zuweisen, Ihren Menüs und Menübefehlen.

### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>So weisen Sie einem Menübefehl eine Zugriffstaste (Tastenkombination) zu

1. Geben Sie ein kaufmännisches und-Zeichen (`&`) vor einen Buchstaben im Namen des Menüs oder Befehlsnamen, um diesen Buchstaben als die entsprechende Zugriffstaste festzulegen. Z. B. "& Datei" legt **Alt**+**F** als Tastenkombination für den **Datei** Menü in Anwendungen für Microsoft Windows.

   Das Menüelement gibt einen sichtbaren Hinweis darauf, dass einem der Buchstaben eine Zugriffstaste zugeordnet ist. Der Buchstabe, der auf das kaufmännische Und-Zeichen folgt, wird unterstrichen dargestellt (abhängig vom Betriebssystem).

   > [!NOTE]
   > Achten Sie darauf, dass alle Zugriffstasten in einem Menü eindeutig sind, indem Sie mit der rechten Maustaste auf das Menü klicken und im Kontextmenü **Mnemonik überprüfen** auswählen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)