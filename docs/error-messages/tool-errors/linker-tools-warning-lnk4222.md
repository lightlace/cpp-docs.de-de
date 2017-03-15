---
title: "Linkertoolwarnung LNK4222 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4222"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4222"
ms.assetid: b7bb1794-41fb-4c83-b9b0-59c0d786a7da
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Linkertoolwarnung LNK4222
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dem exportierten Symbol 'Symbol' sollte keine Ordinalzahl zugewiesen sein  
  
 Die folgenden Symbole sollten nicht anhand der Ordinalzahl exportiert werden:  
  
-   `DllCanUnloadNow`  
  
-   `DllGetClassObject`  
  
-   `DllGetClassFactoryFromClassString`  
  
-   `DllInstall`  
  
-   `DllRegisterServer`  
  
-   `DllRegisterServerEx`  
  
-   `DllUnregisterServer`  
  
 Diese Funktionen werden unter Verwendung von `GetProcAddress` immer anhand ihres Namens gesucht.  In dieser Situation wird eine Linkerwarnung ausgegeben, da die Anwendung durch diesen Exporttyp vergrößert werden könnte.  Dies ist z. B. der Fall, wenn der anhand der Ordinalzahl durchgeführte Export einen großen Bereich, aber relativ wenige Objekte umfasst.  Beispiel:  
  
```  
EXPORTS  
   DllGetClassObject   @1  
   MyOtherAPI      @100  
```  
  
 Die vorangehenden Codezeilen erfordern 100 Umsetzungsplätze in der Exportadressentabelle, wobei 98 davon \(2\-99\) lediglich als Füllzeichen dienen.  Die folgenden Zeilen  
  
```  
EXPORTS  
   DllGetClassObject  
   MyOtherAPI      @100  
```  
  
 erfordern jedoch nur zwei Umsetzungsplätze. \(Beachten Sie, dass auch mit der [\/EXPORT](../../build/reference/export-exports-a-function.md)\-Linkeroption exportiert werden kann.\)