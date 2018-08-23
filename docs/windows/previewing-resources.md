---
title: Anzeigen einer Vorschau Ressourcen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.previewing
- vs.resvw.resource.previewing
dev_langs:
- C++
helpviewer_keywords:
- resources [Visual Studio], viewing
- resource previews
- code, viewing
ms.assetid: d6abda66-0e2b-4ac3-a59a-a57b8c6fb70b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e6e15a4557d8368596021307ba7045bfb4b08664
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583831"
---
# <a name="previewing-resources"></a>Anzeigen von Ressourcen in der Vorschau

Anzeigen einer Vorschau Ihrer Ressourcen, können Sie grafische Ressourcen anzeigen, ohne sie zu öffnen. Anzeigen einer Vorschau ist auch nützlich für ausführbare Dateien, nachdem Sie diese kompiliert haben, da die Ressourcen-IDs in Zahlen zu ändern. Da diese numerischen Bezeichnern nicht oft genug Informationen bereitstellen, kann die Vorschau der Ressourcen schnell identifizieren.

Sie können das visuelle Layout der die folgenden Ressourcentypen in Vorschau anzeigen:

- Bitmap

- Dialogfeld

- Symbol

- Menü

- Cursor

- Symbolleiste

Die Vorschau-Funktion gilt nicht für Ressourcen Accelerator, Manifest, Zeichenfolgentabelle und Versionsinformationen.

### <a name="to-preview-resources"></a>Vorschau der Ressourcen

1. In [Ressourcenansicht](../windows/resource-view-window.md) oder ein Dokumentfenster, und wählen Sie die Ressource ein, z. B. **IDD_ABOUTBOX**.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), klicken Sie auf die **Eigenschaftenseiten** Schaltfläche.

   \- oder –

3. Auf der **Ansicht** Menü klicken Sie auf **Eigenschaftenseiten**.

   Die **Eigenschaftenseite** für die Ressource wird geöffnet, eine Vorschau der jeweiligen Ressource angezeigt. Anschließend können Sie die **einrichten** und **unten** Pfeiltasten, um der Struktur navigieren zu steuern, **Ressourcenansicht** oder das Dokumentfenster. Die **Eigenschaftenseite** bleibt geöffnet und zeigt Sie alle Ressourcen, die Fokus besitzt und kann in der Vorschau angezeigt werden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)  
[Ressourcen-Editor](../windows/resource-editors.md)