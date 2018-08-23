---
title: Festlegen des bestimmenden Steuerelements | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dominant controls
- Dialog editor, dominant control
- controls [C++], dominant
ms.assetid: 42b523a7-192a-417b-9512-d4af795e002f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 93e8d1dff23d77d861a52d4f1531203ebd05987b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42593295"
---
# <a name="specifying-the-dominant-control"></a>Festlegen des bestimmenden Steuerelements

Das ausgewählte Steuerelement ist zunächst das dominante Steuerelement.

### <a name="to-specify-the-dominant-control"></a>Zum Angeben des bestimmenden Steuerelements

1. Halten Sie die **STRG** gedrückt, und klicken Sie auf das Steuerelement, das Sie nutzen, um die Größe oder Position von anderen Steuerelementen beeinflussen möchten *erste*.

   **Beachten Sie** die Ziehpunkte des bestimmenden Steuerelements sind solid, während die Ziehpunkte der untergeordneten Steuerelemente leer sind. Alle weiteren Ändern der Größe oder Ausrichtung basiert auf das dominante Steuerelement.

### <a name="to-change-the-dominant-control"></a>Ändern des bestimmenden Steuerelements

1. Löschen Sie die aktuelle Auswahl, indem Sie die außerhalb aller derzeit ausgewählten Steuerelemente auf.

2. Wiederholen Sie die vorherigen Schritte, und wählen ein anderes Steuerelement zuerst aus.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Markieren mehrerer Steuerelemente](../windows/selecting-multiple-controls.md)  
[Auswählen von Steuerelementen](../windows/selecting-controls.md)  
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)