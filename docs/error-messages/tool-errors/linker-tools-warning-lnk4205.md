---
title: "Linkertoolwarnung LNK4205 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK4205"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4205"
ms.assetid: d63b9d18-ef3c-4081-9d8d-93077dad13c2
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Linkertoolwarnung LNK4205
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Für 'Dateiname' fehlen aktuelle Debuginformationen für das Verweismodul; Objekt wird verknüpft, als ob keine Debuginformationen vorhanden wären  
  
 Die Informationen in der PDB\-Datei sind nicht mehr aktuell.  Der Linker verknüpft das Objekt ohne Debuginformationen.  Sie können das Objekt auch mit der [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option neu kompilieren.