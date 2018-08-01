---
title: Verbundanweisungen (Blöcke) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '}'
- '{'
dev_langs:
- C++
helpviewer_keywords:
- blocks, about blocks
- compound statements
ms.assetid: 23855939-7430-498e-8936-0c70055ea701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c85de0f147d0cfed873a091d17c46e56bf5758a9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408795"
---
# <a name="compound-statements-blocks"></a>Verbundanweisungen (Blöcke)
Eine verbundanweisung besteht aus null oder mehr Anweisungen, die in geschweiften Klammern (**{}**). Einer Verbundanweisung kann an einer jeder beliebigen Stelle, an der eine Anweisung erwartet wird. Verbundanweisungen werden im Allgemeinen "Blöcke" genannt.  
  
## <a name="syntax"></a>Syntax  
  
```  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Hinweise  
 Im folgenden Beispiel wird eine verbundanweisung als den *Anweisung* Teil der **Wenn** Anweisung (finden Sie unter [If Anweisung](../cpp/if-else-statement-cpp.md) Details zur Syntax):  
  
```cpp 
if( Amount > 100 )  
{  
    cout << "Amount was too large to handle\n";  
    Alert();  
}  
else  
{
    Balance -= Amount;  
}
```  
  
> [!NOTE]
>  Da eine Deklaration eine Anweisung ist, eine Deklaration kann eine der Anweisungen in der *Anweisungsliste*. Folglich verfügen Namen, die innerhalb einer Verbundanweisung deklariert werden, jedoch nicht explizit als statisch deklariert werden, über einen lokalen Gültigkeitsbereich und eine lokale Lebensdauer (für Objekte). Finden Sie unter [Bereich](../cpp/scope-visual-cpp.md) ausführliche Informationen zum Umgang mit Namen mit lokalem Gültigkeitsbereich.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)