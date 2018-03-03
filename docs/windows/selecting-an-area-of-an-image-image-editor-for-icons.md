---
title: "Markieren eines Bilds (Bildbearbeitung für Symbole) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3060c47af46a39358ac2e8a7ab5b573f50867869
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>Markieren eines Bildbereichs (Bildbearbeitung für Symbole)
Sie können Auswahlwerkzeuge verwenden, um einen Bereich eines Bilds zu definieren, den Sie Ausschneiden, kopieren, löschen, ändern Sie die Größe, umkehren oder verschieben möchten. Mit der **Rechteckauswahl** Tool können Sie definieren, und wählen Sie einen rechteckigen Bereich des Bilds. Mit der **Unregelmäßige Auswahl** Tool können Sie einen Überblick über den Bereich, die Sie auswählen, für das Ausschneiden, kopieren, oder einen anderen Vorgang möchten Freihandlinie zeichnen.  
  
> [!NOTE]
>  Finden Sie unter der **Rechteckauswahl** und **Unregelmäßige Auswahl** Tools in dargestellte [Grafik-Editor-Symbolleiste](../windows/toolbar-image-editor-for-icons.md) oder Anzeigen von QuickInfos, die jede Schaltfläche auf der zugeordneten**Bildbearbeitung** Symbolleiste.  
  
 Sie können auch einen benutzerdefinierten Pinsel aus einer Auswahl erstellen. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
### <a name="to-select-an-area-of-an-image"></a>Wählen Sie einen Bereich eines Bilds  
  
1.  Auf der **Bildbearbeitung** Symbolleiste (oder aus der **Image** im Menü **Tools** Befehl), klicken Sie auf die gewünschte Auswahltool.  
  
2.  Verschieben Sie die Einfügemarke an einer Ecke Randes des Bildbereichs, die Sie auswählen möchten. Fadenkreuz angezeigt werden, wenn die Einfügemarke befindet sich auf das Bild.  
  
3.  Ziehen Sie die Einfügemarke in die entgegengesetzte Ecke des Bereichs, den Sie auswählen möchten. Ein Rechteck zeigt an, welche Pixel ausgewählt werden. Alle Pixel innerhalb des Rechtecks, einschließlich der unter dem Rechteck sind in der Auswahl enthalten.  
  
4.  Lassen Sie die Maustaste los. Der Markierungsrahmen umschließt den ausgewählten Bereich.  
  
### <a name="to-select-an-entire-image"></a>Auswählen ein ganzen Bildes  
  
1.  Klicken Sie auf das Bild außerhalb der aktuellen Auswahl. Die Auswahlrahmen ändert den Fokus, und das gesamte Bild erneut umfasst.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

