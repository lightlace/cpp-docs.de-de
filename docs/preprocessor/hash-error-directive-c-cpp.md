---
title: '#Fehler-Direktive (C/C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- '#error'
dev_langs:
- C++
helpviewer_keywords:
- '#error directive'
- preprocessor, directives
- error directive (#error directive)
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e449da64b5221ccddee34dd850a987b28a2f39df
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="error-directive-cc"></a>#error-Anweisung (C/C++)
Die `#error`-Direktive gibt eine benutzerdefinierte Fehlermeldung zur Kompilierzeit aus und beendet dann die Kompilierung.  
  
## <a name="syntax"></a>Syntax  
  
```  
#errortoken-string  
```  
  
## <a name="remarks"></a>Hinweise  
 Die Fehlermeldung, die dieser Richtlinie ausgibt enthält die *-Token-String* Parameter. Der `token-string`-Parameter unterliegt nicht der Makroerweiterung. Diese Direktive ist während der Vorverarbeitung am hilfreichsten, denn sie informiert den Entwickler über eine Programminkonsistenz oder einen Verstoß gegen eine Einschränkung. Das folgende Beispiel zeigt die Fehlerverarbeitung während der Vorverarbeitung:  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Präprozessordirektiven](../preprocessor/preprocessor-directives.md)