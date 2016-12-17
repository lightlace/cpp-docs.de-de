---
title: "Symbol Name Restrictions"
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
  - "vc.editors.symbol.restrictions.name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
  - "restrictions, symbol names"
ms.assetid: 4ae7f695-ca86-4f4b-989a-fe6f89650ff7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Symbol Name Restrictions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Einschränkungen für Symbolnamen lauten wie folgt:  
  
-   Alle [Symbole](../mfc/symbols-resource-identifiers.md) müssen innerhalb des Anwendungsbereichs eindeutig sein.  Dadurch werden Symboldefinitionskonflikte in den Headerdateien verhindert.  
  
-   Zu den gültigen Zeichen für einen Symbolnamen zählen A–Z, a–z, 0–9 und Unterstriche \( – \).  
  
-   Symbolnamen dürfen nicht mit einer Zahl beginnen und sind auf 247 Zeichen begrenzt.  
  
-   Symbolnamen dürfen keine Leerzeichen enthalten.  
  
-   Bei Symbolnamen wird die Groß\-\/Kleinschreibung nicht beachtet. Die Groß\-\/Kleinschreibung der ersten Symboldefinition wird jedoch beibehalten.  Die die Symbole definierende Headerdatei wird durch den Ressourcencompiler\/Editor und durch das bzw. die C\+\+Programm\(e\) verwendet, um auf in einer Ressourcendatei definierte Ressourcen zu verweisen.  Bei zwei Symbolnamen, die sich nur in der Groß\-\/Kleinschreibung unterscheiden, erkennt das C\+\+\-Programm zwei getrennte Symbole, während der Ressourcencompiler\/Editor beide Namen als ein einzelnes Symbol erkennt.  
  
    > [!NOTE]
    >  Wenn Sie das im Folgenden hervorgehobene standardmäßige Symbolnamensschema \(ID\*\_\[keyword\]\) nicht befolgen und Ihr Symbolname dem Schlüsselwort entspricht, das dem Ressourcenskriptcompiler bekannt ist, führt der Versuch, die Ressourcenskriptdatei zu erstellen, anscheinend zu einer zufälligen Fehlergenerierung, die sich schwer diagnostizieren lässt.  Halten Sie sich an die standardmäßige Namensgebung, um dies zu verhindern.  
  
 Symbolnamen weisen beschreibende Präfixe auf, die die Art der Ressource oder des Objekts andeuten, die bzw. das sie repräsentieren.  Diese beschreibenden Präfixe beginnen mit der Textkombinations\-ID.  Die Microsoft Foundation Class\-Bibliothek \(MFC\) verwendet die in der folgenden Tabelle gezeigten Symbolnamenskonventionen.  
  
|Kategorie|Präfix|Verwenden|  
|---------------|------------|---------------|  
|Ressourcen|IDR\_ IDD\_ IDC\_ IDI\_ IDB\_|Zugriffstaste oder Menü \(sowie zugehörige oder benutzerdefinierte Ressourcen\), Dialogfeld, Cursor, Symbol, Bitmap|  
|Menüelemente|ID\_|Menüelement|  
|Befehle|ID\_|Befehl|  
|Steuerelemente und untergeordnete Fenster|IDC\_|Steuerelement|  
|Zeichenfolgen|IDS\_|Zeichenfolge in der Zeichenfolgentabelle|  
|MFC|AFX\_|Reserviert für vordefinierte MFC\-Symbole|  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Changing a Symbol or Symbol Name \(ID\)](../windows/changing-a-symbol-or-symbol-name-id.md)   
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)