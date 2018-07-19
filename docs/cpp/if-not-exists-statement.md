---
title: __if_not_exists-Anweisung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37148a3849e859d7ca77595416616cfa0b952ecf
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939948"
---
# <a name="ifnotexists-statement"></a>__if_not_exists-Anweisung
Die **__if_not_exists** -Anweisung testet, ob der angegebene Bezeichner vorhanden ist. Wenn der Bezeichner nicht vorhanden ist, wird der angegebene Anweisungsblock ausgeführt.  
  
## <a name="syntax"></a>Syntax  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`identifier`|Der Bezeichner, dessen Vorhandensein Sie überprüfen möchten.|  
|`statements`|Eine oder mehrere Anweisungen ausgeführt wird, wenn `identifier` ist nicht vorhanden.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Um die zuverlässigsten Ergebnisse zu erzielen, verwenden die **__if_not_exists** Anweisung unter den folgenden Einschränkungen.  
  
-   Anwenden der **__if_not_exists** -Anweisung nur einfache Typen, die nicht durch Vorlagen.  
  
-   Anwenden der **__if_not_exists** -Anweisung auf Bezeichner innerhalb oder außerhalb einer Klasse. Wenden Sie keine der **__if_not_exists** Anweisung, um lokale Variablen.  
  
-   Verwenden der **__if_not_exists** Anweisung nur im Text einer Funktion. Außerhalb des Texts einer Funktion die **__if_not_exists** -Anweisung kann nur vollständig definierte Typen testen.  
  
-   Wenn Sie auf überladene Funktionen testen, können Sie nicht auf eine bestimmte Form der Überladung testen.  
  
 Die Ergänzung der **__if_not_exists** -Anweisung ist die [__if_exists](../cpp/if-exists-statement.md) Anweisung.  
  
## <a name="example"></a>Beispiel  
 Ein Beispiel zur Verwendung von **__if_not_exists**, finden Sie unter [__if_exists-Anweisung](../cpp/if-exists-statement.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Auswahlanweisungen](../cpp/selection-statements-cpp.md)   
 [Stichwörter](../cpp/keywords-cpp.md)   
 [__if_exists-Anweisung](../cpp/if-exists-statement.md)