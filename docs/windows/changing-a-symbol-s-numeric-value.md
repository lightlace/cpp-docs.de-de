---
title: Ändern eines Symbols&#39;Zahlenwert s | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.value
dev_langs:
- C++
helpviewer_keywords:
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eef16275bcd563a258347f8853a3c705594df99d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318671"
---
# <a name="changing-a-symbol39s-numeric-value"></a>Ändern eines Symbols&#39;s numerischer Wert

Symbole, die eine einzelne Ressource zugeordnet werden, können Sie die [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) den Symbolwert zu ändern. Können Sie die [Dialogfeld Ressourcensymbole](../windows/resource-symbols-dialog-box.md) so ändern Sie den Wert von Symbolen, die derzeit nicht auf eine Ressource zugewiesen. Weitere Informationen finden Sie unter [ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md).

### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>So ändern Sie einen zu einer einzelnen Ressource oder einem Objekt zugewiesenen Symbolwert

1. In [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie die Ressource.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der **Eigenschaften** geben den Symbolnamen, gefolgt von einem Gleichheitszeichen und einer ganzen Zahl in die **ID** Feld, z. B.:

    ```
    IDC_EDITNAME=5100
    ```

Der neue Wert wird in der Symbolheaderdatei gespeichert, wenn Sie das nächste Mal das Projekt speichern. Nur der Symbolnamen verbleibt weiterhin im Feld „ID“ sichtbar. Nach der Überprüfung werden das Gleichheitszeichen und der Wert nicht mehr angezeigt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, die Zugriff auf Ressourcen Zeichenfolgen zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcen auf Eigenschaften.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Beschränkungen bei Symbolwerten](../windows/symbol-value-restrictions.md)  
[Vordefinierte Symbol-IDs](../windows/predefined-symbol-ids.md)