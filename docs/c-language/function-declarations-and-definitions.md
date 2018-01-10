---
title: Funktionsdeklarationen und -definitionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 65be3d2e59a9d672db18ba332d608fdf031f16e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="function-declarations-and-definitions"></a>Funktionsdeklarationen und -definitionen
Funktionsprototypen legen den Namen der Funktion, des Rückgabetyps und des Typs und der Anzahl von formalen Parametern fest. Eine Funktionsdefinition enthält den Funktionsrumpf.  
  
## <a name="remarks"></a>Hinweise  
 Funktions- und Variablendeklarationen können innerhalb oder außerhalb einer Funktionsdefinition angezeigt werden. Jede Deklaration innerhalb einer Funktionsdefinition wird auf "interner" oder "lokaler" Ebene angezeigt. Eine Deklaration außerhalb aller Funktionsdefinitionen wird auf "externer", globaler" oder auf Ebene des "Dateigültigkeitsbereichs" angezeigt. Variable Definitionen, wie Deklarationen, können auf der internen Ebene (innerhalb einer Funktionsdefinition) oder auf der externen Ebene angezeigt (außerhalb aller Funktionsdefinitionen) werden. Funktionsdefinitionen treten immer auf der externen Ebene auf. Funktionsdefinitionen werden unter [Funktionsdefinitionen](../c-language/c-function-definitions.md) näher erläutert. Funktionsprototypen werden unter [Funktionsprototypen](../c-language/function-prototypes.md) behandelt.  
  
## <a name="see-also"></a>Siehe auch  
 [Quelldateien und Quellprogramme](../c-language/source-files-and-source-programs.md)