---
title: "Suchpfade für abhängige Dateien | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf777c89c78ab844b61138c30a5a9a25ca6b91d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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