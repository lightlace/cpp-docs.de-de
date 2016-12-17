---
title: "Including Shared (Read-Only) or Calculated Symbols"
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
  - "vc.editors.symbol.shared.calculated"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, read-only"
  - "symbols, shared"
  - "symbols, calculated"
  - "read-only symbols"
  - "symbol directives"
  - "calculated symbols"
  - "shared symbols"
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Including Shared (Read-Only) or Calculated Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die Entwicklungsumgebung erstmals eine durch eine andere Anwendung erstellte Ressourcendatei liest, markiert sie alle einbezogenen Headerdateien als schreibgeschützt.  Anschließend können Sie das Dialogfeld [Ressourcenincludes](../windows/resource-includes-dialog-box.md) verwenden, um zusätzliche schreibgeschützte Symbolheaderdateien hinzuzufügen.  
  
 Ein Grund, weshalb Sie möglicherweise schreibgeschützte Symboldefinitionen verwenden möchten, ist der Plan, Symboldateien unter verschiedenen Projekten freizugeben.  
  
 Sie können zudem einbezogene Symboldateien verwenden, wenn Sie über vorhandene Ressourcen mit Symboldefinitionen verfügen, die anstelle von einfachen Ganzzahlen Ausdrücke zum Definieren des Symbolwerts verwenden.  Zum Beispiel:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 Die Umgebung interpretiert diese berechneten Symbole ordnungsgemäß, sofern Folgendes gegeben ist:  
  
-   Die berechneten Symbole sind in einer schreibgeschützten Symboldatei platziert.  
  
-   Ihre Ressourcendatei enthält Ressourcen, zu denen diese berechneten Symbole bereits zugewiesen sind.  
  
-   Es wird ein numerischer Ausdruck erwartet.  
  
> [!NOTE]
>  Wenn eine Zeichenfolge oder ein numerischer Ausdruck erwartet wird, wird der Ausdruck nicht ausgewertet.  
  
### So beziehen Sie freigegebene \(schreibgeschützte\) Symbole in Ihrer Ressourcendatei ein  
  
1.  Klicken Sie mit der rechten Maustaste in der [Ressourcenansicht](../windows/resource-view-window.md) auf die RC\-Datei, und wählen Sie [Ressourcenincludes](../windows/resource-includes-dialog-box.md) aus dem Kontextmenü.  
  
    > [!NOTE]
    >  Wenn das Projekt noch keine RC\-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Verwenden Sie im Feld **Direktiven für schreibgeschützte Symbole** die Compilerdirektive **\#include**, um die Datei anzugeben, in der die schreibgeschützten Symbole beibehalten werden sollen.  
  
     Rufen Sie nicht die Datei „Resource.h“ auf. Hierbei handelt es sich nämlich für gewöhnlich um den Dateinamen, der durch die Hauptsymbol\-Headerdatei verwendet wird.  
  
    > [!NOTE]
    >  **Wichtig**: Was Sie im Feld „Direktiven für schreibgeschützte Symbole“ eingeben, wird genau so in der Ressourcendatei einbezogen, wie Sie es eingeben.  Stellen Sie sicher, dass die Eingabe weder Schreib\- noch Syntaxfehler aufweist.  
  
     Verwenden Sie das Feld **Direktiven für schreibgeschützte Symbole**, um nur Dateien mit Symboldefinitionen einzubeziehen.  Beziehen Sie keine Ressourcendefinitionen ein. Ansonsten werden doppelte Ressourcendefinitionen erstellt, wenn die Datei gespeichert wird.  
  
3.  Platzieren Sie die Symbole in der von Ihnen angegebenen Datei.  
  
     Die auf diese Weise in die Dateien einbezogenen Symbole werden ausgewertet, sobald Sie Ihre Ressourcendatei öffnen. Sie werden jedoch nicht auf dem Datenträger ersetzt, wenn Sie Ihre Datei speichern.  
  
4.  Klicken Sie auf **OK**.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Anforderungen  
  
 Win32  
  
## Siehe auch  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Symbol Value Restrictions](../windows/symbol-value-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)