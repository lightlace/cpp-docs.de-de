---
title: Zugriffstasten-Editor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: feece642928db70a2b78dd3a4117b695b19f4af9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466071"
---
# <a name="accelerator-editor"></a>Zugriffstasten-Editor
Eine Zugriffstastentabelle ist eine Windows-Ressource, die eine Liste mit Zugriffstasten (auch als Tastenkombinationen bezeichnet) und die Befehlsbezeichner enthält, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.  
  
 Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.  
  
 Sie können [Klassenansicht](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) um Zugriffstastenbefehle mit Code zu verknüpfen.  
  
 Im Zugriffstasten-Editor ist Folgendes möglich:  
  
-   [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)  
  
-   [Zuordnen einer Zugriffstaste zu einem Menüeintrag](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)  
  
-   [Verwenden vordefinierter Zugriffstasten](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  Im Zugriffstasten-Editor können Sie mit der rechten Maustaste klicken, um ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.  
  
    > [!NOTE]
    >  Windows lässt die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editor](../windows/resource-editors.md)