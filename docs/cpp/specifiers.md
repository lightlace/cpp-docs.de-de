---
title: Spezifizierer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- declaration specifiers
- declarations, specifiers
- specifiers, in declarations
ms.assetid: 8b14e844-9880-4571-8779-28c8efe44633
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d9898dc6b918643aa8ca4ace34ce2e716344c57
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463488"
---
# <a name="specifiers"></a>Spezifizierer
In diesem Thema wird beschrieben, die *Decl-Specifiers* -Komponente (deklarationsspezifizierer) einer [Deklaration](declarations-and-definitions-cpp.md).  
  
 Die folgenden Platzhalter und Sprachschlüsselwörter sind Deklarationsbezeichner:  
  
 *Storage-Class-specifier*  
  
 *Typspezifizierer*  
  
 *Funktionsspezifizierer*  
  
 [friend](../cpp/friend-cpp.md)  
  
 [Typedef] ( [Typedef](http://msdn.microsod) `(` *extended-Decl-Modifier-Seq* `)`  
  
## <a name="remarks"></a>Hinweise  
 Die *Decl-Specifiers* Teil einer Deklaration ist die längste Sequenz von *Decl-Specifiers* , der als Typname, einschließlich der nicht den Zeiger oder verweismodifizierer erstellt werden können. Der Rest der Deklaration ist die *Deklarator*, der den eingeführten Namen enthält.  
  
 Die folgende Tabelle enthält vier Deklarationen und zeigt dann jede Deklaration des *Decl-Specifers* und *Deklarator* Komponente getrennt.  
  
|Deklaration|*Decl-specifiers*|`declarator`|  
|-----------------|------------------------|------------------|  
|`char *lpszAppName;`|**char**|`*lpszAppName`|  
|`typedef char * LPSTR;`|**char**|`*LPSTR`|  
|`const int func1();`|**const int**|`func1`|  
|`volatile void *pvvObj;`|**flüchtige "void"**|`*pvvObj`|  
  
 Da **signiert**, **ohne Vorzeichen**, **lange**, und **kurze** impliziert alle **Int**,  **TypeDef** name eines dieser Schlüsselwörter folgt, werden Sie Mitglied der *Declarator-List* nicht *Decl-Specifiers*.  
  
> [!NOTE]
>  Da ein Name neu deklariert werden kann, unterliegt seine Interpretation der letzten Deklaration im aktuellen Gültigkeitsbereich. Eine Neudeklaration kann beeinflussen, wie Namen insbesondere vom Compiler interpretiert werden **Typedef** Namen.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarationen und Definitionen](declarations-and-definitions-cpp.md)