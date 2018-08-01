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
ms.openlocfilehash: bee63ace276863a30c4ec81d970ba3bf5fd29e40
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405284"
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
|*identifier*|Der Bezeichner, dessen Vorhandensein Sie überprüfen möchten.|  
|*Anweisungen*|Eine oder mehrere Anweisungen ausgeführt wird, wenn *Bezeichner* ist nicht vorhanden.|  
  
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