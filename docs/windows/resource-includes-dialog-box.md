---
title: Ressourcenincludes (Dialogfeld) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.resourceincludes
dev_langs:
- C++
helpviewer_keywords:
- Resource Includes dialog box
- rc files, changing storage
- symbol header files, changing
- compiling source code, including resources
- .rc files, changing storage
- symbol header files, read-only
- symbols, symbol header files
ms.assetid: 659a54e6-e416-4045-8411-798730ff4ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 96ee92f1b21d67321b95a169cbc4c47eaca2de17
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610660"
---
# <a name="resource-includes-dialog-box"></a>Ressourcenincludes (Dialogfeld)

Können Sie die **Ressourcenincludes** Dialogfeld so ändern Sie die normale arbeitsanordnung der Umgebung zum Speichern aller Ressourcen in der RC-Datei des Projekts und alle [Symbole](../windows/symbols-resource-identifiers.md) in Resource.h gespeichert.

Zu öffnen der **Ressourcenincludes** klicken Sie im Dialogfeld mit der rechten Maustaste eine RC-Datei [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie dann **Ressourcenincludes** aus dem Kontextmenü.

**Symbolheaderdatei**  
Erlaubt es Ihnen, den Namen der Headerdatei dort zu ändern, wo die Symboldefinitionen für Ihre Ressourcendatei gespeichert werden. Weitere Informationen finden Sie unter [ändern die Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md).

**Anweisungen für schreibgeschützte Symbole**  
Ermöglicht es Ihnen, Headerdateien einzufügen, die Symbole enthalten, die während einer Bearbeitungssitzung nicht geändert werden sollen. Sie können z. B. eine Symboldatei einfügen, die von mehreren Projekten gemeinsam verwendet wird. Sie können auch die MFC H-Dateien einfügen. Weitere Informationen finden Sie unter [einschließlich gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).

**Kompilierzeitdirektiven**  
Ermöglicht Ihnen das Einfügen von Ressourcendateien, die separat von den Ressourcen in der Hauptressourcendatei erstellt und bearbeitet wurden, Kompilierzeitanweisungen (z. B. die, die bedingt Ressourcen einfügen) enthalten oder Ressourcen in einem benutzerdefinierten Format enthalten. Sie können auch der **Kompilierung Feld kompilierzeitanweisungen** zum standard-MFC-Ressourcendateien einzufügen. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

> [!NOTE]
> Einträge in diesen Textfeldern angezeigt werden, in der RC-Datei markiert `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, und `TEXTINCLUDE 3` bzw. Weitere Informationen finden Sie unter [TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).

Nachdem Sie Änderungen, um Ihrer Ressourcendatei mithilfe vorgenommen haben der **Ressourcenincludes** im Dialogfeld müssen Sie die RC-Datei zu schließen und erneut öffnen, damit die Änderungen wirksam werden. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Festlegen von Includeverzeichnissen für Ressourcen](../windows/how-to-specify-include-directories-for-resources.md)  
[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Ressourcen-Editor](../windows/resource-editors.md)