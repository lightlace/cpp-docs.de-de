---
title: Erstellen von benutzerdefinierten Pinseln (Bildbearbeitung für Symbole) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a879850c00957568065150b6c6fc1c801c049fa2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873146"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Erstellen von benutzerdefinierten Pinseln (Bildbearbeitung für Symbole)
Benutzerdefinierte Pinsel ist eine rechteckige Teil eines Bildes, das Sie übernehmen, und wie eine vorgefertigte Pinsel für den Grafik-Editor verwenden. Alle Vorgänge auf einer Auswahl von ausgeführt werden können, können Sie für einen benutzerdefinierten Pinsel ebenfalls ausführen.  
  
### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>So erstellen Sie einen benutzerdefinierten Pinsel aus einem Teil eines Bildes  
  
1.  [Wählen Sie den Teil des Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) , die für den Pinsel verwendet werden sollen.  
  
2.  Mit der **UMSCHALT** nach-unten-Taste, klicken Sie in der Auswahl auf, und ziehen Sie es über das Bild.  
  
     \- oder –  
  
3.  Aus der **Image** Menü wählen **Auswahl als Pinsel verwenden**.  
  
     Ihre Auswahl wird eine benutzerdefinierte Pinsel, der die Farben in der Auswahl auf das Bild verteilt. Kopien der Auswahl befinden sich entlang des Pfads ziehen. Sie ziehen, desto langsamer, die mehrere Kopien erfolgen.  
  
     **Hinweis** auf die **verwenden eine Markierung als Pinsel** ohne Sie zuerst einen Teil des Bilds auswählen, wird das gesamte Bild als Pinsel verwendet. Das Ergebnis der Verwendung von benutzerdefinierten Pinseln hängt außerdem, ob Sie ausgewählt haben eine [undurchsichtig oder Transparent im Hintergrund](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
 Pixel in einem benutzerdefinierten Pinsel, die mit die aktuellen Hintergrundfarbe übereinstimmen, sind normalerweise transparent: sie nicht über das vorhandene Bild gezeichnet. Sie können dieses Verhalten ändern, sodass Hintergrundfarbe Pixel über das vorhandene Bild gezeichnet.  
  
 Den benutzerdefinierte Pinsel wie einen Zeitstempel oder eine Schablone können Sie um eine Vielzahl von Spezialeffekte zu erstellen.  
  
#### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Zum Zeichnen von benutzerdefinierten Pinselformen in die Farbe des Hintergrunds  
  
1.  [Wählen Sie einen Hintergrund undurchsichtig oder transparenten](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).  
  
2.  [Legen Sie die Farbe des Hintergrunds](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) , in dem Sie die gewünschte Farbe gezeichnet werden soll.  
  
3.  Positionieren Sie den benutzerdefinierten Pinsel, in dem gezeichnet werden soll.  
  
4.  Klicken Sie auf die rechte Maustaste gedrückt. Nicht transparente Bereiche von benutzerdefinierten Pinseln werden in der Hintergrundfarbe gezeichnet.  
  
#### <a name="to-double-or-halve-the-custom-brush-size"></a>Doppelklicken oder die benutzerdefinierte Pinselgröße halbiert  
  
1.  Drücken Sie die **Pluszeichen** (**+**)-Taste, um die Pinselgröße doppelklicken oder die **Minuszeichen (-)** (**-**)-Taste, um es halbiert .  
  
#### <a name="to-cancel-the-custom-brush"></a>Abbrechen von benutzerdefinierten Pinseln  
  
1.  Drücken Sie **ESC** , oder wählen Sie ein anderes Zeichenblattes Tool.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)

