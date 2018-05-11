---
title: Dialogfeld "Ressourcenincludes" | Microsoft Docs
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
ms.openlocfilehash: 756289bb819809fed63dba579c4ad1cd1e975780
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="resource-includes-dialog-box"></a>Ressourcenincludes (Dialogfeld)
Können Sie die **Ressourcenincludes** Dialogfeld so ändern Sie die normale arbeitsanordnung der Umgebung zum Speichern aller Ressourcen in der Projektdatei .rc und alle [Symbole](../windows/symbols-resource-identifiers.md) in Resource.h.  
  
 So öffnen die **Ressourcenincludes** (Dialogfeld), mit der rechten Maustaste eine RC-Datei [Ressourcenansicht](../windows/resource-view-window.md), wählen Sie dann **Ressourcenincludes** aus dem Kontextmenü.  
  
 **Symbolheaderdatei**  
 Erlaubt es Ihnen, den Namen der Headerdatei dort zu ändern, wo die Symboldefinitionen für Ihre Ressourcendatei gespeichert werden. Weitere Informationen finden Sie unter [Ändern der Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md).  
  
 **Direktiven für schreibgeschützte Symbole**  
 Ermöglicht es Ihnen, Headerdateien einzufügen, die Symbole enthalten, die während einer Bearbeitungssitzung nicht geändert werden sollen. Sie können z. B. eine Symboldatei einfügen, die von mehreren Projekten gemeinsam verwendet wird. Sie können auch die MFC H-Dateien einfügen. Weitere Informationen finden Sie unter [einschließlich gemeinsam genutzter (schreibgeschützter) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 **Kompilierzeitdirektiven**  
 Ermöglicht Ihnen das Einfügen von Ressourcendateien, die separat von den Ressourcen in der Hauptressourcendatei erstellt und bearbeitet wurden, Kompilierzeitanweisungen (z. B. die, die bedingt Ressourcen einfügen) enthalten oder Ressourcen in einem benutzerdefinierten Format enthalten. Sie können ebenso das Feld Kompilierzeitanweisungen verwenden, um Standard-MFC-Ressourcendateien einzufügen. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  
> [!NOTE]
>  Einträge in diesen Textfeldern angezeigt werden, in der RC-Datei ComInterfaceType.InterfaceIsIDispatch `TEXTINCLUDE 1`, `TEXTINCLUDE 2`, und `TEXTINCLUDE 3` bzw. Weitere Informationen finden Sie unter [TN035: Verwenden mehrerer Ressourcendateien und Headerdateien mit Visual C++](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md).  
  
 Nachdem Sie Änderungen, zu Ihrer Ressourcendatei mithilfe vorgenommen haben der **Ressourcenincludes** (Dialogfeld), müssen Sie die RC-Datei zu schließen und erneut öffnen, damit die Änderungen wirksam werden. Weitere Informationen finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).  
  

  
## <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: angeben Includeverzeichnissen für Ressourcen](../windows/how-to-specify-include-directories-for-resources.md)   
 [Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)   
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)