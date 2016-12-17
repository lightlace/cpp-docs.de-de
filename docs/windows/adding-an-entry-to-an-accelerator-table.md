---
title: "Hinzuf&#252;gen eines Eintrags zu einer Zugriffstastentabelle"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zugriffstastentabellen [C++], Hinzufügen von Einträgen"
  - "Neue Zugriffstaste (Befehl)"
ms.assetid: 559c2415-8323-4339-9447-6966665f8288
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# Hinzuf&#252;gen eines Eintrags zu einer Zugriffstastentabelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

### <a name="to-add-an-entry-to-an-accelerator-table"></a>So fügen Sie einer Zugriffstastentabelle einen Eintrag hinzu  
  
1.  Öffnen Sie durch Doppelklicken auf das Symbol in der Zugriffstastentabelle [Ressourcenansicht](../windows/resource-view-window.md).  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Mit der rechten Maustaste in der Zugriffstastentabelle, und wählen Sie **neue Zugriffstaste** über das Kontextmenü, oder klicken Sie auf die leere Zeile am unteren Rand der Tabelle.  
  
3.  Wählen Sie eine [ID](Id%20Property.xml) Feld aus der Dropdown-Liste in der ID, oder geben Sie eine neue ID in der **ID** Feld.  
  
4.  Typ der [Schlüssel](../windows/accelerator-key-property.md) Sie verwenden möchten, verwenden Sie als Zugriffstaste oder mit der rechten Maustaste, und wählen **Nächste Taste** aus dem Kontextmenü, um eine Tastenkombination festzulegen (der **Nächste Taste** Befehl steht auch die **Bearbeiten** Menü).  
  
5.  Ändern der [Modifizierer](../windows/accelerator-modifier-property.md) und [Typ](../windows/accelerator-type-property.md), falls erforderlich.  
  
6.  Drücken Sie **EINGABETASTE**.  
  
    > [!NOTE]
    >  Stellen Sie sicher, dass alle von Ihnen definierten Zugriffstasten eindeutig sind. Der gleichen ID können mehrere Tastenkombinationen ohne weitere Auswirkungen zugewiesen werden, z. B. können STRG+P und F8 „ID_PRINT“ zugewiesen werden. Wenn eine Tastenkombination mehr als einer ID zugewiesen wird, funktioniert dies nicht ordnungsgemäß, z. B. wenn STRG+Z sowohl „ID_SPELL_CHECK“ als auch „ID_THESAURUS“ zugewiesen wird.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 **Anforderungen**  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Bearbeiten von Zugriffstastentabellen](../windows/editing-accelerator-tables.md)   
 [Zugriffstasten-Editor](../mfc/accelerator-editor.md)