---
title: Suchpfade für abhängige Dateien | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 577fc7e44bfff35cf7efdcff20dc4cdca1c7001e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380484"
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