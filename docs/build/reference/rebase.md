---
title: "/REBASE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/rebase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/REBASE editbin-Option [C++]"
  - "Basisadressen [C++]"
  - "DLLs [C++], Verknüpfen"
  - "Ausführbare Dateien [C++], Basisadresse"
  - "REBASE (editbin-Option)"
  - "-REBASE (editbin-Option)"
ms.assetid: 3f89d874-af5c-485b-974b-fd205f6e1a4b
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /REBASE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/REBASE[:modifiers]  
```  
  
## Hinweise  
 Durch diese Option werden die Basisadressen für die angegebenen Dateien festgelegt.  EDITBIN weist entsprechend der Größe der Dateien neue Basisadressen in einem zusammenhängenden Adressbereich zu und rundet auf die nächsten 64 KB auf.  Ausführliche Informationen über Basisadressen finden Sie unter der [\/\(BASE\) Basisadresse](../../build/reference/base-base-address.md)\-Linkeroption.  
  
 Geben Sie die ausführbaren Dateien und DLLs des Programms im *files*\-Argument der EDITBIN\-Befehlszeile in der Reihenfolge an, in der ihnen Basisadressen zugewiesen werden sollen.  Sie können einen oder mehrere durch Kommas \(**,**\) voneinander getrennte Modifizierer angeben:  
  
|Modifizierer|Aktion|  
|------------------|------------|  
|BASIS**\=***Adresse*|Enthält eine Startadresse für das erneute Zuweisen von Basisadressen zu den Dateien.  *Adresse* wird dezimal oder in C\-Notation angegeben.  Wenn **BASE** nicht angegeben ist, dann ist die Startbasisadresse standardmäßig 0x400000.  Wenn DOWN verwendet wird, muss BASE angegeben werden, wobei das Ende des Basisadressenbereichs durch *Adresse* festgelegt wird.|  
|BASEFILE|Erstellt eine Datei mit dem Namen **COFFBASE.TXT**. Dies ist eine Textdatei in dem von der **\/BASE**\-Linkeroption erwarteten Format.|  
|NACH\-OBEN|Weist EDITBIN an, die Basisadressen von der Endadresse absteigend erneut zuzuweisen.  Die Dateien werden in der angegebenen Reihenfolge erneut zugewiesen, wobei die erste Datei an der höchstmöglichen Adresse nach Ende des Adressbereichs angeordnet wird.  **BASE** muss zusammen mit **DOWN** verwendet werden, um sicherzustellen, dass ein ausreichender Adressbereich für das Zuweisen von Basisadressen vorhanden ist.  Um zu ermitteln, welcher Adressbereich von den angegebenen Dateien belegt wird, führen Sie für die Dateien EDITBIN mit **\/REBASE** aus und addieren zur angezeigten Gesamtgröße 64 KB.|  
  
## Siehe auch  
 [EDITBIN\-Optionen](../../build/reference/editbin-options.md)