---
title: Hinzufügen oder löschen eine Zeichenfolgenressource (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.string
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], adding to string tables
- string tables [C++], deleting strings
- strings [C++], deleting in string tables
- string tables [C++], adding strings
ms.assetid: 077077b4-0f4b-4633-92d6-60b321164cab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b3800a99a6c3ae22b34f1c70a7a688ae523b7a67
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50061640"
---
# <a name="adding-or-deleting-a-string-resource-c"></a>Hinzufügen oder löschen eine Zeichenfolgenressource (C++)

Sie können schnell Einfügen neuer Einträge in die Tabelle mit den **Zeichenfolge** Editor. Neue Zeichenfolgen befinden sich am Ende der Tabelle und den nächsten verfügbaren Bezeichner erhalten. Anschließend können Sie bearbeiten die **ID**, **Wert**, oder **Beschriftung** Eigenschaften in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) je nach Bedarf.

Die **Zeichenfolge** -Editor wird sichergestellt, verwenden Sie keine ID, die bereits verwendet wird. Wenn Sie eine ID bereits verwendet wird, wählen Sie die **Zeichenfolge** Editor benachrichtigt wird, und weisen Sie eine generische eindeutige ID, z. B. `IDS_STRING58113`.

### <a name="to-add-a-string-table-entry"></a>Zum Hinzufügen eines Eintrags der Zeichenfolge-Tabelle

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Mit der rechten Maustaste in der Tabelle, und wählen Sie **neue Zeichenfolge** aus dem Kontextmenü.

3. In der **Zeichenfolge** -Editor, wählen eine **ID** aus der ID Dropdown-Liste oder geben Sie eine ID direkt vorhanden.

4. Bearbeiten der **Wert**, falls erforderlich.

5. Geben Sie einen Eintrag für die **Beschriftung**.

   > [!NOTE]
   > NULL-Zeichenfolgen werden in der Windows-Zeichenfolgentabellen nicht zulässig. Wenn Sie einen Eintrag in der Zeichenfolgentabelle, die eine null-Zeichenfolge ist erstellen, erhalten Sie eine Meldung gebeten, "Bitte geben Sie eine Zeichenfolge für diesen Tabelleneintrag."

### <a name="to-delete-a-string-table-entry"></a>So löschen Sie einen Zeichenfolgeneintrag-Tabelle

1. Wählen Sie den zu löschenden Eintrag aus.

2. Auf der **bearbeiten** Menü klicken Sie auf **löschen**.

\- oder –

- Mit der rechten Maustaste in der Zeichenfolge, die Sie verwenden möchten, löschen, und wählen **löschen** aus dem Kontextmenü.

\- oder –

- Drücken Sie die **löschen** Schlüssel.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)