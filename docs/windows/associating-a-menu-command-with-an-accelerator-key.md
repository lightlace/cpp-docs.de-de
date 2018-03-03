---
title: "Verknüpfen eines Menübefehls mit einer Zugriffstaste | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, menu association
- commands, associating menu commands with accelerator keys
- menu commands, associating with keyboard shortcuts
ms.assetid: ad2de43f-b20a-4c9f-bda8-0420179da48c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 79a16cf8d67fb7a6a45043c28455a7ed22f90ffa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="associating-a-menu-command-with-an-accelerator-key"></a>Verknüpfen eines Menübefehls mit einer Zugriffstaste
Häufig ist es wünschenswert, dass ein Menübefehl und eine Tastenkombination den gleichen Programmbefehl ausgeben. Sie erreichen dies, indem Sie im Menü-Editor dem Menübefehl und einem Eintrag in der Zugriffstastentabelle Ihrer Anwendung den gleichen Ressourcenbezeichner zuordnen. Anschließend bearbeiten Sie die [Beschriftung](../windows/menu-command-properties.md) des Menübefehls so, dass sie den Namen der Zugriffstaste anzeigt.  
  
### <a name="to-associate-a-menu-command-with-an-accelerator-key"></a>So ordnen Sie einen Menübefehl einer Zugriffstaste zu  
  
1.  Wählen Sie im **Menü** -Editor den gewünschten Menübefehl aus.  
  
2.  Fügen Sie im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)der Eigenschaft **Caption** den Namen der Zugriffstaste hinzu:  
  
    -   Geben Sie im Anschluss an die Menübeschriftung die Escapesequenz für einen Tabulator (\t) ein, damit alle Zugriffstasten des Menüs links ausgerichtet sind.  
  
    -   Geben Sie den Namen der Modifizierertaste (**STRG**, **ALT**oder **UMSCHALT**) ein, gefolgt von einem Pluszeichen (**+**) und dem Namen, Buchstaben oder Symbol der zusätzlichen Taste.  
  
         Wenn Sie beispielsweise **STRG+O** zum Befehl **Öffnen** im Menü **Datei** zuordnen möchten, ändern Sie die **Beschriftung** des Menübefehls, sodass sie aussieht wie hier dargestellt:  
  
        ```  
        &Open...\tCtrl+O   
        ```  
  
         Der Menübefehl im Menü-Editor wird aktualisiert, um die neue Beschriftung so darzustellen, wie Sie sie eingeben.  
  
3.  [Erstellen Sie den Zugriffstastentabellen-Eintrag](../windows/adding-an-entry-to-an-accelerator-table.md) im **Zugriffstasten** -Editor, und weisen Sie ihm den gleichen Bezeichner wie dem Menübefehl zu. Verwenden Sie eine Tastenkombination, die Ihrer Ansicht nach leicht zu merken ist.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen von Befehlen zu einem Menü](../windows/adding-commands-to-a-menu.md)   
 [Menü-Editor](../windows/menu-editor.md)