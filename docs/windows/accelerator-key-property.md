---
title: "Eigenschaft &quot;Taste&quot; von Zugriffstasten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Key-Eigenschaft"
ms.assetid: d1570cd9-b414-4cd6-96bd-47c38281eaca
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Eigenschaft &quot;Taste&quot; von Zugriffstasten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Einträge sind für die Eigenschaft **Taste** in der Zugriffstastentabelle zulässig:  
  
-   Eine ganze Zahl zwischen 0 und 255 im dezimalen Format.  Es wird wie folgt festgelegt, ob der Wert als ASCII\- oder als ANSI\-Wert behandelt wird:  
  
    -   Einstellige Zahlen werden nicht als ASCII\- oder ANSI\-Werte, sondern immer als die entsprechende Taste interpretiert.  
  
    -   Sofern Nullen vorangestellt sind, werden Werte von 1 bis 26 als ^A bis ^Z interpretiert. Diese Darstellung entspricht dem ASCII\-Wert der Buchstaben des Alphabets, wenn sie mit gedrückter STRG\-TASTE gedrückt werden.  
  
    -   Werte von 27 bis 32 werden immer als dreistellige Dezimalzahlen 027 bis 032 interpretiert.  
  
    -   Werte von 033 bis 255 werden nicht als ANSI\-Werte interpretiert, unabhängig davon, ob ihnen eine 0 vorangestellt ist oder nicht.  
  
-   Ein einzelnes Zeichen der Tastatur.  Die Großbuchstaben A \- Z oder die Ziffern 0 \- 9 können entweder ASCII\-Werte oder virtuelle Tastenwerte sein. Alle anderen Zeichen sind ausschließlich ASCII\-Werte.  
  
-   Ein einzelnes Zeichen der Tastatur im Bereich von A – Z \(nur Großbuchstaben\), dem ein Zirkumflexzeichen \(^\) vorangestellt ist \(z. B. ^C\).  Auf diese Weise wird der ASCII\-Wert der Taste eingegeben, wenn diese bei gleichzeitig gedrückter STRG\-TASTE gedrückt wird.  
  
    > [!NOTE]
    >  Bei der Eingabe eines ASCII\-Werts sind für die Modifizierer\-Eigenschaft weniger Optionen verfügbar.  Als einzige Steuerungstaste ist die ALT\-TASTE verfügbar.  
  
-   Beliebige gültige Bezeichner für virtuelle Tasten.  Das Dropdownfeld **Taste** in der Zugriffstastentabelle enthält eine Liste von Standardbezeichnern für virtuelle Tasten.  
  
    > [!TIP]
    >  Eine andere Möglichkeit zum Definieren einer Zugriffstaste besteht darin, mit der rechten Maustaste auf einen oder mehrere Einträge in der Zugriffstastentabelle zu klicken, aus dem Kontextmenü den Befehl **Nächste Taste** auszuwählen und dann beliebige Tasten oder Tastenkombinationen auf der Tastatur zu drücken.  Der Befehl **Nächste Taste** ist auch im Menü **Bearbeiten** verfügbar.  
  
## Anforderungen  
 Win32  
  
## Siehe auch  
 [Setting Accelerator Properties](../windows/setting-accelerator-properties.md)   
 [Editing in an Accelerator Table](../windows/editing-in-an-accelerator-table.md)   
 [Accelerator Editor](../mfc/accelerator-editor.md)