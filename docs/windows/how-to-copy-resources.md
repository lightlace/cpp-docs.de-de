---
title: 'Vorgehensweise: Kopieren von Ressourcen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], moving between files
- resources [Visual Studio], copying
- resource files, copying or moving resources between
- resource files, tiling
- .rc files, copying resources between
- rc files, copying resources between
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f29a115d20eca90b66a876bf1b5070052d90008d
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570684"
---
# <a name="how-to-copy-resources"></a>Gewusst wie: Kopieren von Ressourcen
Sie können Ressourcen in eine andere aus einer Datei kopieren, ohne sie zu ändern, oder Sie können [Ändern von Sprache oder Bedingung einer Ressource während des Kopiervorgangs](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Sie können Ressourcen problemlos aus einer vorhandenen Ressource oder die ausführbare Datei in Ihre aktuelle Ressourcendatei kopieren. Zu diesem Zweck öffnen Sie beide Dateien, die mit Ressourcen zur gleichen Zeit Sie und ziehen Sie Elemente aus einer Datei in eine andere oder kopieren und fügen Sie zwischen den beiden Dateien. Diese Methode funktioniert für Ressourcenskriptdateien (RC) und Ressourcendateien für die Vorlage (.rct) sowie für ausführbare Dateien (.exe).  
  
> [!NOTE]
>  Visual C++ enthält Beispiel-Ressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können. Weitere Informationen finden Sie unter [CLIPART: Allgemeine Ressourcen](http://msdn.microsoft.com/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Sie können die Drag & Drop-Methode verwenden, RC-Dateien, die geöffnet sind [außerhalb des Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>So kopieren Sie Ressourcen zwischen den Dateien, die mithilfe der Drag & Drop-Methode  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [eine Ressourcenskriptdatei Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Öffnen Sie beispielsweise Source1.rc und Source2.rc.  
  
2.  Klicken Sie in der ersten RC-Datei auf die Ressource, die Sie kopieren möchten. Klicken Sie im Source1.rc, z. B. auf **IDD_DIALOG1**.  
  
3.  Halten Sie die STRG-Taste, und ziehen Sie die Ressource in der zweiten RC-Datei. Ziehen Sie z. B. **IDD_DIALOG1** aus Source1.rc in Source2.rc.  
  
    > [!NOTE]
    >  Ziehen die Ressource, ohne dabei die STRG-Taste gedrückt, verschiebt die Ressource, statt es zu kopieren.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>Zum Kopieren von Ressourcen mithilfe von kopieren und einfügen  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [eine Ressourcenskriptdatei Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Beispielsweise Source1.rc und Source2.rc.  
  
2.  Maustaste auf eine Ressource, in der Quelldatei, die von dem Sie eine Ressource (beispielsweise Source1.rc) kopieren möchten, und wählen **Kopie** aus dem Kontextmenü.  
  
3.  Mit der rechten Maustaste in der Ressourcendatei, die in der Sie die Ressource (z. B. Source2.rc) einfügen möchten. Wählen Sie **einfügen** aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Ziehen kann nicht und ablegen, kopieren, Ausschneiden oder fügen Sie zwischen Ressourcendateien im Projekt (Ressourcenansicht) und eigenständige RC-Dateien (die im Dokumentfenster geöffnet). In früheren Versionen des Produkts können Sie dazu.  
  
    > [!NOTE]
    >  Um Konflikte mit Symbolnamen oder Werten in die vorhandene Datei zu vermeiden, kann Visual C++ Symbolwert der übertragenen Ressource oder Symbolnamens und-Werts ändern, wenn Sie ihn in die neue Datei kopieren.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)