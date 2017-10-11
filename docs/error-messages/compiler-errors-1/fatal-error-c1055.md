---
title: Schwerwiegender Fehler C1055 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1055
dev_langs:
- C++
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 68b9dc5ac8a574111a678086a03e2760941e766f
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1055"></a>Schwerwiegender Fehler C1055
Compilerlimit: keine weiteren Schlüssel  
  
 Die Quelldatei enthält zu viele Symbole. Der Compiler war nicht genügend Hashschlüssel für die Symboltabelle.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Teilen Sie die Quelldatei in kleinere Dateien.  
  
2.  Vermeiden Sie unnötige Headerdateien.  
  
3.  Wiederverwenden von temporären und globale Variablen statt neue zu erstellen.
