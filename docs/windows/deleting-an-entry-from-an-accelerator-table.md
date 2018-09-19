---
title: Löschen eines Eintrags aus einer Zugriffstastentabelle (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], deleting entries
- keyboard shortcuts [C++], deleting entry from accelerator table
ms.assetid: cc9cd499-dc04-4fe6-9393-a3e471e115a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9543f33895e112634bf9c62b00652760313af97f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46397194"
---
# <a name="deleting-an-entry-from-an-accelerator-table-c"></a>Löschen eines Eintrags aus einer Zugriffstastentabelle (C++)

### <a name="to-delete-an-entry-from-an-accelerator-table"></a>So löschen Sie einen Eintrag aus einer Zugriffstastentabelle

1. Öffnen Sie die Zugriffstastentabelle durch Doppelklicken auf das Symbol im [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie den zu löschenden Eintrag aus. (Halten Sie die **STRG** oder **UMSCHALT** beim Klicken auf die Schlüssel, um mehrere Einträge auszuwählen.)

3. Mit der rechten Maustaste, und wählen Sie **löschen** aus dem Kontextmenü (oder wählen Sie **löschen** aus der **bearbeiten** Menü).

\- oder –

- Drücken Sie die **löschen** Schlüssel.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)<br/>
[Zugriffstasten-Editor](../windows/accelerator-editor.md)