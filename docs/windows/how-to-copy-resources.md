---
title: 'Vorgehensweise: Kopieren von Ressourcen | Microsoft Docs'
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
ms.openlocfilehash: 4b173be24e9f177a3156f740fcb07240c30fec75
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33879847"
---
# <a name="how-to-copy-resources"></a>Gewusst wie: Kopieren von Ressourcen
Sie können Ressourcen in eine andere aus einer Datei kopieren, ohne sie zu ändern, oder Sie können [Ändern von Sprache oder Bedingung einer Ressource während des Kopiervorgangs](../windows/how-to-change-the-language-or-condition-of-a-resource-while-copying.md).  
  
 Sie können problemlos Ressourcen aus einer vorhandenen Ressource oder eine ausführbare Datei in der aktuelle(n) Ressourcendatei kopieren. Zu diesem Zweck öffnen Sie beide Dateien, die zur gleichen Zeit Ressourcen enthalten Sie und ziehen Sie Elemente aus einer Datei in eine andere oder kopieren und fügen Sie zwischen den beiden Dateien. Diese Methode funktioniert für Ressourcenskriptdateien (RC) und Ressourcendateien für die Vorlage (RCT) als auch ausführbare Dateien (.exe).  
  
> [!NOTE]
>  Visual C++ enthält Beispiel-Ressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können. Weitere Informationen finden Sie unter [CLIPART: Allgemeine Ressourcen](http://msdn.microsoft.com/en-us/9bac2891-b6b3-49ec-a287-cec850c707e0).  
  
 Sie können mithilfe der Drag-and-Drop-Methode RC-Dateien, die geöffnet sind [außerhalb des Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>Kopieren von Ressourcen zwischen den Dateien, die mithilfe der Drag-and-Drop-Methode  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen in einer RC-Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Öffnen Sie beispielsweise Source1.rc und Source2.rc.  
  
2.  Klicken Sie in der ersten RC-Datei auf die Ressource, die Sie kopieren möchten. Beispielsweise Source1.rc, klicken Sie auf IDD_DIALOG1.  
  
3.  Halten Sie die STRG-Taste gedrückt, und ziehen Sie die Ressource in die zweite RC-Datei. Ziehen Sie z. B. IDD_DIALOG1 aus Source1.rc in Source2.rc.  
  
    > [!NOTE]
    >  Ziehen die Ressource, ohne Sie die STRG-Taste gedrückt halten, verschiebt sie kopieren, anstatt die Ressource.  
  
### <a name="to-copy-resources-using-copy-and-paste"></a>Kopieren von Ressourcen mithilfe von kopieren und einfügen  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen in einer RC-Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Beispielsweise Source1.rc und Source2.rc.  
  
2.  Maustaste Sie eine Ressource in der Quelldatei, von dem Sie eine Ressource (z. B. Source1.rc) kopieren möchten, und wählen Sie **Kopie** aus dem Kontextmenü.  
  
3.  Mit der rechten Maustaste in der Ressourcendatei, in der Sie die Ressource (z. B. Source2.rc) einfügen möchten. Wählen Sie **einfügen** aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Sie können nicht ziehen und löschen, kopieren, Ausschneiden oder fügen Sie zwischen Ressourcendateien im Projekt (Ressourcenansicht) und eigenständige RC-Dateien (die im Dokumentfenster geöffnet). Sie können in früheren Versionen des Produkts erfolgen.  
  
    > [!NOTE]
    >  Um Konflikte mit Symbolnamen oder Werten in die vorhandene Datei zu vermeiden, können Visual C++ Symbolwert der übertragenen Ressource oder Symbolnamens und-Werts ändern, wenn Sie an die neue Datei zu kopieren.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)