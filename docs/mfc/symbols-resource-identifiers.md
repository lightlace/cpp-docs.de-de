---
title: "Symbols: Resource Identifiers"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.identifiers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, resource identifiers"
  - "symbols, creating"
  - "resource symbols"
  - "symbols, editing"
  - "resource editors, resource symbols"
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Symbols: Resource Identifiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Symbol ist ein Ressourcenbezeichner \(ID\), der aus zwei Teilen besteht: einer Textzeichenfolge \(Symbolname\), die einem ganzzahligen Wert \(Symbolwert\) zugeordnet ist. Zum Beispiel:  
  
```  
IDC_EDITNAME = 5100  
```  
  
 Symbolnamen werden meistens als Bezeichner bezeichnet.  
  
 Symbole bieten eine anschauliche Möglichkeit, auf Ressourcen und Objekte der Benutzeroberfläche zu verweisen, sowohl im Quellcode als auch bei der Arbeit im Ressourcen\-Editor. Mithilfe des Dialogfelds [Ressourcensymbole](../windows/viewing-resource-symbols.md) können Symbole komfortabel an einem Ort angezeigt und bearbeitet werden.  
  
 Wenn Sie eine neue Ressource oder ein neues Ressourcenobjekt erstellen, stellt der [Ressourcen\-Editor](../mfc/resource-editors.md) einen Standardnamen für die Ressource bereit, z. B. `IDC_RADIO1`, und weist ihr einen Wert zu. Die Name\-plus\-Wert\-Definition wird in der Datei „Resource.h“ gespeichert.  
  
> [!NOTE]
>  Wenn Sie Ressourcen oder Ressourcenobjekte aus einer RC\-Datei in eine andere kopieren, ändert Visual C\+\+ möglicherweise den Symbolwert der übertragenen Ressource, oder den Symbolnamen und den Wert, um Konflikte mit Symbolnamen oder Werten in der vorhandenen Datei zu vermeiden.  
  
 In dem Maß, in dem Ihre Anwendung in Umfang und Komplexität wächst, wächst auch die Anzahl ihrer Ressourcen und Symbole. Das Nachverfolgen einer großen Zahl von Symbolen, die über verschiedene Dateien verteilt sind, kann schwierig sein. Das Dialogfeld [Ressourcensymbole](../windows/resource-symbols-dialog-box.md) vereinfacht die Symbolverwaltung, indem es ein zentrales Tool bereitstellt, das Ihnen folgende Möglichkeiten bietet:  
  
-   [Anzeigen von Ressourcensymbolen](../windows/viewing-resource-symbols.md)  
  
-   [Erstellen neuer Symbole](../windows/creating-new-symbols.md)  
  
-   [Ändern nicht zugewiesener Symbole](../windows/changing-unassigned-symbols.md)  
  
-   [Löschen nicht zugewiesener Symbole](../windows/deleting-unassigned-symbols.md)  
  
-   [Öffnen des Ressourcen\-Editors für ein bestimmtes Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md)  
  
-   [Ändern eines Symbols oder Symbolnamens \(ID\)](../windows/changing-a-symbol-or-symbol-name-id.md)  
  
-   [Ändern des numerischen Werts eines Symbols](../windows/changing-a-symbol-s-numeric-value.md)  
  
-   [Ändern der Namen von Symbolheaderdateien](../windows/changing-the-names-of-symbol-header-files.md)  
  
-   [Einschließen gemeinsam genutzter \(schreibgeschützter\) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md)  
  
-   [Anzeigen vordefinierter Symbol\-IDs](../windows/predefined-symbol-ids.md)  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [How to: Search for Symbols in Resources](../windows/how-to-search-for-symbols-in-resources.md)   
 [Resource Editors](../mfc/resource-editors.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)