---
title: "/volatile (Interpretation des volatile-Schl&#252;sselworts) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/volatile:iso"
  - "/volatile:ms"
  - "/volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/volatile (Compileroption)"
  - "/volatile (Compileroption) [C++]"
  - "volatile (Compileroption)"
  - "-volatile (Compileroption)"
  - "volatile (Compileroption) [C++]"
  - "-volatile (Compileroption) [C++]"
ms.assetid: 9d08fcc6-5bda-44c8-8151-8d8d54f164b8
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# /volatile (Interpretation des volatile-Schl&#252;sselworts)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt an, wie das [volatile](../../cpp/volatile-cpp.md)\-Schlüsselwort interpretiert werden soll.  
  
## Syntax  
  
```  
/volatile:{iso|ms}  
```  
  
## Argumente  
 **\/volatile:iso**  
 Wählt strenge `volatile`\-Semantik aus, wie vom ISO\-Standard für die C\+\+\-Sprache definiert.  Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen nicht garantiert.  Wenn der Compiler auf ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.  
  
 **\/volatile:ms**  
 Wählt erweiterte Microsoft\-`volatile`\-Semantik aus, mit der über den ISO\-Standard für die C\+\+\-Sprache hinausgehe Speicheranordnungsgarantien hinzufügt werden.  Semantiken zum Abrufen bzw. Freigeben sind bei flüchtigen Zugriffen garantiert.  Allerdings zwingt diese Option den Compiler auch zum Generieren von Hardwarearbeitsspeicherbarrieren, die möglicherweise beträchtlichen Mehraufwand für ARM und andere schwache Speicheranordnungsarchitekturen bedeuten.  Wenn der Compiler auf eine Plattform außer ARM ausgerichtet ist, ist dies die Standardinterpretation von `volatile`.  
  
## Hinweise  
 Es wird dringend empfohlen, dass Sie **\/volatile:iso** zusammen mit expliziten Synchronisierungsprimitiven und systeminternen Funktionen des Compilers verwenden, wenn Sie mit Speicherplatz arbeiten, der über Threads freigegeben wird.  Weitere Informationen finden Sie unter [volatile](../../cpp/volatile-cpp.md).  
  
 Wenn Sie vorhandenen Code portieren oder diese Option mitten in einem Projekt ändern, kann es hilfreich sein, die Warnung [C4746](../../error-messages/compiler-warnings/compiler-warning-c4746.md) zu aktivieren, um Codespeicherorte zu identifizieren, die von dem Unterschied in der Semantik beeinflusst werden.  
  
 Es gibt keine `#pragma`\-Entsprechung, zum Steuern dieser Option.  
  
### So legen Sie die \/volatile\-Compileroption in Visual Studio fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** für das Projekt.  Weitere Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Fügen Sie im Feld **Zusätzliche Optionen**`/volatile:iso` oder `/volatile:ms` hinzu.  
  
## Siehe auch  
 [volatile](../../cpp/volatile-cpp.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)