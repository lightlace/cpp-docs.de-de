---
title: Verschieben und Kopieren von Menüs und Menübefehlen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7933aeb5b9b12e761c684a1a9b62c4201ef4bdb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204837"
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>Verschieben und Kopieren von Menüs und Menübefehlen

Sie können Menüs und Menübefehle mithilfe der Drag-and-Drop-Methode oder mithilfe von Befehlen im Kontextmenü (Rechtsklickmenü) verschieben oder kopieren.

### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>So verschieben oder kopieren Sie Menüs oder Menübefehle mithilfe der Drag-and-Drop-Methode

1. Ziehen oder kopieren Sie das zu verschiebende Elemente in:

   - Eine neue Position im aktuellen Menü.

   - Ein anderes Menü. (Sie können zu anderen Menüs navigieren, indem Sie den Mauszeiger darüber ziehen.)

2. Legen Sie den Menübefehl ab, wenn die Einfügemarke die gewünschte Position anzeigt.

### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>So verschieben oder kopieren Sie Menübefehle mithilfe von Kontextmenübefehlen

1. Klicken Sie mit der rechten Maustaste auf mindestens ein Menü oder Menübefehl

2. Wählen Sie im Kontextmenü **Ausschneiden** (zum Verschieben) oder **Kopieren**aus.

3. Wenn Sie die Elemente zu einer anderen Menüressource oder Ressourcenskriptdatei verschieben, [öffnen Sie sie in einem anderen Fenster](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

4. Wählen Sie die Position des Menüs oder Menübefehls aus, zu der Sie das Verschieben oder Kopieren vornehmen möchten.

5. Wählen Sie im Kontextmenü **Einfügen**aus. Das verschobene oder kopierte Element wird vor dem von Ihnen ausgewählten Element platziert.

   > [!NOTE]
   > Sie können Elemente auch ziehen und kopieren und sie in anderen Menüs in anderen Menüfenstern einfügen.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, die Zugriff auf Ressourcen Zeichenfolgen zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcen auf Eigenschaften.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Menü-Editor](../windows/menu-editor.md)