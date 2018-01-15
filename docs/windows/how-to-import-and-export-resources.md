---
title: 'Vorgehensweise: Importieren und Exportieren von Ressourcen | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs: C++
helpviewer_keywords:
- resources [Visual Studio], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [Visual Studio], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 3c9329dc-dcb8-4edd-a600-78e3e572bd89
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a01269928d0e5b52cca6e2301ad681db61289f80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-import-and-export-resources"></a>Gewusst wie: Importieren und Exportieren von Ressourcen
Sie können grafische Ressourcen (Bitmaps, Symbole, Cursor und Symbolleisten), HTML-Dateien und benutzerdefinierte Ressourcen für die Verwendung in Visual C++ importieren. Die können dieselben Dateitypen aus einem Visual C++-Projekt exportieren, um Dateien zu trennen, die außerhalb der Entwicklungsumgebung verwendet werden können.  
  
> [!NOTE]
>  Ressourcentypen wie Zugriffstasten, Dialogfelder und Zeichenfolgentabellen können weder im- noch exportiert werden, da sie keine eigenständigen Dateitypen sind.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>So importieren Sie eine einzelne Ressource in Ihre aktuelle Ressourcendatei  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste des Knotens für die Ressourcenskriptdatei (* .rc) Datei, die Sie eine Ressource hinzufügen möchten.  
  
2.  Klicken Sie auf **Import** im Kontextmenü.  
  
3.  Suchen Sie nach dem Dateinamen der Bitmap- (.bmp), Symbol- (.ico), Cursor- (.cur), HTML- (.html) oder einer anderen zu importierenden Datei, und wählen Sie ihn aus.  
  
4.  Klicken Sie auf **OK** die Ressource hinzugefügt, um die ausgewählte Datei in **Ressource** anzeigen.  
  
    > [!NOTE]
    >  Der Importvorgang funktioniert auf die gleiche Weise, und zwar unabhängig davon, welchen bestimmten Ressourcentyp Sie ausgewählt haben. Die importierte Ressource wird automatisch zum richtigen Knoten für diesen Ressourcentyp hinzugefügt.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>So exportieren Sie Bitmaps, Symbole oder Cursor als eine getrennte Datei (für die Verwendung außerhalb von Visual C++)  
  
1.  In **Ressource** zeigen Sie an der rechten Maustaste auf die Ressource, die Sie exportieren möchten.  
  
2.  Klicken Sie auf **exportieren** im Kontextmenü.  
  
3.  In der **Ressource exportieren** Dialogfeld Feld, nehmen Sie den aktuellen Dateinamen an oder geben Sie einen neuen ein.  
  
4.  Navigieren Sie zu dem Ordner, in dem Sie soll zum Speichern der Datei, und klicken Sie auf **exportieren**.  
  

  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)