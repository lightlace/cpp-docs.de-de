---
title: "Linkertoolwarnung LNK4197 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4197"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4197"
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Linkertoolwarnung LNK4197
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Export 'Exportname' wurde mehrmals festgelegt; erste Angabe wird verwendet  
  
 Ein Export wurde mehrfach und auf unterschiedliche Weise definiert.  Von allen Angaben berücksichtigt der Linker lediglich die erste.  
  
 Wenn Sie die C\-Laufzeitbibliothek neu erstellen, können Sie diese Meldung ignorieren.  
  
 Wenn ein Export mehrmals in genau derselben Weise angegeben wird, generiert der Linker keine Warnung.  
  
 Durch eine DEF\-Datei mit folgendem Inhalt wird diese Warnung generiert:  
  
```  
EXPORTS  
   functioname      NONAME  
   functioname      @10  
```  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  In der Befehlszeile \(durch **export:**\) und in der DEF\-Datei wird derselbe Export angegeben.  
  
2.  Derselbe Export ist in der DEF\-Datei zweimal mit unterschiedlichen Attributen aufgeführt.