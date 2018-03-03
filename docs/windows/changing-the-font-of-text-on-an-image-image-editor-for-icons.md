---
title: "Ändern der Schriftart von Text in einem Bild (Bildbearbeitung für Symbole) | Microsoft Docs"
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
- fonts, changing on an image
ms.assetid: b8849d40-d401-4e06-808f-e615cb2bee3b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07dc7d7fd74ad9d4b0229ffef7cf4e96a4ea44b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="changing-the-font-of-text-on-an-image-image-editor-for-icons"></a>Ändern der Schriftart von Text in einem Bild (Bildbearbeitung für Symbole)
Das folgende Verfahren ist ein Beispiel:  
  
-   Fügen Sie Text für ein Symbol in einer Windows-Anwendung hinzu.  
  
-   Bearbeiten der Schriftart von text  
  
### <a name="to-change-the-font-of-text-on-an-image"></a>So ändern Sie die Schriftart des Texts in einem Bild  
  
1.  Erstellen Sie eine C++-Windows Forms-Anwendung. Weitere Informationen finden Sie unter [Erstellen eines Windows-Anwendungsprojekts](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa). Die [Vorlage für Windows Forms-Anwendung](http://msdn.microsoft.com/en-us/1babdebf-ab3f-4a64-a608-98499a5b9cea) Datei app.ico zu Ihrem Projekt standardmäßig hinzugefügt.  
  
2.  Doppelklicken Sie im Projektmappen-Explorer auf die Datei app.ico. Die [Bildbearbeitung](../windows/image-editor-for-icons.md) wird geöffnet.  
  
3.  Aus der **Image** klicken Sie im Menü **Tools** und wählen Sie dann **Texttool**. Die [Text-Dialogfeld "Texttool"](../windows/text-tool-dialog-box-image-editor-for-icons.md) wird angezeigt.  
  
4.  Geben Sie im Dialogfeld Text-Tool `C++` in den leeren Textbereich. Dieser Text wird in einem in der Größe veränderbaren befindet sich in der oberen linken Ecke von app.ico, in dem Bild-Editor angezeigt.  
  
5.  Die Grafik-Editor ziehen Sie das in der Größe veränderbaren Feld in die Mitte der app.ico, um die Lesbarkeit von Text zu verbessern.  
  
6.  Klicken Sie im Dialogfeld Text-Tool auf dem **Schriftart** Schaltfläche. Die [Text Tool Schriftart (Dialogfeld)](../windows/text-tool-font-dialog-box-image-editor-for-icons.md) wird angezeigt.  
  
7.  Wählen Sie im Dialogfeld Schriftart für Texttool **Times New Roman** aus der Liste der verfügbaren Schriftarten, die in aufgeführt sind die **Schriftart** Listenfeld.  
  
8.  Wählen Sie **fett** aus der Liste der verfügbaren Schriftschnitte aufgeführt, die der **Schriftschnitt** Listenfeld.  
  
9. Wählen Sie **10** aus der Liste der verfügbaren Punktgrößen aufgeführt, die der **Größe** Listenfeld.  
  
10. Klicken Sie auf die **OK** Schaltfläche. Das Dialogfeld Schriftart von Text-Tool wird geschlossen, und die neue Schriftart-Einstellung wird in den Text angewendet.  
  
11. Klicken Sie auf die **schließen** Schaltfläche im Dialogfeld Text-Tool. In der Größe veränderbaren Feld um den Text wird nicht mehr aus dem Bild-Editor angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Symbolleiste](../windows/toolbar-image-editor-for-icons.md)

