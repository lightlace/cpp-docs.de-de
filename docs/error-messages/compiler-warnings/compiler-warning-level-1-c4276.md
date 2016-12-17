---
title: "Compilerwarnung (Stufe 1) C4276"
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
  - "C4276"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4276"
ms.assetid: 9d738c2d-29e5-408a-b9ff-be1a850b2238
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4276
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion': Kein Prototyp gegeben; Annahme: keine Parameter  
  
 Wenn Sie die Adresse einer Funktion mit der Aufrufkonvention [\_\_stdcall](../../cpp/stdcall.md) verwenden, müssen Sie einen Prototyp so angeben, dass der Compiler den ergänzten Namen der Funktion erstellen kann.  Da die *Funktion* keinen Prototyp besitzt, geht der Compiler beim Erstellen des ergänzten Namens davon aus, dass die Funktion keine Parameter enthält.