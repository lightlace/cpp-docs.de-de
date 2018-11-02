---
title: Zugriffstasten-Editor (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator.F1
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: fdb2d9cf0954142da990a0a9f995cb482060345d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621493"
---
# <a name="accelerator-editor-c"></a>Zugriffstasten-Editor (C++)

Eine Zugriffstastentabelle ist eine C++-Windows-Ressource, die eine Liste mit Zugriffstasten (auch als Tastenkombinationen bezeichnet) enthält und die Befehls-IDs, die ihnen zugeordnet sind. Ein Programm kann über mehrere Zugriffstastentabellen verfügen.

Normalerweise werden Zugriffstasten als Tastenkombinationen für Programmbefehle verwendet, die auch in einem Menü oder auf einer Symbolleiste verfügbar sind. Allerdings können Sie die Zugriffstastentabelle auch verwenden, um Tastenkombinationen für Befehle zu definieren, denen kein Objekt auf der Benutzeroberfläche zugeordnet ist.

Sie können die [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code) verwenden, um Zugriffstastenbefehle mit Code zu verknüpfen.

Mit der **Accelerator** -Editor können Sie:

- [Festlegen von Zugriffstasteneigenschaften](../windows/setting-accelerator-properties.md)

- [Zuordnen einer Zugriffstaste zu einem Menüeintrag](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)

- [Verwenden vordefinierter Zugriffstasten](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > Bei der Verwendung der **Accelerator** -Editor, Sie können mit der rechten Maustaste ein Kontextmenü mit häufig verwendeten Befehlen anzuzeigen. Die verfügbaren Befehle hängen davon ab, auf was der Zeiger verweist.

   > [!NOTE]
   > Windows lässt die Erstellung leerer Zugriffstastentabellen nicht zu. Wenn Sie eine Zugriffstastentabelle ohne Einträge erstellen, wird diese beim Speichern automatisch gelöscht.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)