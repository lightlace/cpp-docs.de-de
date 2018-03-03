---
title: "Größe von individuellen Steuerelementen | Microsoft Docs"
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
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b019cd2bbf68a4321bafd6dd960ffbcdba2dddf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sizing-individual-controls"></a>Festlegen der Größe von individuellen Steuerelementen
Verwenden Sie den Ziehpunkt, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert er Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Aktive Ziehpunkte sind gefüllt. Wenn Sie ein Ziehpunkt leer ist, kann nicht entlang dieser Achse Größe des Steuerelements geändert werden.  
  
 Sie können auch die Größe eines Steuerelements ändern, indem das Steuerelement in den Handbüchern oder die Ränder andocken, oder durch Verschieben einer "angedockt" Handbuch Weg von einem anderen und Steuerelement.  
  
### <a name="to-size-a-control"></a>Größe eines Steuerelements  
  
1.  Wählen Sie das Steuerelement.  
  
2.  Ziehen Sie die Ziehpunkte zum Ändern der Größe des Steuerelements ein:  
  
    -   Ziehpunkte am oberen und Seiten werden die horizontale oder vertikale Größe ändern.  
  
    -   Ziehpunkte an den Ecken werden horizontale und vertikale Größe ändern.  
  
    > [!TIP]
    >  Sie können das Steuerelement um eine Dialogeinheit (DLU) zu einem Zeitpunkt ändern, indem Sie die UMSCHALTTASTE gedrückt halten und die rechts und nach-unten-Tasten verwenden.  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Ein Steuerelement, um die Textgröße darin automatisch angepasst  
  
1.  Wählen Sie **Größe an Inhalt anpassen** aus der **Format** Menü.  
  
 \- oder –  
  
-   Mit der rechten Maustaste in des Steuerelements, und wählen Sie **Größe an Inhalt anpassen** aus dem Kontextmenü.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

