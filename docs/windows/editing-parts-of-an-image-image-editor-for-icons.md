---
title: "Bearbeiten von Bestandteilen eines Bilds (Bildbearbeitung für Symbole) | Microsoft Docs"
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
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: acd4859bf7c80cf2bbe6cd2d86c39d0fc596351d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Bearbeiten von Bestandteilen eines Bilds (Bildbearbeitung für Symbole)
Können Sie standard Bearbeitungsvorgänge ausführen – Ausschneiden, kopieren, löschen und Verschieben von – auf einer [Auswahl](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), ob die Auswahl auf das gesamte Bild oder bilden nur einen Teil davon ist. Da die Grafik-Editor die Windows-Zwischenablage verwendet wird, können Sie Bilder zwischen dem Bild-Editor und anderen Anwendungen für Windows übertragen.  
  
 Darüber hinaus können Sie die Auswahl ändern, ob es sich um das gesamte Bild oder nur ein Teil enthält.  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>So schneiden Sie die aktuelle Auswahl und verschieben Sie sie in die Zwischenablage  
  
1.  Klicken Sie auf **Ausschneiden** auf die **bearbeiten** Menü.  
  
### <a name="to-copy-the-selection"></a>So kopieren Sie die Auswahl  
  
1.  Positionieren Sie den Zeiger innerhalb der Auswahlrahmen oder eine beliebige Stelle auf, mit Ausnahme der Ziehpunkte.  
  
2.  Halten Sie die **STRG** Schlüssel, wie Sie die Auswahl in einem neuen Speicherort ziehen. Der Bereich der ursprünglichen Auswahl ist unverändert.  
  
3.  Um die Auswahl in das Image auf seinem aktuellen Speicherort zu kopieren, klicken Sie außerhalb des Cursors Auswahl.  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Der Inhalt der Zwischenablage in ein Bild einfügen  
  
1.  Aus der **bearbeiten** Menü wählen **einfügen**.  
  
     Der Inhalt der Zwischenablage, von der Markierungsrahmen umgeben werden in der oberen linken Ecke des Bereichs angezeigt.  
  
2.  Positionieren Sie den Zeiger innerhalb der Markierungsrahmen umgeben, und ziehen Sie das Bild an die gewünschte Position auf dem Bild.  
  
3.  Um das Bild an seiner neuen Position zu verankern, klicken Sie auf außerhalb der Markierungsrahmen umgeben.  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Die aktuelle Auswahl zu löschen, ohne dass diese in die Zwischenablage verschoben werden  
  
1.  Aus der **bearbeiten** Menü wählen **löschen**.  
  
     Der ursprüngliche Bereich der Auswahl ist mit der aktuellen Hintergrundfarbe gefüllt.  
  
    > [!NOTE]
    >  Sie können Zugriff auf die Ausschneide-, Kopier-, Einfüge- und Löschbefehlen, indem Sie mit der mit der rechten Maustaste in das Fenster "Ressourcenansicht".  
  
### <a name="to-move-the-selection"></a>So verschieben Sie die Auswahl  
  
1.  Positionieren Sie den Zeiger innerhalb der Auswahlrahmen oder eine beliebige Stelle auf, mit Ausnahme der Ziehpunkte.  
  
2.  Ziehen Sie die Auswahl an die neue Position.  
  
3.  Um die Auswahl in der Abbildung an seiner neuen Position zu verankern, klicken Sie außerhalb der Markierungsrahmen umgeben.  
  
 Weitere Informationen zum Zeichnen mit einer Auswahl finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

