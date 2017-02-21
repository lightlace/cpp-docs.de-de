---
title: "Linkertoolfehler LNK2027 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2027"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2027"
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolfehler LNK2027
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Nicht aufgelöster Modulverweis 'Modul'  
  
 Eine an den Linker übergebene Datei ist abhängig von einem Modul, das weder mithilfe von **\/ASSEMBLYMODULE** angegeben noch direkt an den Linker übergeben wurde.  
  
 Führen Sie zur Behebung von LNK2027 einen der folgenden Schritte aus:  
  
-   Übergeben Sie die Datei mit der Modulabhängigkeit nicht an den Linker.  
  
-   Geben Sie das Modul mithilfe von **\/ASSEMBLYMODULE** an.  
  
-   Wenn das Modul ein Tresor .netmodule ist, übergeben Sie das Modul direkt an den Linker.  
  
 Weitere Informationen finden Sie unter [\/ASSEMBLYMODULE \(MSIL\-Modul zur Assembly hinzufügen\)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) und [.NETMODULE\-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).