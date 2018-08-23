---
title: Hinzufügen eines Eintrags zu einer Zugriffstastentabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d463dc59e88dbd5c302de632d5261f29d8a4aab
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595566"
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>Hinzufügen eines Eintrags zu einer Zugriffstastentabelle

### <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Mit der rechten Maustaste in die Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste** über das Kontextmenü, oder klicken Sie auf die leere Zeile am unteren Rand der Tabelle.

3. Wählen Sie eine [ID](id-property.md) Feld aus der Dropdown-Liste in die ID, oder geben Sie eine neue ID in der **ID** Feld.

4. Typ der [Schlüssel](../windows/accelerator-key-property.md) Sie verwenden möchten, verwenden Sie als eine Zugriffstaste oder eine mit der rechten Maustaste, und wählen **Nächste Taste** aus dem Kontextmenü aus, um eine Tastenkombination festzulegen (der **Nächste Taste** Befehl ist auch verfügbar in der **bearbeiten** Menü).

5. Ändern der [Modifizierer](../windows/accelerator-modifier-property.md) und [Typ](../windows/accelerator-type-property.md), falls erforderlich.

6. Drücken Sie die **EINGABETASTE**.

   > [!NOTE]
   > Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Sie können mehrere Tastenkombinationen ohne weitere Auswirkungen, z. B. dieselbe ID zugewiesen haben **STRG** + **P** und **F8** "id_print" zugewiesen werden. Allerdings müssen Sie eine Tastenkombination zugewiesen mit ID nicht, z. B. funktioniert mehr als einem **STRG** + **Z** sowohl "ID_SPELL_CHECK" und "Dies zugewiesen.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)  
[Zugriffstasten-Editor](../windows/accelerator-editor.md)