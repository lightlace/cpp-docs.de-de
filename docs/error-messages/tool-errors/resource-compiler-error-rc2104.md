---
title: "Ressourcencompiler: Fehler RC2104 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2104"
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Ressourcencompiler: Fehler RC2104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Undefiniertes Schlüsselwort oder Schlüsselname: Schlüssel  
  
 Das angegebene Schlüsselwort oder der Schlüsselname ist nicht definiert.  
  
 Dieser Fehler wird häufig durch einen Tippfehler in die Definition der Ressource oder in der zugehörigen Header\-Datei verursacht.  Er kann auch durch eine fehlende Headerdatei verursacht werden.  
  
 Um das Problem zu beheben, suchen Sie die Header\-Datei, die das definierte Schlüsselwort oder den Schlüsselnamen enthält und stellen Sie sicher, dass er in Ihrer Ressourcendatei enthalten ist und dass das Schlüsselwort oder der Schlüsselname richtig geschrieben ist.  Wenn das Projekt mit einem vorkompilierten Header erstellt wurde und Sie es anschließend entfernen, stellen Sie sicher, dass die Ressourcendatei erforderliche Header enthält.  
  
 Überprüfen Sie die definierten Schlüsselwörter und Schlüsselnamen in die Ressourcendatei in Visual Studio, öffnen Sie das Fenster **Ressourcenansicht** – Wählen Sie in der Menüleiste **Ansicht**, **Ressourcenansicht** – öffnen Sie das Kontextmenü für die .rc\-Datei und wählen Sie **Ressourcensymbole**, um die Liste der definierten Symbole anzuzeigen.  Um die enthaltenen Header zu ändern, öffnen Sie das Kontextmenü für die .rc\-Datei, und wählen Sie **Ressource enthält**.  
  
 Wenn Sie diese Meldung erhalten:  
  
```  
undefined keyword or key name: MFT_STRING   
```  
  
 Öffnen Sie \\MCL\\MFC\\Include\\AfxRes.h, und fügen Sie diese Eingüge\-Direktive ein:  
  
```  
#include <winresrc.h>  
```