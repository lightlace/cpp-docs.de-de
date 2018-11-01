---
title: 'Vorgehensweise: erstellen eine Ressourcenskriptdatei (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: eb884ca7520b34771c73e71c7ee9b4d811d5383c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491253"
---
# <a name="how-to-create-a-resource-script-file-c"></a>Vorgehensweise: erstellen eine Ressourcenskriptdatei (C++)

> [!NOTE]
> Die **Ressourcen-Editor-** ist in Express-Editionen nicht verfügbar.
>
> Diese Materialien beziehen sich auf Windows-Desktopanwendungen. Für Projekte in .NET-Sprachen werden keine Ressourcenskriptdateien verwendet. Weitere Informationen finden Sie unter [Ressourcendateien](../windows/resource-files-visual-studio.md).

### <a name="to-create-a-new-resource-script-rc-file"></a>So erstellen Sie eine neue Ressourcenskriptdatei (RC-Datei)

1. Setzen Sie den Fokus auf den vorhandenen Projektordner in **Projektmappen-Explorer**, z. B. `MyProject`.

   > [!NOTE]
   > Verwechseln Sie nicht mit dem Projektmappenordner im Projektordner **Projektmappen-Explorer**. Wenn den Fokus verschieben, auf die **Lösung** -Ordner, Ihre Auswahl in der **neues Element hinzufügen** (Dialogfeld) (in Schritt 3) unterscheiden.

2. Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.

3. Klicken Sie im Dialogfeld **Neues Element hinzufügen** auf den Ordner **Visual C++** , und wählen Sie dann **Ressourcendatei (.rc)** im rechten Bereich aus.

4. Geben Sie im Textfeld **Name** einen Namen für die Ressourcenskriptdatei ein, und klicken Sie dann auf **Öffnen**.

Sie können jetzt neue Ressourcen [erstellen](../windows/how-to-create-a-resource.md) und diese der RC-Datei hinzufügen.

> [!NOTE]
> Eine Ressourcenskriptdatei (.rc) kann nur in ein vorhandenes Projekt aufgenommen werden, das bereits in der Visual Studio-IDE geladen wurde. Es können keine eigenständige RC-Datei (außerhalb des Projekts) erstellt werden. [Ressourcenvorlagen](../windows/how-to-use-resource-templates.md) (RCT-Dateien) können jederzeit erstellt werden.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)