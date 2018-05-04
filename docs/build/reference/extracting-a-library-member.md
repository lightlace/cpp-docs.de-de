---
title: Extrahieren eines Bibliothekmembers | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0dc0dc67a6d9e4a3ff61aa3b82ac10b9eabcb94b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="extracting-a-library-member"></a>Extrahieren eines Bibliothekmembers
Sie können LIB verwenden, um eine Objektdatei (obj) zu erstellen, die eine Kopie des Mitglied einer vorhandenen Bibliotheksfreigabe enthält. Verwenden Sie die folgende Syntax, um eine Kopie eines Elements zu extrahieren:  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 Dieser Befehl erstellt eine OBJ-Datei mit dem Namen *Objektdatei* , enthält eine Kopie einer `member` von einer *Bibliothek*. Die `member` Namen wird Groß-/Kleinschreibung beachtet. Sie können nur ein Element in einem einzigen Befehl extrahieren. Die Option/Out ist erforderlich. Es ist keine standardausgabename. Wenn eine Datei namens *Objektdatei* bereits im angegebenen Verzeichnis (das aktuelle Verzeichnis, wenn kein Verzeichnis angegeben wird oder *Objektdatei*), die extrahierte *Objektdatei*ersetzt die vorhandene Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [LIB-Referenz](../../build/reference/lib-reference.md)