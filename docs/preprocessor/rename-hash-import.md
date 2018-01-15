---
title: Umbenennen (#import) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Rename
dev_langs: C++
helpviewer_keywords: rename attribute
ms.assetid: 5c5c6153-1087-4b7b-87fb-fc59b90b9975
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fe5efd48867d5911a6512c32c3e91d80201d03ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="rename-import"></a>rename (#import)
**C++-spezifisch**  
  
 Umgeht Probleme mit Namenskonflikten.  
  
## <a name="syntax"></a>Syntax  
  
```  
rename("OldName","NewName")  
```  
  
#### <a name="parameters"></a>Parameter  
 `OldName`  
 Alter Name in der Typbibliothek.  
  
 `NewName`  
 Name, der anstelle des alten Namens verwendet werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Wenn dieses Attribut angegeben wird, ersetzt der Compiler alle Vorkommen von *OldName* in eine Typbibliothek mit den vom Benutzer bereitgestellten *NewName* in den resultierenden Headerdateien.  
  
 Dieses Attribut kann verwendet werden, wenn ein Name in der Typbibliothek einer Makrodefinition in den Systemheaderdateien entspricht. Wenn dieses Problem nicht gelöst wird, verschiedene Syntaxfehler generiert werden, z. B. [Compilerfehler C2059](../error-messages/compiler-errors-1/compiler-error-c2059.md) und [Compiler Fehler C2061](../error-messages/compiler-errors-1/compiler-error-c2061.md).  
  
> [!NOTE]
>  Die Ersetzung erfolgt für einen in der Typbibliothek verwendeten, nicht für einen in der resultierenden Headerdatei verwendeten Namen.  
  
 Angenommen, eine Eigenschaft mit dem Namen `MyParent` ist in einer Typbibliothek vorhanden und das Makro `GetMyParent` wird in einer Headerdatei definiert und vor `#import` verwendet. Da `GetMyParent` der Standardname einer Wrapperfunktion für die Fehlerbehandlung **abrufen** -Eigenschaft, ein Konflikt von geschachteltem Klassennamen erfolgt. Um das Problem zu umgehen, verwenden Sie das folgende Attribut in der `#import`-Anweisung:  
  
```  
rename("MyParent","MyParentX")  
```  
  
 das den Namen `MyParent` in der Typbibliothek umbenennt. Bei dem Versuch, den Wrappernamen `GetMyParent` umzubenennen, tritt ein Fehler auf:  
  
```  
rename("GetMyParent","GetMyParentX")  
```  
  
 Dies ist darauf zurückzuführen, dass der Name `GetMyParent` nur in der resultierenden Typbibliotheksheaderdatei auftritt.  
  
 **Ende C++-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)   
 [#import-Direktive](../preprocessor/hash-import-directive-cpp.md)