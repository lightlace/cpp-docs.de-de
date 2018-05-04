---
title: Verbundanweisungen (Blöcke) | Microsoft Docs
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
ms.openlocfilehash: 9a8823935ee2f871cdc033aec23f05fc108244e8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="compound-statements-blocks"></a>Verbundanweisungen (Blöcke)
Eine verbundanweisung besteht aus null oder mehr Anweisungen, die in geschweiften Klammern (**{}**). Einer Verbundanweisung kann an einer jeder beliebigen Stelle, an der eine Anweisung erwartet wird. Verbundanweisungen werden im Allgemeinen "Blöcke" genannt.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
{ [ statement-list ] }  
```  
  
## <a name="remarks"></a>Hinweise  
 Im folgenden Beispiel wird eine verbundanweisung als den *Anweisung* Teil der **Wenn** Anweisung (finden Sie unter [If Anweisung](../cpp/if-else-statement-cpp.md) Einzelheiten zur Syntax):  
  
```  
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
>  Da eine Deklaration eine Anweisung ist, eine Deklaration kann eine der Anweisungen in der *Anweisungsliste*. Folglich verfügen Namen, die innerhalb einer Verbundanweisung deklariert werden, jedoch nicht explizit als statisch deklariert werden, über einen lokalen Gültigkeitsbereich und eine lokale Lebensdauer (für Objekte). Finden Sie unter [Bereich](../cpp/scope-visual-cpp.md) Einzelheiten zum Umgang mit Namen mit lokalem Gültigkeitsbereich.  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über C++-Anweisungen](../cpp/overview-of-cpp-statements.md)