---
title: Markieren eines Bildbereichs (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5ed8669a22be7e1a2b696ca9373c30e71f17c191
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012682"
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>Markieren eines Bildbereichs (Bildbearbeitung für Symbole)
Sie können Tools für die Auswahl verwenden, um einen Bereich eines Bildes zu definieren, die Sie Ausschneiden, kopieren, löschen, ändern Sie die Größe, umkehren, oder verschieben möchten. Mit der **Rechteckauswahl** Tool können Sie definieren, und wählen Sie einen rechteckigen Bereich des Bilds. Mit der **Unregelmäßige Auswahl** Tool können Sie einen Freihand über den Bereich, die Sie auswählen, für das Ausschneiden, kopieren oder andere Vorgänge möchten zeichnen.  
  
> [!NOTE]
>  Finden Sie unter der **Rechteckauswahl** und **Unregelmäßige Auswahl** Tools in dargestellte [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md) oder die QuickInfos jeder Schaltfläche auf der **Bildbearbeitung** Symbolleiste.  
  
 Sie können auch einen benutzerdefinierten Pinsel aus einer Auswahl erstellen. Weitere Informationen finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
### <a name="to-select-an-area-of-an-image"></a>Um einen Bereich eines Bilds  
  
1.  Auf der **Bild-Editor** Symbolleiste (oder von der **Image** Menü **Tools** Befehl), klicken Sie auf das Auswahlwerkzeug werden sollen.  
  
2.  Verschieben Sie die Einfügemarke an einer Ecke des Bereichs, Image, das Sie auswählen möchten. Fadenkreuz wird angezeigt, wenn die Einfügemarke auf das Bild ist.  
  
3.  Ziehen Sie die Einfügemarke in die entgegengesetzte Ecke des Bereichs, die Sie auswählen möchten. Ein Rechteck zeigt an, welche Pixel ausgewählt werden. Alle Pixel innerhalb des Rechtecks, u. a. die das Rechteck, sind in der Auswahl enthalten.  
  
4.  Lassen Sie die Maustaste los. Der Markierungsrahmen umschließt den ausgewählten Bereich.  
  
### <a name="to-select-an-entire-image"></a>Auswählen ein ganzen Bildes  
  
1.  Klicken Sie auf das Bild außerhalb der aktuellen Auswahl. Die Markierungsrahmen umgeben ändert den Fokus, und das gesamte Bild wieder umfasst.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)