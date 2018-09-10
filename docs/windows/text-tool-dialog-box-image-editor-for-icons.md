---
title: Im Dialogfeld für Texttool (C++) (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.texttool
dev_langs:
- C++
helpviewer_keywords:
- text, adding to an image
- Text Tool dialog box [C++]
ms.assetid: a6036ef4-1871-40db-8239-6ddbe8f422f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e55ad361c9252cfc4989926f90a9fedfd523c7d9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44313445"
---
# <a name="text-tool-dialog-box-c-image-editor-for-icons"></a>Im Dialogfeld für Texttool (C++) (Bildbearbeitung für Symbole)

Verwenden der **Texttool** Dialogfeld zum Hinzufügen von Text mit einem Cursor, Bitmap oder Symbol.

Um dieses Dialogfeld zuzugreifen, öffnen die [Bildbearbeitung](../windows/window-panes-image-editor-for-icons.md). Wählen Sie **Tools** aus der **Image** Menü, und wählen Sie dann die **Texttool** Befehl.

### <a name="font-button"></a>Schaltfläche "Schriftart"

Öffnet die [Schriftart für Texttool (Dialogfeld)](../windows/text-tool-font-dialog-box-image-editor-for-icons.md), in dem Sie die Schriftart, Schriftschnitt oder Schriftgrad Cursor ändern können. Änderungen werden angewendet, um den Text in die **Text** Bereich.

### <a name="text-area"></a>Textbereich

Zeigt den Text, der als Teil der Ressource angezeigt wird. Dieser Bereich ist zunächst leer.

> [!NOTE]
> Wenn **transparenten Hintergrund** festgelegt ist, wird nur der Text in das Image platziert werden. Wenn **nicht transparenter Hintergrund** festgelegt ist, wird ein umschließendes Rechteck, gefüllt mit dem [Hintergrundfarbe](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md), hinter dem Text platziert werden. Weitere Informationen finden Sie unter [Auswählen eines transparenten oder deckenden Hintergrundes](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Sie können mit der rechten Maustaste auf die **Texttool** im Dialogfeld ein standardmäßigen Kontextmenü zugreifen, die eine Liste der standard-Windows-Befehle enthält.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)