---
title: Hinzufügen von Dateien zu leeren Win32-Anwendungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- empty projects [C++], adding files
- projects [C++], adding items
- blank projects
- files [C++], adding to projects
ms.assetid: 070098e8-0396-49fe-a697-3daa2f1be6de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7ed87390608c05a215caf9c9991c286e5fb0be4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060974"
---
# <a name="adding-files-to-an-empty-win32-applications"></a>Hinzufügen von Dateien zu leeren Win32-Anwendungen

### <a name="to-add-your-files-to-an-empty-windows-desktop-application"></a>So fügen Sie Ihre Dateien einer leeren Windows-Desktop-Anwendung hinzu

1. Wählen Sie das Verzeichnis im **Projektmappen-Explorer**aus.

2. Klicken Sie mit der rechten Maustaste auf den Verzeichnisnamen, klicken Sie im Kontextmenü auf **Hinzufügen** , und klicken Sie dann auf **Vorhandenes Element**.

3. Navigieren Sie im Dialogfeld **Vorhandenes Element hinzufügen**zu den Dateien, die Sie Ihrem Projekt hinzufügen möchten.

4. Klicken Sie auf **OK**.

Hinzufügen von Dateien, die weder Quell-, Header oder Ressourcendateien, die Ihr Projekt sind Informationen zu diesem mit der rechten Maustaste die **Lösung** Knoten **Projektmappen-Explorer** und fügen Sie die Dateien zum Projekt hinzu, auf die gleiche Weise. Ein **Sonstiges** Ordner erstellt wird, um die anderen Dateien in Ihrem Projekt zu speichern.

> [!NOTE]
> Bevor Sie Ihr Projekt erstellen, müssen Sie Buildoptionen für diese Dateien angeben, damit sie ordnungsgemäß in die fertige Anwendung eingeschlossen werden. Weitere Informationen finden Sie unter [Angeben von Projekteinstellungen mithilfe von Eigenschaftenseiten](../ide/property-pages-visual-cpp.md) und [Erstellen eines C/C++-Programms](../build/building-c-cpp-programs.md).

## <a name="see-also"></a>Siehe auch

[Erstellen einer leeren Windows-Desktopanwendung](../windows/creating-an-empty-windows-desktop-application.md)
