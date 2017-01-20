---
title: "Linkertoolwarnung LNK4237"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4237"
ms.assetid: 87bfec39-5241-464f-9feb-517b49f352ea
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolwarnung LNK4237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\/SUBSYSTEM:NATIVE wurde beim Importieren von 'dll' angegeben. Verwenden Sie \/SUBSYSTEM:CONSOLE oder \/SUBSYSTEM:WINDOWS.  
  
 [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) wurde beim Erstellen einer Windows\-Anwendung \(Win32\) angegeben, die eine oder mehrere der folgenden DLLs direkt verwendet:  
  
-   kernel32.dll  
  
-   gdi32.dll  
  
-   user32.dll  
  
-   eine der msvcrt\*\-DLLs  
  
 Beheben Sie diese Warnung, indem Sie die Angabe **\/SUBSYSTEM:NATIVE** weglassen.