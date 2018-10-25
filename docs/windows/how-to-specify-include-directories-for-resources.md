---
title: 'Vorgehensweise: angeben Includeverzeichnissen für Ressourcen (C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directories [C++], specifying include paths for resources
- include files [C++], specifying for resources
- resources [C++], including in projects
ms.assetid: d6a7c0f6-4810-4bb0-b4b7-7d2476a20ca2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: be030539a7b2d0585ea895f1428de822d3300d53
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052966"
---
# <a name="how-to-specify-include-directories-for-resources-c"></a>Vorgehensweise: angeben Includeverzeichnissen für Ressourcen (C++)

### <a name="to-specify-include-directories-for-a-specific-rc-file"></a>So legen Sie Includeverzeichnisse für eine spezifische RC-Datei fest

1. Mit der rechten Maustaste im Projektmappen-Explorer auf der RC-Datei, und wählen Sie **Eigenschaften** aus dem Kontextmenü.

2. In der **Eigenschaftenseiten** Dialogfeld klicken Sie auf die **Ressourcen** Knoten im linken Bereich, geben Sie dann die zusätzlichen "include"-Verzeichnissen in die **Zusätzliche Includeverzeichnisse** Diese Eigenschaft.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in .NET Framework-Entwicklerhandbuch.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Dialogfeld „Ressourcenincludes“](../windows/resource-includes-dialog-box.md)<br/>
[TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)<br/>
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)