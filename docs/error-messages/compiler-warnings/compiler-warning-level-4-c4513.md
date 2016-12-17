---
title: "Compilerwarnung (Stufe 4) C4513"
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
  - "C4513"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4513"
ms.assetid: 6877334a-f30a-4184-9483-dac3348737a4
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4513
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Klasse': Destruktor konnte nicht generiert werden  
  
 Der Compiler kann für die angegebene Klasse keinen Standarddestruktor erzeugen; es wurde kein Destruktor erstellt.  Der Destruktor befindet sich in einer Basisklasse, auf die von der abgeleiteten Klasse nicht zugegriffen werden kann.  Wenn die Basisklasse einen `private`\-Destruktor hat, deklarieren Sie ihn als **public** oder `protected`.