---
title: "EDITBIN-Referenz | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "editbin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Binäre Daten, Bearbeiten"
  - "COFF-Dateien, Bearbeiten"
  - "EDITBIN (Programm)"
  - "Objektdateien, Ändern"
ms.assetid: efdda03b-3dfc-4d31-90e6-caf5b3977914
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# EDITBIN-Referenz
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Der COFF\-Binärdatei\-Editor von Microsoft \(EDITBIN.EXE\) bearbeitet Binärdateien im COFF\-Format \(Common Object File Format\).  Mit EDITBIN können Sie Objektdateien, ausführbare Dateien und DLLs \(Dynamic Link Libraries\) ändern.  
  
> [!NOTE]
>  Sie können dieses Tool nur von der [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]\-Eingabeaufforderung aus starten.  Sie können es nicht von einer Systemeingabeaufforderung oder vom Datei\-Explorer aus starten.  
  
 EDITBIN kann nicht für Dateien verwendet werden, die mit der [\/GL](../../build/reference/gl-whole-program-optimization.md)\-Compileroption erstellt wurden.  Änderungen an mit \/GL erstellten Binärdateien werden durch die Neukompilierung und Verknüpfung vorgenommen.  
  
-   [EDITBIN\-Befehlszeile](../../build/reference/editbin-command-line.md)  
  
-   [EDITBIN\-Optionen](../../build/reference/editbin-options.md)  
  
## Siehe auch  
 [C\/C\+\+\-Buildtools](../../build/reference/c-cpp-build-tools.md)