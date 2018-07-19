---
title: Erstellen transparenter oder invertierter Bereiche in Gerätebildern (Bildbearbeitung für Symbole) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], screen regions
- inverse colors, device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices, transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects, transparent images
- icons [C++], screen regions
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 70fd2411eefba495478baaf5fb20fe7a27031001
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882549"
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>Erstellen transparenter oder invertierter Bereiche in Gerätebildern (Bildbearbeitung für Symbole)
In der [bildbearbeitung](../windows/image-editor-for-icons.md), das erste Symbol oder Cursor Abbild verfügt über eine transparent-Attribut. Obwohl Symbol-als auch Cursor rechteckig sind, werden viele nicht in dieser Form angezeigt, da Teile des Bilds transparent sind; das zugrunde liegende Bild auf dem Bildschirm zeigt über dem Symbol oder Cursor. Wenn Sie ein Symbol ziehen, können Teile des Bilds invertierten Farben angezeigt werden. Sie erstellen diese Auswirkungen durch Festlegen der Bildschirmfarbe und invertierte Farbe in der [Fenster "Farben"](../windows/colors-window-image-editor-for-icons.md).  
  
 Die Bildschirm- und invertierte Farben angewendet, Symbole und Cursor entweder Form und Farbe des abgeleiteten Bildes oder invertierter Bereiche bestimmt werden. Die Farben kennzeichnen Teile des Bilds, das diese Attribute besitzen. Sie können die Farben ändern, die die Attribute Bildschirmfarbe und Inverse Farbe bearbeiten darstellen. Diese Änderungen wirken sich nicht auf die Darstellung des Symbol oder Cursor in der Anwendung aus.  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-transparent-or-inverse-regions"></a>Erstellen transparenter oder invertierter Bereiche  
  
1.  In der **Farben** Fenster, klicken Sie auf die **Bildschirmfarbe** Selektor oder **Inverse Farbe** Selektor.  
  
2.  Wenden Sie den Bildschirm oder invertierte Farbe auf das Abbild mithilfe eines Tools zeichnen. Weitere Informationen zu Zeichentools finden Sie unter [mithilfe eines Tools zeichnen](using-a-drawing-tool-image-editor-for-icons.md).  
  
### <a name="to-change-the-screen-or-inverse-color"></a>So ändern Sie den Bildschirm oder Inverse Farbe  
  
1.  Wählen Sie entweder die **Bildschirmfarbe** Selektor oder **Inverse Farbe** Selektor.  
  
2.  Wählen Sie eine Farbe aus der **Farben** Palette in den **Farben** Fenster.  
  
     Die Komplementärfarbe wird automatisch für die anderen-Auswahl festgelegt.  
  
    > [!TIP]
    >  Wenn Sie die Auswahl Bildschirmfarbe oder Inverse Farbe, doppelklicken Sie auf die [benutzerdefinierte Farbauswahl (Dialogfeld)](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) angezeigt wird.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Keiner  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

