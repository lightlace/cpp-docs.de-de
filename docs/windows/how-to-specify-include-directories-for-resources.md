---
title: 'Vorgehensweise: angeben Includeverzeichnissen für Ressourcen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- directories [C++], specifying include paths for resources
- include files, specifying for resources
- resources [Visual Studio], including in projects
ms.assetid: d6a7c0f6-4810-4bb0-b4b7-7d2476a20ca2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c52f2a17e347e7b37152a3d7a78423f0523b5679
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220597"
---
# <a name="how-to-specify-include-directories-for-resources"></a>Gewusst wie: Festlegen von Includeverzeichnissen für Ressourcen

### <a name="to-specify-include-directories-for-a-specific-rc-file"></a>So legen Sie Includeverzeichnisse für eine spezifische RC-Datei fest

1. Mit der rechten Maustaste im Projektmappen-Explorer auf der RC-Datei, und wählen Sie **Eigenschaften** aus dem Kontextmenü.

2. In der **Eigenschaftenseiten** Dialogfeld klicken Sie auf die **Ressourcen** Knoten im linken Bereich, geben Sie dann die zusätzlichen "include"-Verzeichnissen in die **Zusätzliche Includeverzeichnisse** Diese Eigenschaft.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in .NET Framework-Entwicklerhandbuch. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](https://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Dialogfeld „Ressourcenincludes“](../windows/resource-includes-dialog-box.md)  
[TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md)  
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Ressourcen-Editor](../windows/resource-editors.md)