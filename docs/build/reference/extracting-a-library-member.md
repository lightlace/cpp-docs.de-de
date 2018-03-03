---
title: Extrahieren eines Bibliothekmembers | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38f45463bb76f858d1b88c059de57a4b8b86227e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="extracting-a-library-member"></a>Extrahieren eines Bibliothekmembers
Sie können LIB verwenden, um eine Objektdatei (obj) zu erstellen, die eine Kopie des Mitglied einer vorhandenen Bibliotheksfreigabe enthält. Verwenden Sie die folgende Syntax, um eine Kopie eines Elements zu extrahieren:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Dieser Befehl erstellt eine OBJ-Datei mit dem Namen *Objektdatei* , enthält eine Kopie einer `member` von einer *Bibliothek*. Die `member` Namen wird Groß-/Kleinschreibung beachtet. Sie können nur ein Element in einem einzigen Befehl extrahieren. Die Option/Out ist erforderlich. Es ist keine standardausgabename. Wenn eine Datei namens *Objektdatei* bereits im angegebenen Verzeichnis (das aktuelle Verzeichnis, wenn kein Verzeichnis angegeben wird oder *Objektdatei*), die extrahierte *Objektdatei*ersetzt die vorhandene Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)