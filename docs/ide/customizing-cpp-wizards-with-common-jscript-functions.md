---
title: "Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen"
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
  - "JScript-Methoden (Assistent), Erstellen von C++-Assistenten"
ms.assetid: c602978f-a2c4-462f-85c3-50b5897bec46
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Anpassen von C++-Assistenten mit allgemeinen JScript-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein Assistentenprojekt mit dem [benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md) erstellen, enthält das Projekt die Datei Common.js.  Wenn Sie festlegen, dass der Assistent eine Benutzeroberfläche besitzt, enthält das Projekt außerdem HTML\-Seiten, in denen die Skriptsprache JScript angegeben und die Datei Common.js eingeschlossen ist. Siehe folgendes Beispiel:  
  
```  
<SCRIPT ID="INCLUDE_COMMON" LANGUAGE ="JSCRIPT"></SCRIPT>  
```  
  
 Darüber hinaus erstellt der Assistent die spezifische Datei Default.js.  Sie können Ihre eigenen JScript\-Funktionen in Default.js anpassen.  Weitere Informationen finden Sie unter [JScript\-Datei](../ide/jscript-file.md).  
  
 Common.js enthält Funktionen, die Sie von den HTML\-Seiten der einzelnen Assistenten sowie von Default.js aufrufen können.  Wenn Sie in verschiedenen Assistenten identische Funktionen verwenden möchten, können Sie diese in Common.js ablegen.  
  
## Siehe auch  
 [JScript\-Funktionen für C\+\+\-Assistenten](../ide/jscript-functions-for-cpp-wizards.md)   
 [Erstellen eines benutzerdefinierten Assistenten](../ide/creating-a-custom-wizard.md)   
 [Entwerfen eines Assistenten](../ide/designing-a-wizard.md)