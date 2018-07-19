---
title: Zuordnen von Tastenkombinationen zu Menübefehlen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], checking
- menus, shortcut keys
- keyboard shortcuts [C++], command assignments
- access keys [C++], assigning
- mnemonics, adding to menus
- keyboard shortcuts [C++], uniqueness checking
- mnemonics, uniqueness checking
- Check Mnemonics command
ms.assetid: fbcf1a00-af6a-4171-805a-0ac01d4e8b0d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 44a21e5930d0d8f2fcaad79cc5cef5bc984ad8b5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857898"
---
# <a name="assigning-access-keys-to-menu-commands"></a>Zuordnen von Tastenkombinationen zu Menübefehlen
Sie können Ihren Menüs und Menübefehlen eine Zugriffstaste (ein mnemonisches Zeichen, das dem Benutzer die Auswahl des Menüs mit der Tastatur ermöglicht) zuweisen.  
  
### <a name="to-assign-an-access-shortcut-key-to-a-menu-command"></a>So weisen Sie einem Menübefehl eine Zugriffstaste (Tastenkombination) zu  
  
1.  Geben Sie vor einem Buchstaben im Namen des Menüs oder Befehls ein kaufmännisches Und-Zeichen (**&**) ein, um diesen Buchstaben als die entsprechende Zugriffstaste festzulegen. Beispielsweise legt „&Datei“ ALT+D als Tastenkombination für das Dateimenü in Anwendungen fest, die für Microsoft Windows erstellt wurden.  
  
     Das Menüelement gibt einen sichtbaren Hinweis darauf, dass einem der Buchstaben eine Zugriffstaste zugeordnet ist. Der Buchstabe, der auf das kaufmännische Und-Zeichen folgt, wird unterstrichen dargestellt (abhängig vom Betriebssystem).  
  
    > [!NOTE]
    >  Achten Sie darauf, dass alle Zugriffstasten in einem Menü eindeutig sind, indem Sie mit der rechten Maustaste auf das Menü klicken und im Kontextmenü **Mnemonik überprüfen** auswählen.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Menü-Editor](../windows/menu-editor.md)