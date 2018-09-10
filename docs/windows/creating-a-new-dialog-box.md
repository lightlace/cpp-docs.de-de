---
title: Erstellen eines neuen Dialogfelds (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], creating
- Dialog Editor [C++], creating dialog boxes
ms.assetid: 303de801-c4f8-42e1-b622-353f6423f688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 285444b5f9bfa29ab00fc6a2ca1b644208bc95a8
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315794"
---
# <a name="creating-a-new-dialog-box-c"></a>Erstellen eines neuen Dialogfelds (C++)

### <a name="to-create-a-new-dialog-box"></a>Um ein neues Dialogfeld zu erstellen.

1. In [Ressourcenansicht](../windows/resource-view-window.md)mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der **Ressource hinzufügen** wählen Sie im Dialogfeld **Dialogfeld** in die **Ressourcentyp** und dann auf **neu**.

   Wenn ein Pluszeichen (**+**) wird neben der **Dialogfeld** Ressourcentyp an, es bedeutet, dass Dialogfeldvorlagen verfügbar sind. Klicken Sie auf das Pluszeichen, um der Liste der Vorlagen erweitern, wählen Sie eine Vorlage aus, und auf **neu**.

   Das neue Dialogfeld wird geöffnet, der **Dialogfeld** Editor.

   Sie können auch [vorhandene Dialogfelder im Editor im Dialogfeld zur Bearbeitung öffnen](../windows/viewing-and-editing-resources-in-a-resource-editor.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Erstellen einer Ressource](../windows/how-to-create-a-resource.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Dialog-Editor](../windows/dialog-editor.md)