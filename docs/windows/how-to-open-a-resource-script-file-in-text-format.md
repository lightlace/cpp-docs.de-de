---
title: 'Vorgehensweise: Öffnen eine Ressourcenskriptdatei im Textformat | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resource script files, opening in text format
- .rc files, opening in text format
- rc files, opening in text format
ms.assetid: 0bc57527-f53b-40c9-99a9-4dcbc5c9af57
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 345171742f979e488c6a4bb48cf1b57e4bb2f164
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018109"
---
# <a name="how-to-open-a-resource-script-file-in-text-format"></a>Gewusst wie: Öffnen einer Ressourcenskriptdatei im Textformat
Es gibt viele Situationen, in denen Sie die Inhalte der Ressourcenskriptdatei (.rc) Ihres Projekts anzeigen möchten, ohne dafür eine Ressource wie ein Dialogfeld im entsprechenden Ressourcen-Editor zu öffnen. Beispielsweise möchten Sie möglicherweise nach einer Zeichenfolge über alle Dialogfelder in der Ressourcendatei hinweg suchen, ohne dass Sie dafür jedes einzeln öffnen müssen.  
  
> [!NOTE]
>  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
 Sie können die Ressourcendatei einfach öffnen, im Text-Format, um globale Vorgänge, die von unterstützt alle darin enthaltenen Ressourcen anzeigen und Ausführen der [Text-Editor](http://msdn.microsoft.com/508e1f18-99d5-48ad-b5ad-d011b21c6ab1).  
  
> [!NOTE]
>  Die Ressourcen-Editoren nicht direkt RC gelesen oder `resource.h` Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei nicht mehr mit der .rc-Datei synchron ist, wird die .rc-Datei neu generiert (z. B. überschreibt der Ressourcen-Editor beim Speichern die .rc-Datei und resource.h-Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  
### <a name="to-open-a-resource-script-file-as-text"></a>So öffnen Sie eine Ressourcenskriptdatei als Text  
  
1.  Von der **Datei** Menü **öffnen**, klicken Sie dann auf **Datei.**  
  
2.  In der **geöffnete Datei** Dialogfeld navigieren Sie auf die Ressourcenskriptdatei im Textformat anzeigen möchten.  
  
3.  Markieren Sie die Datei, und klicken Sie dann den Dropdown-Pfeil auf der **öffnen** Schaltfläche (auf der rechten Seite der Schaltfläche).  
  
4.  Wählen Sie **Öffnen mit** im Dropdown-Menü.  
  
5.  In der **Öffnen mit** Dialogfeld klicken Sie auf **Quellcode-Editor (Text)**.  
  
6.  Von der **öffnen als** Dropdown-Liste **Text**.  
  
     Die Ressource wird geöffnet, der **Quellcode** Editor.  
  
 \- oder –  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste in der RC-Datei.  
  
2.  Wählen Sie im Kontextmenü den Befehl **Öffnen mit...** , und wählen Sie dann **Quellcode-Editor (Text)**.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)