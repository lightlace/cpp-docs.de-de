---
title: Ändern der Eigenschaften mehrerer Zugriffstasten (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts [C++], property changing
- accelerator tables [C++], changing properties
ms.assetid: b55c9bd6-b430-48bb-b942-0e6f21d7abf9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bf70622dc901842a74cf8718d9447f899defb57d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313519"
---
# <a name="changing-the-properties-of-multiple-accelerator-keys-c"></a>Ändern der Eigenschaften mehrerer Zugriffstasten (C++)

### <a name="to-change-the-properties-of-multiple-accelerator-keys"></a>Zum Ändern der Eigenschaften mehrerer Zugriffstasten

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zugriffstasten, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie die einzelnen Elemente klicken.

3. Wechseln Sie zu der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) , und geben Sie die Werte aller ausgewählten Zugriffstasten freigeben.

   > [!NOTE]
   > Jeder Modifiziererwert angezeigt wird, als eine boolesche Eigenschaft in der **Eigenschaften** Fenster. Wenn Sie ändern eine [Modifizierer](../windows/accelerator-modifier-property.md) Wert in der **Eigenschaften** Fenster die Zugriffstastentabelle behandelt den new-Modifizierer als eine Erweiterung für alle Modifizierer, die bereits vorhanden waren. Aus diesem Grund setzen Sie alle Modifiziererwerte, Sie benötigen, legen Sie alle Angaben, um sicherzustellen, dass alle Zugriffstasten dasselbe **Modifizierer** Einstellungen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)  
[Zugriffstasten-Editor](../windows/accelerator-editor.md)