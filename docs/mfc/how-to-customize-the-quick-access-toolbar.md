---
title: 'Vorgehensweise: Anpassen der schnellen Zugriffssymbolleiste | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0f3ec14971b69788892690c26ef2759f3b35d55f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419101"
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Gewusst wie: Anpassen der Symbolleiste für den Schnellzugriff

Der schnelle Zugriff Symbolleiste (QAT) ist eine anpassbare Symbolleiste, die eine Reihe von Befehlen enthält, die entweder neben der Schaltfläche "Anwendung" oder auf den Registerkarten für die Kategorie angezeigt. Die folgende Abbildung zeigt eine typische Symbolleiste für den Schnellzugriff an.

![MFC-Menüband die Symbolleiste für Schnellzugriff](../mfc/media/quick_access_toolbar.png "Quick_access_toolbar")

Informationen zum Anpassen der Symbolleiste für den Schnellzugriff öffnen Sie es in der **Eigenschaften** , ändern Sie die Befehle, und klicken Sie dann eine Vorschau des Menüband-Steuerelements.

### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>Auf der Symbolleiste für den Schnellzugriff im Eigenschaftenfenster zu öffnen.

1. In Visual Studio auf die **Ansicht** Menü klicken Sie auf **Ressourcenansicht**.

1. In **Ressourcenansicht**, doppelklicken Sie auf die menübandressource, um sie auf der Entwurfsoberfläche anzuzeigen.

1. Klicken Sie auf die Entwurfsoberfläche, mit der rechten Maustaste in der Symbolleiste für den Schnellzugriff-Menü, und klicken Sie dann auf **Eigenschaften**.

## <a name="quick-access-toolbar-properties"></a>Eigenschaften für Schnellzugriff-Symbolleiste

In der folgende Tabelle definiert die Eigenschaften der Symbolleiste für den Schnellzugriff an.

|Eigenschaft|Definition|
|--------------|----------------|
|QAT Position|Gibt die Position der Symbolleiste für den Schnellzugriff an, beim Starten der Anwendung. Die Position kann es sich um **oben** oder **unten** des Menüband-Steuerelements.|
|QAT Items|Gibt die Befehle, die für die Symbolleiste für den Schnellzugriff verfügbar sind.|

#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>Zum Hinzufügen oder Entfernen von Befehlen auf der Symbolleiste für den Schnellzugriff

1. In der **Eigenschaften** Fenster, klicken Sie auf **QAT Items**, und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten **(...)** .

1. In der **QAT Items Editor** Dialogfelds die **hinzufügen** und **entfernen** Schaltflächen so ändern Sie die Liste der Befehle auf der Symbolleiste für den Schnellzugriff.

1. Wenn Sie einen Befehl auf der Symbolleiste für den Schnellzugriff und die Symbolleiste für den Schnellzugriff im Menü angezeigt werden soll, wählen Sie das Kontrollkästchen neben den Befehl. Wenn der Befehl nur auf das Menü angezeigt werden soll, deaktivieren Sie das Kontrollkästchen.

## <a name="previewing-the-ribbon"></a>Anzeigen einer Vorschau im Menüband

Symbolleiste für den schnellbefehle werden nicht auf der Entwurfsoberfläche angezeigt. Um diese anzuzeigen, müssen Sie eine Vorschau im Menüband oder die Anwendung auszuführen.

#### <a name="to-preview-the-ribbon-control"></a>Vorschau des Menüband-Steuerelements

- Auf der **Ribbon-Editor-Symbolleiste**, klicken Sie auf **Ribbon testen**.

## <a name="see-also"></a>Siehe auch

[Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

