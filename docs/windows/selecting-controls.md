---
title: Auswählen von Steuerelementen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Dialog editor, selecting controls
- dominant controls
- dialog box controls, selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5c8a7a57b263fc3db1fa7f021c1a6f4e09c0f8f7
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605668"
---
# <a name="selecting-controls"></a>Markieren von Steuerelementen
Auswählen von Steuerelementen auf Größe, ausrichten, verschieben, kopieren, oder löschen und anschließend den gewünschten Vorgang ausführen. In den meisten Fällen müssen Sie zu verwenden, die Tools zur größenanpassung und die Ausrichtung auf mehrere Steuerelement auswählen, die [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
 Wenn ein Steuerelement ausgewählt ist, einen schattierten Rahmen mit Solid (aktiv hat) oder leere (deaktivierte) "Ziehpunkten" kleine, die Quadrate in den Auswahlrahmen angezeigt werden. Wenn mehrere Steuerelemente ausgewählt sind, hat das dominante Steuerelement gefüllte Ziehpunkte; Alle anderen ausgewählten Steuerelemente haben leere Ziehpunkte an.  
  
 Wenn verkleinert oder Ausrichten von mehreren Steuerelementen aus, verwendet des Dialog-Editors "vorherrschende Control" um zu bestimmen, wie die anderen Steuerelemente angepasst oder ausgerichtet sind. Standardmäßig ist das dominante Steuerelement das erste Steuerelement ausgewählt.  
  
-   [Markieren mehrerer Steuerelemente](../windows/selecting-multiple-controls.md)  
  
-   [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)