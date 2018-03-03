---
title: Versionsinfo-Editor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor, about Version Information editor
- editors, Version Information
- resource editors, Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c221120bf7170025506fe49fe2ab6419ce66044
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="version-information-editor"></a>Versionsinfo-Editor
Versionsinformationen bestehen aus einer Firmen- und einer Produkt-ID, einer Produktseriennummer und Copyright- und Markenbestimmungen. Mit dem Versionsinformations-Editor können Sie diese Daten, die in der Versionsinformationsressource gespeichert sind, erstellen und warten. Die Versionsinformationsressource ist für eine Anwendung nicht erforderlich, sie stellt aber einen sinnvollen Ort dar, alle Informationen zusammenzuführen, die zur Identifizierung der Anwendung dienen. Versionsinformationen werden auch von Setup-APIs verwendet.  
  
 Eine Versionsinformationsressource weist einen oberen Block und mindestens einen unteren Block auf: ein einzelner Block mit unveränderlichen Informationen oben und mindestens ein weiterer Versionsinformationsblock darunter (für andere Sprachen und/oder Zeichensätze). Der obere Block weist sowohl editierbare Zahlenfelder als auch auswählbare Dropdownlisten auf. Die unteren Blöcke weisen nur editierbare Textfelder auf.  
  
> [!NOTE]
>  Der Windows-Standard sieht nur eine Versionsressource mit dem Namen VS_VERSION_INFO vor.  
  
 Mithilfe des Versionsinformations-Editors können Sie dies ausführen:  
  
-   [Bearbeiten einer Zeichenfolge in einer Versionsinformationsressource](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [Hinzufügen von Versionsinformationen für eine andere Sprache (neuer Versionsinformationsblock)](../windows/adding-version-information-for-another-language.md)  
  
-   [Löschen eines Versionsinformationsblocks](../windows/deleting-a-version-information-block.md)  
  
-   [Zugreifen auf Versionsinformationen aus dem Programm](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  Indem Sie im Versionsinformations-Editor auf die rechte Maustaste klicken, können Sie in vielen Situationen ein Kontextmenü aufrufen, in dem ressourcenspezifische Befehle enthalten sind. Wenn Sie z. B. klicken, während Sie auf einen Blockheadereintrag zeigen, zeigt das Kontextmenü die Befehle „Neue Versionsblockinformationen“ und „Versionsblockinformationen löschen“ an.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcen-Editoren](../windows/resource-editors.md)   
 [Menüs und weitere Ressourcen](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

