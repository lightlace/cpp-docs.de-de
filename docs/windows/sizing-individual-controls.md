---
title: Größe der einzelnen Steuerelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Size to Content command
- size, controls
- text, autosizing controls to fit text
- controls [C++], sizing
ms.assetid: 14ccba02-7171-463a-a121-7018cf1e2e5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 20dc5eb7af4195c9861d09761da245cdd5d3217d
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652213"
---
# <a name="sizing-individual-controls"></a>Festlegen der Größe von individuellen Steuerelementen
Verwenden Sie die Ziehpunkte, um die Größe eines Steuerelements. Wenn der Zeiger an einem Ziehpunkt befindet, ändert es Form an, dass die Anweisungen in denen Größe des Steuerelements geändert werden kann. Es sind aktive Ziehpunkte gefüllt. Wenn ein Ziehpunkt leerer ist, kann nicht das Steuerelement entlang dieser Achse Größe geändert werden.  
  
 Sie können auch die Größe eines Steuerelements ändern, durch das das Steuerelement an Führungslinien oder Rand andocken, oder durch das Verschieben einer Kontrolle und Anleitung von einem anderen angedockt.  
  
### <a name="to-size-a-control"></a>Größe eines Steuerelements  
  
1.  Wählen Sie das Steuerelement.  
  
2.  Ziehen Sie die Ziehpunkte, um die Größe des Steuerelements zu ändern:  
  
    -   Ziehpunkte an den oberen und den Seiten die horizontale oder vertikale Größe geändert.  
  
    -   Ziehpunkte an den Ecken ändern Sie horizontale und vertikale Größe.  
  
    > [!TIP]
    >  Sie können die Steuerelement ein Dialog-Einheit (DLU) zu einem Zeitpunkt ändern, halten die **UMSCHALT** Schlüssel- und unter Verwendung der **Pfeil nach rechts** und **nach-unten-** Schlüssel.  
  
### <a name="to-automatically-size-a-control-to-fit-the-text-within-it"></a>Automatisch die Größe ein Steuerelement für den Text angepasst  
  
1.  Wählen Sie **Größe an Inhalt anpassen** aus der **Format** Menü.  
  
 \- oder –  
  
-   Klicken Sie auf das Steuerelement, und wählen Sie **Größe an Inhalt anpassen** aus dem Kontextmenü.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)