---
title: Versionsinfo-Editor (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.version.F1
- vc.editors.version
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
- version information resources [C++]
- resources [C++], editing version information
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: 8420feb6ddde116a24bee5333f4ef8f83ff4e0d4
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320470"
---
# <a name="version-information-editor-c"></a>Versionsinfo-Editor (C++)

Versionsinformationen bestehen aus einer Firmen- und einer Produkt-ID, einer Produktseriennummer und Copyright- und Markenbestimmungen. Mit der **Versionsinformationen** -Editor erstellt und verwaltet diese Daten, die in der Versionsinformationsressource gespeichert wird. Die Versionsinformationsressource ist nicht von einer Anwendung erforderlich, aber es ist eine nützliche Möglichkeit zum Sammeln von Informationen, die die Anwendung identifiziert. Versionsinformationen werden auch von Setup-APIs verwendet.

Eine Versionsinformationsressource weist einen oberen Block und mindestens einen unteren Block auf: ein einzelner Block mit unveränderlichen Informationen oben und mindestens ein weiterer Versionsinformationsblock darunter (für andere Sprachen und/oder Zeichensätze). Der obere Block weist sowohl editierbare Zahlenfelder als auch auswählbare Dropdownlisten auf. Die unteren Blöcke weisen nur editierbare Textfelder auf.

> [!NOTE]
> Der Windows-Standard sieht nur eine Versionsressource mit dem Namen VS_VERSION_INFO vor.

## <a name="how-to"></a>Exemplarische Vorgehensweise

Die **Versionsinformationen** -Editor können Sie:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>So bearbeiten Sie eine Zeichenfolge in einer Versionsinformationsressource

Wählen Sie das Element einmal an, klicken Sie dann erneut mit der Bearbeitung anfangen möchten. Nehmen Sie die Änderungen direkt in die **Versionsinformationen** Tabelle oder in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window). Die vorgenommenen Änderungen werden an beiden Orten berücksichtigt.

Beim Bearbeiten der `FILEFLAGS` -Schlüssel in der **Versionsinformationen** -Editor, Sie werden bemerken Sie nicht Festlegen der **Debuggen**, **Private Build**, oder **spezielle Erstellen Sie** Eigenschaften (in der **Eigenschaften** Fenster) für RC-Dateien:

- Die **Versionsinformationen** legt die **Debuggen** Eigenschaft mit einer `#ifdef` im Ressourcenskript, basierend auf den `_DEBUG` build-Flag.

- Wenn die `Private Build` Schlüssel besitzt eine **Wert** legen Sie in der **Versionsinformationen** Tabelle, die entsprechende **Private Build** Eigenschaft (in der **Eigenschaften**  Fenster) für die `FILEFLAGS` Schlüssel **"true"**. Wenn der **Wert** leer ist, ist die Eigenschaft **False**. Ebenso der **Special Build** Schlüssel (in der **Versionsinformationen** Tabelle) gebunden ist, um die **Special Build** -Eigenschaft für die `FILEFLAGS` Schlüssel.

Sie können die Sequenz der Informationen des Zeichenfolgenblocks sortieren, indem Sie entweder die **Schlüssel** oder **Wert** Spaltenüberschriften. Mithilfe dieser Überschriften können die Informationen automatisch in der ausgewählten Reihenfolge neu angeordnet werden.

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>Hinzufügen von Versionsinformationen für eine andere Sprache (Neuer Versionsinformationsblock)

1. Öffnen Sie eine Versionsinformationsressource, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md)darauf doppelklicken.

1. Klicken Sie mit der rechten Maustaste in der Versionsinformationstabelle, und wählen Sie aus dem Kontextmenü **Neuer Versionsinformationsblock** aus.

   Dieser Befehl fügt der aktuellen Versionsinformationsressource einen zusätzlichen Informationsblock hinzu und öffnet dessen entsprechende Eigenschaften im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window).

1. Wählen Sie im **Eigenschaftenfenster** die Sprache und den Zeichensatz für den neuen Block aus.

### <a name="to-delete-a-version-information-block"></a>So löschen Sie einen Versionsinformationsblock

1. Öffnen Sie die Versionsinformationsressource, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md)auf ihr Symbol doppelklicken.

1. Klicken Sie mit der rechten Maustaste auf den Blockheader, den Sie löschen möchten, und wählen Sie dann im Kontextmenü **Versionsinformationsblock löschen** aus.

   Dieser Befehl löscht den ausgewählten Header und den Rest der Versionsinformationen bleiben intakt. Sie können nicht rückgängig gemacht werden.

### <a name="to-access-version-information-from-within-your-program"></a>So greifen Sie aus Ihrem Programm auf Versionsinformationen zu

Wenn Sie aus ihrem Programm auf die Versionsinformationen zugreifen möchten, verwenden Sie die Funktion [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) und die Funktion [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) .

   > [!NOTE]
   > Bei der Verwendung der **Versionsinformationen** -Editor, in vielen Fällen, Sie können mit der rechten Maustaste, ein Kontextmenü mit ressourcenspezifische Befehle angezeigt. Beispielsweise wenn Sie auswählen, während Sie auf einen Blockheadereintrag zeigen, zeigt das Kontextmenü der **neue Versionsblockinformationen** und **Versionsblockinformationen löschen** Befehle.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Menüs und weitere Ressourcen](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)
