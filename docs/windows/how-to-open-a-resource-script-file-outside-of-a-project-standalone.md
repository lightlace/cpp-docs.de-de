---
title: "Vorgehensweise: Öffnen eine Ressourcenskriptdatei außerhalb eines Projekts (eigenständig) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.resource
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- rc files, viewing resources
- .rc files, viewing resources
- resource script files, viewing resources
ms.assetid: bc350c60-178d-4c5d-9a7e-6576b0c936e4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2dd3bb3996fca1fd2c73ff98e7f391d27911ad15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-open-a-resource-script-file-outside-of-a-project-standalone"></a>Gewusst wie: Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)
Sie können Ressourcen in einer RC-Datei anzeigen, ohne dass ein Projekt geöffnet sein muss. Die RC-Datei wird geöffnet, in einem Dokumentfenster geöffnet, anstatt in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster (wie dies der Fall ist, wenn die Datei innerhalb eines Projekts geöffnet ist).  
  
> [!NOTE]
>  Dies ist eine wichtige Unterscheidung, da einige Befehle nur verfügbar sind, wenn die Datei eigenständig (außerhalb eines Projekts) geöffnet wird. Angenommen, Sie können nur Speichern einer Datei in ein anderes Format oder als einen anderen Dateinamen an, wenn die Datei außerhalb eines Projekts geöffnet wird (die **speichern unter** Befehl ist nicht verfügbar, wenn eine Datei innerhalb eines Projekts geöffnet ist).  
  
### <a name="to-open-an-rc-file-outside-a-project"></a>Öffnen einer RC-Datei außerhalb eines Projekts  
  
1.  Aus der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.  
  
2.  In der **Dateiöffnungsmodus** Dialogfeld Feld, navigieren Sie zu der Ressourcenskriptdatei, die Sie verwenden möchten, anzuzeigen, markieren Sie die Datei, und klicken Sie auf **öffnen**.  
  
    > [!NOTE]
    >  Wenn Sie das Projekt zuerst öffnen (**Datei**, **öffnen**, **Projekt**), einige Befehle werden nicht zur Verfügung. Eine Datei „eigenständig“ zu öffnen, bedeutet, sie zu öffnen, ohne erst das Projekt zu laden.  
  
 Öffnen und Anzeigen der Ressourcendatei im Textformat, finden Sie unter [Bearbeiten einer Ressourcenskriptdatei (.rc) Datei](../windows/how-to-open-a-resource-script-file-in-text-format.md).  
  
#### <a name="to-open-multiple-rc-files-outside-a-project"></a>Öffnen mehrerer RC-Dateien außerhalb eines Projekts  
  
1.  Öffnen Sie beide Ressourcendateien eigenständig. Öffnen Sie beispielsweise Source1.rc und Source2.rc.  
  
    1.  Aus der **Datei** Menü wählen **öffnen**, klicken Sie dann auf **Datei**.  
  
    2.  In der **Datei öffnen** Dialogfeld Feld, navigieren Sie zu den ersten Ressourcenskriptdatei, die Sie verwenden möchten, öffnen (Source1.rc), markieren Sie die Datei, und klicken Sie auf **öffnen**.  
  
    3.  Wiederholen Sie den vorherigen Schritt, um die zweite RC-Datei (Source2.rc) zu öffnen.  
  
         Die RC-Dateien sind nun in separaten Dokumentfenstern geöffnet.  
  
2.  Wenn beide RC-Dateien geöffnet sind, ordnen Sie die Fenster so an, dass sie gleichzeitig angezeigt werden:  
  
    -   Aus der **Fenster** Menü wählen **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe**.  
  
         \- oder –  
  
    -   Maustaste auf eine der RC-Dateien, und wählen Sie **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe** aus dem Kontextmenü.  
  
> [!NOTE]
>  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  

  
### <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)