---
title: "Hinzufügen eines Eintrags zu einer Zugriffstastentabelle | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accelerator tables [C++], adding entries
- New Accelerator command
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9fe2df81aae0b9b7232443de1db091a9cbb0c0d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-entry-to-an-accelerator-table"></a>Hinzufügen eines Eintrags zu einer Zugriffstastentabelle
### <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu  
  
1.  Öffnen Sie die Zugriffstastentabelle, indem Sie doppelklicken auf das Symbol in [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Mit der rechten Maustaste in die Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste** aus dem Kontextmenü aus, oder klicken Sie auf die leere Zeile am unteren Rand der Tabelle.  
  
3.  Wählen Sie eine [ID](id-property.md) Feld aus der Dropdown-Liste in der ID, oder geben Sie eine neue ID in der **ID** Feld.  
  
4.  Typ der [Schlüssel](../windows/accelerator-key-property.md) Sie verwenden möchten, verwenden Sie als Zugriffstaste oder mit der rechten Maustaste, und wählen **Nächste Taste** aus dem Kontextmenü aus, um eine Tastenkombination festzulegen (der **Nächste Taste** Befehl ist auch verfügbar in der **bearbeiten** Menü).  
  
5.  Ändern der [Modifizierer](../windows/accelerator-modifier-property.md) und [Typ](../windows/accelerator-type-property.md), falls erforderlich.  
  
6.  Drücken Sie die **EINGABETASTE**.  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Der gleichen ID können mehrere Tastenkombinationen ohne weitere Auswirkungen zugewiesen werden, z. B. können STRG+P und F8 „ID_PRINT“ zugewiesen werden. Wenn eine Tastenkombination mehr als einer ID zugewiesen wird, funktioniert dies nicht ordnungsgemäß, z. B. wenn STRG+Z sowohl „ID_SPELL_CHECK“ als auch „ID_THESAURUS“ zugewiesen wird.  
  

  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)   
 [Zugriffstasten-Editor](../windows/accelerator-editor.md)