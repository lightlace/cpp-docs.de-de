---
title: "Compilerwarnung (Stufe 4) C4513 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4513"
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Destruktor konnte nicht generiert werden  
  
 Der Compiler kann für die angegebene Klasse keinen Standarddestruktor erzeugen; es wurde kein Destruktor erstellt.  Der Destruktor befindet sich in einer Basisklasse, auf die von der abgeleiteten Klasse nicht zugegriffen werden kann.  Wenn die Basisklasse einen `private`\-Destruktor hat, deklarieren Sie ihn als **public** oder `protected`.