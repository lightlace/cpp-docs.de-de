---
title: "Importieren mithilfe von DEF-Dateien"
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
helpviewer_keywords: 
  - "DEF-Dateien [C++], Importieren mit"
  - "DEF-Dateien [C++], Importieren mit"
  - "dllimport-Attribut [C++], DEF-Dateien"
  - "DLLs [C++], DEF-Dateien"
  - "Importieren von DLLs [C++], DEF-Dateien"
ms.assetid: aefdbf50-f603-488a-b0d7-ed737bae311d
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Importieren mithilfe von DEF-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie **\_\_declspec\(dllimport\)** zusammen mit einer DEF\-Datei verwenden möchten, sollten Sie die DEF\-Datei so ändern, dass DATA anstelle von CONSTANT verwendet wird. So wird das Risiko verringert, dass durch fehlerhaften Code Probleme entstehen:  
  
```  
// project.def  
LIBRARY project  
EXPORTS  
   ulDataInDll   DATA  
```  
  
 Die folgende Tabelle zeigt die Gründe auf:  
  
|Schlüsselwort|Ausgabe in Importbibliothek|Exportiert|  
|-------------------|---------------------------------|----------------|  
|`CONSTANT`|`_imp_ulDataInDll_ulDataInDll`|`_ulDataInDll`|  
|`DATA`|`_imp_ulDataInDll`|`_ulDataInDll`|  
  
 Bei Verwendung von **\_\_declspec\(dllimport\)** mit CONSTANT werden sowohl die `imp`\-Version als auch der nicht ergänzte Name in der für das explizite Verknüpfen erstellten DLL\-Importbibliothek \(.lib\) aufgelistet.  Bei Verwendung von **\_\_declspec\(dllimport\)** mit DATA wird nur die `imp`\-Version des Namens aufgelistet.  
  
 Wenn Sie CONSTANT verwenden, kann eines der beiden folgenden Codekonstrukte für den Zugriff auf `ulDataInDll` verwendet werden:  
  
```  
__declspec(dllimport) ULONG ulDataInDll; /*prototype*/  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 \- oder \-  
  
```  
ULONG *ulDataInDll;      /*prototype*/  
if (*ulDataInDll == 0L)  /*sample code fragment*/  
```  
  
 Wenn Sie jedoch DATA in der DEF\-Datei verwenden, kann nur über mit folgender Definition kompiliertem Code auf die Variable `ulDataInDll` zugegriffen werden:  
  
```  
__declspec(dllimport) ULONG ulDataInDll;  
  
if (ulDataInDll == 0L)   /*sample code fragment*/  
```  
  
 Die Verwendung von **CONSTANT** birgt zusätzliche Risiken: Falls Sie vergessen, die zusätzliche Ebene von Zeigeroperationen zu implementieren, wird u. U. auf den Zeiger in der Importadressentabelle zugegriffen, der auf die Variable verweist, und nicht auf die Variable selbst.  Solche Probleme treten häufig in Form von Zugriffsverletzungen auf, da die Importadressentabelle zu diesem Zeitpunkt vom Compiler und Linker mit einem Schreibschutz versehen wird.  
  
 Der aktuelle Visual C\+\+\-Linker gibt bei Vorhandensein von CONSTANT in der DEF\-Datei eine Warnung aus, um auf diesen Problemfall hinzuweisen.  Der einzige wirkliche Grund für die Verwendung von CONSTANT liegt vor, wenn Sie eine Objektdatei, in deren Headerdatei **\_\_declspec\(dllimport\)** für den Prototyp nicht aufgeführt ist, nicht neu kompilieren können.  
  
## Siehe auch  
 [Importieren in eine Anwendung](../build/importing-into-an-application.md)