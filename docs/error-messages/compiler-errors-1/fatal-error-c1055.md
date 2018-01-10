---
title: Schwerwiegender Fehler C1055 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1055
dev_langs: C++
helpviewer_keywords: C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfdd971dfcb5c762346a8d1f59452f31826db296
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1055"></a>Schwerwiegender Fehler C1055
Compilerlimit: keine weiteren Schlüssel  
  
 Die Quelldatei enthält zu viele Symbole. Der Compiler war nicht genügend Hashschlüssel für die Symboltabelle.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>So beheben Sie den Fehler (unterschiedliche Lösungsmöglichkeiten)  
  
1.  Teilen Sie die Quelldatei in kleinere Dateien.  
  
2.  Vermeiden Sie unnötige Headerdateien.  
  
3.  Wiederverwenden von temporären und globale Variablen statt neue zu erstellen.