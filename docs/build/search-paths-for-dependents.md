---
title: Suchpfade für abhängige Dateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="search-paths-for-dependents"></a>Suchpfade für abhängige Dateien
Jede abhängige Datei besitzt einen optionalen Suchpfad, der wie folgt angegeben:  
  
## <a name="syntax"></a>Syntax  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>Hinweise  
 NMAKE sucht eine abhängige Datei zuerst im aktuellen Verzeichnis, und klicken Sie dann in den Verzeichnissen in der angegebenen Reihenfolge aus. Makros kann einem Suchpfad ganz oder teilweise angeben. Schließen Sie Verzeichnisnamen in der geschweiften Klammern ({}); Trennen Sie mehrere Verzeichnisse mit einem Semikolon (;). Es sind keine Leerzeichen oder Tabstopps zulässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Abhängige Dateien](../build/dependents.md)