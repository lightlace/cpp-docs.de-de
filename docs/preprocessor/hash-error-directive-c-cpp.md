---
title: '#Fehler-Direktive (C/C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ba4f0e06798bc6419f8db0471f19588039eb679a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33905571"
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