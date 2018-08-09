---
title: 'Vorgehensweise: Importieren und Exportieren von Ressourcen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vs.resvw.resource.importing
- vc.resvw.resource.importing
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e912e2aaae53fa0c7f9e506ce70128238bf15a78
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018415"
---
# <a name="how-to-import-and-export-resources"></a>Gewusst wie: Importieren und Exportieren von Ressourcen
Sie können grafische Ressourcen (Bitmaps, Symbole, Cursor und Symbolleisten), HTML-Dateien und benutzerdefinierte Ressourcen für die Verwendung in Visual C++ importieren. Die können dieselben Dateitypen aus einem Visual C++-Projekt exportieren, um Dateien zu trennen, die außerhalb der Entwicklungsumgebung verwendet werden können.  
  
> [!NOTE]
>  Ressourcentypen wie Zugriffstasten, Dialogfelder und Zeichenfolgentabellen können weder im- noch exportiert werden, da sie keine eigenständigen Dateitypen sind.  
  
### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>So importieren Sie eine einzelne Ressource in Ihre aktuelle Ressourcendatei  
  
1.  In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste des Knotens für das Ressourcenskript (* .rc)-Datei zu dem beim Hinzufügen einer Ressource werden sollen.  
  
2.  Klicken Sie auf **Import** im Kontextmenü auf.  
  
3.  Suchen Sie nach dem Dateinamen der Bitmap- (.bmp), Symbol- (.ico), Cursor- (.cur), HTML- (.html) oder einer anderen zu importierenden Datei, und wählen Sie ihn aus.  
  
4.  Klicken Sie auf **OK** zum Hinzufügen der Ressource zur ausgewählten Datei in **Ressource** anzeigen.  
  
    > [!NOTE]
    >  Der Importvorgang funktioniert auf die gleiche Weise, und zwar unabhängig davon, welchen bestimmten Ressourcentyp Sie ausgewählt haben. Die importierte Ressource wird automatisch zum richtigen Knoten für diesen Ressourcentyp hinzugefügt.  
  
### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>So exportieren Sie Bitmaps, Symbole oder Cursor als eine getrennte Datei (für die Verwendung außerhalb von Visual C++)  
  
1.  In **Ressource** Anzeigen der rechten Maustaste auf die Ressource, die Sie exportieren möchten.  
  
2.  Klicken Sie auf **exportieren** im Kontextmenü auf.  
  
3.  In der **Ressource exportieren** Dialogfeld Feld, oder übernehmen Sie den aktuellen Dateinamen geben Sie eine neue Ressourcengruppe.  
  
4.  Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern, und klicken Sie auf möchten **exportieren**.  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)