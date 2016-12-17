---
title: "Zusammenfassung von Lebensdauer und Sichtbarkeit"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Lebensdauer, Und Sichtbarkeit"
  - "Sichtbarkeit, Bezeichner"
ms.assetid: ea05a253-7658-482c-9a6b-abd71169c42d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Zusammenfassung von Lebensdauer und Sichtbarkeit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Tabelle ist eine Zusammenfassung der Lebensdauer\- und Sichtbarkeitseigenschaften der meisten Bezeichner.  Die ersten drei Spalten geben die Attribute an, die die Lebensdauer und die Sichtbarkeit definieren.  Ein Bezeichner mit den Attributen, die durch die ersten drei Spalten angegeben sind, weist die Lebensdauer und Sichtbarkeit auf, die in der vierten und fünften Spalte angezeigt werden.  Allerdings deckt die Tabelle nicht alle möglichen Fälle ab.  Weitere Informationen erhalten Sie unter [Speicherklassen](../c-language/c-storage-classes.md).  
  
### Zusammenfassung von Lebensdauer und Sichtbarkeit  
  
|Attribute:<br /><br /> Ebene|Element|Speicherklasse<br /><br /> Bezeichner|Ergebnis:<br /><br /> Lebensdauer|Sichtbarkeit|  
|--------------------------|-------------|-----------------------------------|-------------------------------|------------------|  
|Dateibereich|Variablendefinition|**static**|Global|Rest der Quelldatei der Ausführung|  
||Variablendeklaration|`extern`|Global|Rest der Quelldatei der Ausführung|  
||Funktionsprototyp oder Definition|**static**|Global|Einzelne Quelldatei|  
||Funktionsprototyp|`extern`|Global|Rest der Quelldatei|  
|Blockbereich|Variablendeklaration|`extern`|Global|Block|  
||Variablendefinition|**static**|Global|Block|  
||Variablendefinition|**auto** oder **register**|Lokal|Block|  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel werden Blöcke, Verschachtelung und die Sichtbarkeit von Variablen veranschaulicht:  
  
### Code  
  
```  
// Lifetime_and_Visibility.c  
  
#include <stdio.h>  
  
int i = 1;  // i defined at external level  
  
int main()  // main function defined at external level  
{  
    printf_s( "%d\n", i ); // Prints 1 (value of external level i)  
    {                                 // Begin first nested block  
        int i = 2, j = 3;          // i and j defined at internal level  
        printf_s( "%d %d\n", i, j );  // Prints 2, 3  
        {                             // Begin second nested block  
            int i = 0;                // i is redefined  
            printf_s( "%d %d\n", i, j ); // Prints 0, 3  
        }                             // End of second nested block  
        printf_s( "%d\n", i );        // Prints 2 (outer definition  
                                      //  restored)  
    }                                 // End of first nested block  
    printf_s( "%d\n", i );            // Prints 1 (external level  
                                      // definition restored)  
    return 0;  
}   
```  
  
### Kommentare  
 In diesem Beispiel gibt es vier Sichtbarkeitsebenen: die externe Ebene und drei Blockebenen.  Die Werte werden auf dem Bildschirm gemäß den Kommentaren nach der jeweiligen Anweisung ausgegeben.  
  
## Siehe auch  
 [Lebensdauer, Bereich, Sichtbarkeit und Verknüpfung](../c-language/lifetime-scope-visibility-and-linkage.md)