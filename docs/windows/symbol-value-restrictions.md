---
title: "Symbol Value Restrictions"
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
  - "vc.editors.symbol.restrictions.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, value restrictions"
  - "restrictions, symbol values"
ms.assetid: 32467ec3-690b-4cd0-a4d0-7d189a3296cb
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Symbol Value Restrictions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei einem Symbolwert kann es sich um eine beliebige Ganzzahl handeln, die in normaler Form für „\#define preprocessor“\-Direktiven ausgedrückt wird.  Hier sind einige Beispiele für Symbolwerte:  
  
```  
18  
4001  
0x0012  
-3456  
```  
  
 Bei Symbolwerten für Ressourcen \(Zugriffstaste, Bitmaps, Cursor, Dialogfelder, Symbole, Menüs, Zeichenfolgentabellen und Versionsinformationen\) muss es sich um Dezimalzahlen im Bereich von 0 bis 32.767 handeln \(darf nicht hexadezimal sein\).  Symbolwerte für Ressourcenbestandteile wie Dialogfeldsteuerelemente oder einzelne Zeichenfolgen in der Zeichenfolgentabelle können von 0 bis 65.534 oder von \-32.768 bis 32.767 reichen.  
  
 Bei Ressourcensymbolen handelt es sich um 16\-Bit\-Zahlen.  Sie können sie signiert oder nicht signiert eingeben. Sie werden jedoch intern als nicht signierte Ganzzahlen verwendet.  Negative Zahlen werden demnach in ihre entsprechenden positiven Werte umgewandelt.  
  
 Im Folgenden finden Sie einige Beschränkungen für Symbolwerte:  
  
-   Die Visual Studio\-Entwicklungsumgebung und MFC verwenden einige Zahlenbereiche für besondere Zwecke.  Alle Zahlen mit dem wichtigsten Bitset \(\-32.768 bis \-1 oder 32.768 bis 65.534 in Abhängigkeit des Zeichens\) sind für MFC reserviert.  
  
-   Es ist nicht möglich, einen Symbolwert mithilfe von anderen Symbolzeichenfolgen zu definieren.  Beispielsweise wird die folgende Symboldefinition nicht unterstützt:  
  
    ```  
    #define IDC_MYEDIT  IDC_OTHEREDIT  //not supported  
    ```  
  
-   Sie können Präprozessormakros mit Argumenten nicht als Wertdefinitionen verwenden.  Zum Beispiel:  
  
    ```  
    #define   IDD_ABOUT  ID(7) //not supported  
    ```  
  
     Ist kein gültiger Ausdruck, unabhängig davon, was `ID` zum Zeitpunkt der Kompilierung auswertet.  
  
-   Ihre Anwendung verfügt möglicherweise über eine vorhandene Datei, die mit Ausdrücken definierte Symbole enthält.  Weitere Informationen über das Einbeziehen der Symbole als schreibgeschützte Symbole finden Sie unter [Verwenden gemeinsam genutzter \(schreibgeschützter\) oder berechneter Symbole](../windows/including-shared-read-only-or-calculated-symbols.md).  
  
 Weitere Informationen über Zahlenbereiche finden Sie unter [TN023: MFC\-Standardressourcen](../mfc/tn023-standard-mfc-resources.md).  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Changing a Symbol's Numeric Value](../windows/changing-a-symbol-s-numeric-value.md)   
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)