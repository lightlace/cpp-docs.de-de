---
title: Bearbeiten in einer Zugriffstastentabelle (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator tables [C++], editing
- keyboard shortcuts [C++], editing in an accelerator table
ms.assetid: 545b650b-4f26-4b20-8431-d942548443bd
ms.openlocfilehash: 3955a74f9387c5f89d4217436e16e76b53bc3f6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463000"
---
# <a name="editing-in-an-accelerator-table-c"></a>Bearbeiten in einer Zugriffstastentabelle (C++)

### <a name="to-edit-in-an-accelerator-table"></a>So führen Sie die Bearbeitung in einer Zugriffstastentabelle durch

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie einen Eintrag in der Tabelle aus, und klicken Sie, um die direkte Bearbeitung zu aktivieren.

3. Treffen Sie eine Auswahl im Dropdown-Kombinationsfeld, oder geben Sie diese direkt ein, um Änderungen vornehmen.

   - Für [ID](id-property.md), wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für [Modifizierer](../windows/accelerator-modifier-property.md), wählen Sie aus der Liste.

   - Für [Schlüssel](../windows/accelerator-key-property.md), wählen Sie aus der Liste, oder geben Sie zum Bearbeiten.

   - Für [Typ](../windows/accelerator-type-property.md)Option **ASCII** oder **VIRTKEY** aus der Liste.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)<br/>
[Zugriffstasten-Editor](../windows/accelerator-editor.md)