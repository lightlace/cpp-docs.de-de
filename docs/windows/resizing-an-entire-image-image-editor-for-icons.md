---
title: Größenänderung eines ganzen Bilds (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- size [C++], images
- images [C++], resizing
- resizing images
ms.assetid: 10782937-7eb4-4340-bdec-618ee7d7904b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f9104feac603819b9420d315e619182722c87474
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606217"
---
# <a name="resizing-an-entire-image-image-editor-for-icons"></a>Größenänderung eines ganzen Bilds (Bildbearbeitung für Symbole)
### <a name="to-resize-an-entire-image-using-the-properties-window"></a>Zum Ändern der Größe eines ganzen Bilds mithilfe des Eigenschaftenfensters  
  
1.  Öffnen Sie das Bild, dessen Eigenschaften Sie ändern möchten.  
  
2.  In der **Breite** und **Höhe** Dialogfelder in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie die Dimensionen, die Sie möchten.  
  
     Wenn Sie die Größe des Bilds zunehmen, der Bild-Editor erweitert das Bild an der rechten Seite nach unten, oder beides und füllt den neuen Bereich in der aktuellen Hintergrundfarbe. Das Bild wird nicht gestreckt.  
  
     Wenn Sie die Größe des Bilds verringert werden, schneidet die Bild-Editor das Abbild auf den rechten oder unteren Rand oder beides.  
  
    > [!NOTE]
    >  Sie können Eigenschaften für Höhe und Breite verwenden, nur das gesamte Bild nicht zum Ändern der Größe eines markierten Größe zu ändern.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Größenänderungen bei Bildern](../windows/resizing-an-image-image-editor-for-icons.md)