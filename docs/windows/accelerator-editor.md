---
title: Zugriffstasten-Editor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [Visual Studio], accelerator key
- accelerator keys
- resource editors, Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e078dbd3dc8d462ef4bca6e6f1056afb9ce8724c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="accelerator-editor"></a>Zugriffstasten-Editor
Eine Zugriffstastentabelle ist eine Windows-Ressource, die eine Liste mit Zugriffstasten (auch als Tastenkombinationen bezeichnet) und die Befehlsbezeichner enthält, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.  
  
 Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.  
  
 Sie können die [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925) verwenden, um Zugriffstastenbefehle mit Code zu verknüpfen.  
  
 Im Zugriffstasten-Editor ist Folgendes möglich:  
  
-   [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)  
  
-   [Zuordnen einer Zugriffstaste zu einem Menüeintrag](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)  
  
-   [Verwenden vordefinierter Zugriffstasten](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  Im Zugriffstasten-Editor können Sie mit der rechten Maustaste klicken, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.  
  
    > [!NOTE]
    >  Windows lässt die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editor](../windows/resource-editors.md)

