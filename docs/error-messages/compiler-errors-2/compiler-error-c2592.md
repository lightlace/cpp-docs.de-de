---
title: "Compilerfehler C2592 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2592"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2592"
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2592
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

„Klasse“: „base\_class\_2“ wird von „base\_class\_1“ geerbt und kann nicht erneut angegeben werden.  
  
 Sie können nur Basisklassen angeben, die nicht von anderen Basisklassen erben.  In diesem Fall ist nur `base_class_1` in der Spezifikation von `class` erforderlich, da `base_class_1` bereits `base_class_2` erbt.