---
title: Ausrichten von Steuerelementgruppen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], aligning
ms.assetid: a4f49a73-4a17-44b3-8568-aa35f646b5cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c791f2951eb7ac9947d48b563bde624bc3b7979f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393580"
---
# <a name="aligning-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

Das folgende Verfahren erfahren Sie, wie Sie eine Gruppe von Steuerelementen ausrichten.

### <a name="to-align-groups-of-controls"></a>Ausrichten von Steuerelementgruppen

1. [Wählen Sie die Steuerelemente](../windows/selecting-multiple-controls.md) Sie ausrichten möchten. Achten Sie darauf, um das Steuerelement auszuwählen, die das dominante Steuerelement werden sollen oder zum Festlegen des bestimmenden Steuerelements vor dem Ausführen von die Ausrichtung, oder Ändern der Größe Befehl sein.

   Die letzte Position in der Gruppe von Steuerelementen, hängt von der Position des bestimmenden Steuerelements ab. Weitere Informationen zum Auswählen des bestimmenden Steuerelements finden Sie unter [Festlegen des bestimmenden Steuerelements](../windows/specifying-the-dominant-control.md).

2. Von der **Format** Menü wählen **ausrichten**, und wählen Sie dann eines der folgenden Ausrichtungen:

   - `Lefts`: Richtet die ausgewählten Steuerelemente an die linke Seite.

   - `Centers`: Richtet den ausgewählten Steuerelemente horizontal an ihren Mittelpunkt aus.

   - `Rights`: Richtet die ausgewählten Steuerelemente an die rechte Seite.

   - `Tops`: Richtet die ausgewählten Steuerelemente an die oberen Ränder.

   - `Middles`: Richtet den ausgewählten Steuerelemente vertikal an ihren Mittelpunkt aus.

   - `Bottoms`: Richtet die ausgewählten Steuerelemente an die unteren Rand.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Anordnung von Steuerelementen in Dialogfeldern](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)<br/>
[Steuerelemente](../mfc/controls-mfc.md)