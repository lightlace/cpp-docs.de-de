---
title: "/Fi (Ausgabedateiname vorverarbeiten) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/Fi"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Fi-Compileroption [C++]"
  - "Fi-Compileroption [C++]"
  - "-Fi-Compileroption [C++]"
  - "Vorverarbeiten von Ausgabedateien, Dateiname"
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# /Fi (Ausgabedateiname vorverarbeiten)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt den Namen der Ausgabedatei an, in die die [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md)\-Compileroption die vorverarbeitete Ausgabe schreibt.  
  
## Syntax  
  
```  
/Fipathname  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`pathname`|Der Name und Pfad der Ausgabedatei, die von der **\/P**\-Compileroption erstellt wurde.|  
  
## Hinweise  
 Verwenden Sie die **\/Fi**\-Compileroption zusammen mit der **\/P**\-Compileroption.  
  
 Wenn Sie nur einen Pfad für den `pathname`\-Parameter angeben, wird der Basisname der Quelldatei als Basisname der vorverarbeiteten Ausgabedatei verwendet.  Der `pathname`\-Parameter erfordert keine bestimmte Dateinamenerweiterung.  Falls Sie keine Dateinamenerweiterungen angeben, wird eine I\-Erweiterung verwendet.  
  
## Beispiel  
 Mit der folgenden Befehlszeile werden eine Vorverarbeitung von PROGRAM.cpp durchgeführt, die Kommentare übernommen, [\#line](../../preprocessor/hash-line-directive-c-cpp.md)\-Direktiven hinzugefügt und das Ergebnis in die Datei "MYPROCESS.i" geschrieben:  
  
```  
CL /P /FiMYPROCESS.I PROGRAM.CPP  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)